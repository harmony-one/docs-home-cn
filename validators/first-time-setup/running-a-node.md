---
description: Using node.sh
---

# Running a Node运行节点

## Download node.sh下载node.sh <a id="download-node-sh"></a>

‌

Run the following command to download the node.sh script:运行以下命令以下载node.sh脚本：

```text
curl -LO https://raw.githubusercontent.com/harmony-one/harmony/master/scripts/node.sh \&& chmod a+x node.sh‌
```

## TMUX <a id="tmux"></a>

Install tmux if your Linux distribution does not already come with it.

请安装tmux，如果你的Linux机器里还没有tmux的话。

```text
sudo apt-get install tmux
```

## Run Node运行节点  <a id="run-node"></a>

**1.** Create a new tmux session called "node". 创建一个名为“ node”的新tmux会话。

```text
tmux new-session -s node
```

You'll want to use a tmux session in order to leave your node running, while you are not connected to your instance.

For any Debian based OS like Ubuntu and others, please install the package below in case you are NOT running statically linked binaries via parameter `-I`:

在不连接到实例的情况下，您将需要使用tmux会话来使节点保持运行状态。

对于任何基于Debian的操作系统，如Ubuntu和其他操作系统，请安装以下软件包:

```text
sudo apt-get install libgmp-dev
```

**2.** Run the node.sh script with the following command. Once you do, it will ask for a passphrase for your BLS key file. Type your passphrase on the screen that follows and your node should be up and running.

使用以下命令运行node.sh脚本。完成后，它将要求为您的BLS密钥文件输入密码。在随后的屏幕上键入密码，您的节点应该已启动并正在运行。

```bash
./node.sh -S -z -k [BLS KEY FILE].key
```

Use `-S` to run node.sh as any user.

Use `-c` to automatically clear old data for a refreshed network.

Use `-z` to run with staking enabled.

Use `-I` to run with the statically linked binary \(recommended\).

Use `-N [NETWORK]` to specify which network to connect to.

Use `-k [BLS KEY FILE]` to specify which BLS key to run the node with.

For the complete list of parameters use `./node.sh --help`

Only use `-c` for our testing networks. Do not use for Mainnet.‌

使用-S以任何用户身份运行node.sh。

使用-c自动清除用于旧数据以刷新网络。

使用-z在启用质押的情况下运行。

使用-I与静态链接的二进制文件一起运行。

使用-N \[NETWORK\]指定要连接到的网络。

使用-k \[BLS KEY FILE\]指定运行该节点的BLS密钥。

获取有关参数的完整列表，请使用./node.sh --help

仅将-c用于我们的测试网络。请勿用于主网。

**3.** Detach your "node" tmux session by press \[**Ctrl\]+b**, releasing and and then press **d**. Detaching from your session will allow you to safely disconnect from your instance, while leaving your node running in the cloud.‌

同时按\[Ctrl\] + b然后按d，退出“节点” tmux会话。从tmux中分离将使您可以安全地与实例断开连接，同时使节点在云中运行。

**4.** To check if your node is syncing properly, run the below command and check that the block height is greater than 0.要检查您的节点是否正确同步，请运行以下命令，并检查块高度是否大于0。

```text
./hmy blockchain latest-headers
```

{% hint style="success" %}
Harmony依靠信标链（也称为分片0）来促进跨分片交易。为了使节点正常工作，您的非分片0和分片0都需要完全同步
{% endhint %}

**5.** Confirm that you are fully synced before continuing. Issue the command in the format **./hmy --node= "\[SHARD\_RPC\_ENDPOINT\]" blockchain latest-headers**, where SHARD\_RCP\_ENDPOINT would be having that format : api.s\[Shard \#\].\[NETWORK\].hmny.io ex : 

确认您已完全同步，然后再继续。以**./hmy --node= "\[SHARD\_RPC\_ENDPOINT\]" blockchain latest-headers**的格式发出命令，其中 SHARD\_RCP\_ENDPOINT将采用以下格式：api.s \[Shard＃\]。\[NETWORK\] .hmny.io 例如：

```bash
./hmy --node="https://api.s0.t.hmny.io" blockchain latest-headers‌
```

**6.** And verity the blocks shown in step 4 and 5 are closed or equals to each other‌ 并且验证步骤4和5中所示的区块是否一致

## Multiple BLS Keys \(Optional and recommended for advanced users\)多个BLS密钥共用机器（可选，建议高级用户使用） <a id="multiple-bls-keys-optional-and-recommended-for-advanced-users"></a>

Optionally, you can run the node using multiple BLS keys if you want.‌您可以根据需要使用多个BLS密钥运行节点。

**1.** Keys are loaded from `.hmy/blskeys` folder which has to be created first: 1.首先创建.hmy / blskeys 从该文件夹中加载密钥：

```text
mkdir -p .hmy/blskeys
```

**2.** Copy all the [previously created BLS key\(s\)](https://docs.harmony.one/home/validators/first-time-setup/generating-a-bls-key) to this new folder将所有先前创建的BLS密钥复制到此新文件夹中：:

```text
cp *.key .hmy/blskeys
```

Make sure all your BLS keys belong to the same shard when using multiple BLS keys. You can use the command below to check each one of them.使用多个BLS密钥时，请确保所有BLS密钥都属于同一分片。您可以使用下面的命令来检查每个。

```bash
./hmy --node="https://api.s0.t.hmny.io" utility shard-for-bls [BLS PUBLIC KEY]
```

**3.** For each BLS key file, a corresponding `<blskey>.pass` file needs to be created inside folder`.hmy/blskeys`with the passphrase inside it.

For any `.key` if no passphrase file is available, it will use the default specified when running the node e.g., `./node.sh -p blspass.txt`‌

对于每个BLS密钥文件，需要在folder.hmy / blskeys内部创建一个相应的 .pass文件，并在其中使用密码短语。

对于任何.key如果没有可用的密码短语文件，它将使用运行节点时指定的默认值，例如./node.sh -p blspass.txt

**4.** You can now run the node using parameter **-M** for multiple BLS keys. Parameter **-k** will not be used anymore as we are loading multiple BLS keys here现在，您可以对多个BLS密钥使用参数-M运行该节点。由于将在此处加载多个BLS密钥，因此不再使用参数-k：:

```text
./node.sh -S -z -M
```

## Helpful Information有用的信息 <a id="helpful-information"></a>

To re-attach to your tmux session where your `node.sh` is running, use the following command: 要重新连接到node.sh的tmux会话，请使用以下命令：

```text
tmux attach-session -t node
```

‌

​[TMUX Cheatsheet](https://gist.github.com/henrik/1967800)​

