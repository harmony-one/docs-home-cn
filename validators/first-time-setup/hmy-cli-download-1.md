---
description: Command-line interface to interact with Harmony blockchain
---

# HMY CLI Download Harmony CLI 下载



To interact with your node, we have developed the HMY CLI. With it, you will be able to do everything in your terminal。为了与您的节点进行交互，我们开发了HMY CLI。有了它，您将能够在终端上完成所有操作。

## Download the HMY CLI下载HMY CLI

### Linux

```bash
curl -LO https://harmony.one/hmycli && mv hmycli hmy && chmod +x hmy
```

### MacOS

```bash
curl -O https://raw.githubusercontent.com/harmony-one/go-sdk/master/scripts/hmy.sh
chmod u+x hmy.sh
./hmy.sh -d
```

{% hint style="danger" %}
For the MacOS version, use `./hmy.sh` instead of `./hmy` for all commands.

对于MacOS版本，对所有命令使用./hmy.sh而不是./hmy。
{% endhint %}

### Check the downloaded binary:检查下载的二进制文件： 

Run `./hmy cookbook`to see some commonly used commands. 运行./hmy cookbook以查看一些常用命令。

```bash
./hmy --node="https://api.s0.t.hmny.io" cookbook
```

Example output:输出示例：

```bash
#Cookbook of Usage ＃使用手册

#Note: ＃注意：

#1) Every subcommand recognizes a '--help' flag
#2) If a passphrase is used by a subcommand, one can enter their own passphrase interactively
#   with the --passphrase option. Alternatively, one can pass their own passphrase via a file
#   using the --passphrase-file option. If no passphrase option is selected, the default
#   passphrase of '' is used.
#3) These examples use Shard 0 of Open Staking Network as argument for --node
＃1）每个子命令都识别一个'--help'标志
＃2）如果子命令使用了密码，则可以交互输入自己的密码
＃与--passphrase选项一起使用。或者，可以通过文件传递自己的密码
＃使用--passphrase-file选项。如果未选择密码选项，则默认
使用 ''（没有密码）
＃3）这些示例使用Open Staking Network的Shard 0作为--node的参数

#Examples:＃例子：

＃1。检查给定链上的帐户余额
#1.  Check account balance on given chain
./hmy --node="https://api.s0.t.hmny.io" balances <SOME_ONE_ADDRESS>

＃2。检查已发送的交易
#2.  Check sent transaction
./hmy --node="https://api.s0.t.hmny.io" blockchain transaction-by-hash <SOME_TX_HASH>

＃3。列出本地帐户密钥
#3.  List local account keys
./hmy keys list

＃4。发送交易（等待40秒以确认交易）
#4.  Sending a transaction (waits 40 seconds for transaction confirmation)
./hmy --node="https://api.s0.t.hmny.io" transfer \
    --from <SOME_ONE_ADDRESS> --to <SOME_ONE_ADDRESS> \
    --from-shard 0 --to-shard 1 --amount 200 --passphrase

＃5。根据文件发送一批交易（“ --dry-run”选项仍然适用）
#5.  Sending a batch of transactions as dictated from a file (the `--dry-run` options still apply)
./hmy --node="https://api.s0.t.hmny.io" transfer --file <PATH_TO_JSON_FILE>
#Check README for details on json file format.

＃6。查看完整的交易收据
#6.  Check a completed transaction receipt
./hmy --node="https://api.s0.t.hmny.io" blockchain transaction-receipt <SOME_TX_HASH>

＃7。使用助记符导入帐户。提示用户提供助记符。
#7.  Import an account using the mnemonic. Prompts the user to give the mnemonic.
./hmy keys recover-from-mnemonic <ACCOUNT_NAME>

＃8。导入现有的密钥库文件
#8.  Import an existing keystore file
./hmy keys import-ks <PATH_TO_KEYSTORE_JSON>

＃9。使用secp256k1私钥导入密钥库文件
#9.  Import a keystore file using a secp256k1 private key
./hmy keys import-private-key <secp256k1_PRIVATE_KEY>

＃10。导出密钥库文件的secp256k1私钥
#10. Export a keystore file's secp256k1 private key
./hmy keys export-private-key <ACCOUNT_ADDRESS> --passphrase

＃11。生成BLS密钥，然后加密并将私钥保存到指定位置。
#11. Generate a BLS key then encrypt and save the private key to the specified location.
./hmy keys generate-bls-key --bls-file-path <PATH_FOR_BLS_KEY_FILE>

＃12。使用BLS密钥列表创建一个新的验证者
#12. Create a new validator with a list of BLS keys
./hmy --node="https://api.s0.t.hmny.io" staking create-validator --amount 10 --validator-addr <SOME_ONE_ADDRESS> \
    --bls-pubkeys <BLS_KEY_1>,<BLS_KEY_2>,<BLS_KEY_3> \
    --identity foo --details bar --name baz --max-change-rate 0.1 --max-rate 0.1 --max-total-delegation 10 \
    --min-self-delegation 10 --rate 0.1 --security-contact Leo  --website harmony.one --passphrase

＃13。编辑现有的验证者
#13. Edit an existing validator
./hmy --node="https://api.s0.t.hmny.io" staking edit-validator \
    --validator-addr <SOME_ONE_ADDRESS> --identity foo --details bar \
    --name baz --security-contact EK --website harmony.one \
    --min-self-delegation 0 --max-total-delegation 10 --rate 0.1\
    --add-bls-key <SOME_BLS_KEY> --remove-bls-key <OTHER_BLS_KEY> --passphrase

＃14。将金额委托给验证者
#14. Delegate an amount to a validator
./hmy --node="https://api.s0.t.hmny.io" staking delegate \
    --delegator-addr <SOME_ONE_ADDRESS> --validator-addr <VALIDATOR_ONE_ADDRESS> \
    --amount 10 --passphrase

＃15。取消委托给验证者
#15. Undelegate to a validator
./hmy --node="https://api.s0.t.hmny.io" staking undelegate \
    --delegator-addr <SOME_ONE_ADDRESS> --validator-addr <VALIDATOR_ONE_ADDRESS> \
    --amount 10 --passphrase


＃16。作为委托人收集奖励
#16. Collect block rewards as a delegator
./hmy --node="https://api.s0.t.hmny.io" staking collect-rewards \
    --delegator-addr <SOME_ONE_ADDRESS> --passphrase

＃17。检查当选的验证者
#17. Check elected validators
./hmy --node="https://api.s0.t.hmny.io" blockchain validator elected

＃18。获取当前的抵押效用指标
#18. Get current staking utility metrics
./hmy --node="https://api.s0.t.hmny.io" blockchain utility-metrics

＃19。检查失败的放样交易的内存记录
#19. Check in-memory record of failed staking transactions
./hmy --node="https://api.s0.t.hmny.io" failures staking

＃20。检查您的BLS公钥将被分配给哪个分片作为验证者
#20. Check which shard your BLS public key would be assigned to as a validator
./hmy --node="https://api.s0.t.hmny.io" utility shard-for-bls 2d61379e44a772e5757e27ee2b3874254f56073e6bd226eb8b160371cc3c18b8c4977bd3dcb71fd57dc62bf0e143fd08
```

## Troubleshooting 常见错误： <a id="troubleshooting"></a>

Frequently encountered errors:

```bash
./hmy cookbook

-bash: ./hmy: cannot execute binary file: Exec format error
​#Make sure you downloaded the right version for your OS.
-bash：./hmy：无法执行二进制文件：Exec格式错误
＃确保您为操作系统下载了正确的版本。
```

