# Setup Cheatsheet指令备忘录

If you are new to setting up Validators, start [here](). 如果您不熟悉设置验证程序，请从首次建立开始。

1. Access your cloud instance. 访问您的云实例

```bash
ssh -i [KEY].pem [SSH ADDRESS]
```

![](../../.gitbook/assets/image%20%2811%29.png)

2. Install `tmux`, if your Linux distribution does not come with it. 如果您的Linux发行版不附带tmux，请安装tmux。

```bash
sudo yum install tmux
```

3. Download the Harmony CLI. 下载Harmony CLI。

```bash
curl -LO https://harmony.one/hmycli && mv hmycli hmy && chmod +x hmy
```

4. Create a BLS Key. 创建一个BLS密钥。

```text
./hmy keys generate-bls-key --passphrase
```

5. Download `node.sh`. 下载node.sh。

```bash
curl -LO https://raw.githubusercontent.com/harmony-one/harmony/master/scripts/node.sh \
&& chmod a+x node.sh
```

6. Start a new `tmux` session called `node`. 启动一个新的名为节点的tmux会话。 tmux new-session -s节点

```bash
tmux new-session -s node
```

7. Run the node. 运行节点。

{% tabs %}
{% tab title="Open Staking Network" %}
```bash
./node.sh -S -c -z -I -N staking -k [BLS KEY FILE].key
```
{% endtab %}
{% endtabs %}

8. Detach from the tmux session by pressing CTRL and B at the same time, then press D. 通过同时按CTRL和B然后按D来退出mux会话，。

9. Check that your node is syncing \(block height &gt; 0\). 检查您的节点是否正在同步（区块高度&gt; 0）。

```bash
./hmy blockchain latest-header
```

10. Create a new wallet. 创建一个新的钱包。

```bash
./hmy keys add [ACCOUNT NAME] --passphrase
```

11. Create your Validator. 创建您的验证者。

{% tabs %}
{% tab title="Mainnet" %}
```bash
./hmy --node="https://api.s0.t.hmny.io" staking create-validator \
    --validator-addr [ONE ADDRESS] --amount 100000 \
    --bls-pubkeys [BLS PUBLIC KEY1],[BLS PUBLIC KEY2] \
    --name JohnWhitton --identity JohnIdentity --details "John The Validator" \
    --security-contact John --website john@harmony.one \
    --max-change-rate 0.1 --max-rate 0.1 --rate 0.1 \
    --max-total-delegation 100000000 --min-self-delegation 100000 --passphrase
```
{% endtab %}
{% endtabs %}

12. Check that your ONE address exists as a validator 检查您的一个地址是否已经是验证者地址

{% tabs %}
{% tab title="Mainnet" %}
```bash
./hmy --node="https://api.s0.t.hmny.io" blockchain validator all | grep [ONE ADDRESS]
```
{% endtab %}
{% endtabs %}

14. Collect rewards收集奖励

{% tabs %}
{% tab title="Mainnet" %}
```bash
./hmy --node="https://api.s0.t.hmny.io" staking collect-rewards --delegator-addr [ONE ADDRESS] --passphrase
```
{% endtab %}
{% endtabs %}

15. Check validator information for active flag / availability \(block signed\) / etc ...检查验证者信息。

{% tabs %}
{% tab title="Mainnet" %}
```bash
./hmy --node="https://api.s0.t.hmny.io" blockchain validator information [VALIDATOR ONE ADDRESS]
```
{% endtab %}
{% endtabs %}



