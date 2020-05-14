# Creating A Wallet 创建新的钱包

## New Wallet \(CLI\)使用CLI创建新钱包 <a id="new-local-account-creation"></a>

You need to provide a local account name of your choice and provide a passphrase. _\*\*_When creating an account, the CLI will ask you to provide a passphrase to encrypt the keystore file :

您需要选择一个本地帐户名称并提供密码。 \*\*创建帐户时，CLI会要求您提供密码来加密密钥库文件，示例：  
**./hmy keys add \[LOCAL ACCOUNT NAME\] --passphrase**  example : 

```text
./hmy keys add mylocalaccountname --passphrase
```

{% hint style="danger" %}
Remember your passphrase. You will need it to decrypt the account keystore in order to send transactions & perform other actions.

Also save your seed phrase \(mnemonic\) somewhere as well, in case you lose your keystore.

记住您的密码。您将需要它来解密帐户密钥库，以便发送交易和执行其他操作。 还要将种子短语（助记符）也保存在某个地方，以防丢失密钥库。
{% endhint %}

### Backing Up Your Keystore File \(Optional\) 创建此文件的备份

```text
./hmy keys location
```

The command above will return the location of your account keystore. You may want to create a backup of this file.‌上面的命令将返回您的帐户密钥库的位置。您可能要以此创建此文件的备份。‌ 

You can check the list of wallets \(local accounts\) with the following command: 您可以使用以下命令检查钱包列表（本地帐户）

```bash
./hmy keys list
```

Example output from above command 输出示例:

```bash
#NAME                                  ADDRESS
example-account1                      one1wh4p0kuc7unxez2z8f82zfnhsg4ty6dupqyjt2
```

## Helpful Information有用的信息

### Checking your account balance检查您的帐户余额

If you are running a node and your node is synced to the latest block, use the following command to check your balance : **./hmy balances \[ONE ADDRESS\]** ex: 如果您正在运行一个节点，并且您的节点已同步到最新的区块，请使用以下命令检查余额：./hmy balances \[ONE ADDRESS\] ：

```bash
./hmy balances one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd --node="<endpoint-address>"
```

If you are not running a node or your node is not synced, use the following command to check your balance : **./hmy --node="\[API\_endpoint\]" balances \[ONE ADDRESS\]** ex: 如果您没有运行节点，或者节点未同步，请使用以下命令检查余额 **./hmy --node="\[API\_endpoint\]" balances \[ONE ADDRESS\]** 

```bash
./hmy --node="https://api.s0.t.hmny.io" balances one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd
```

