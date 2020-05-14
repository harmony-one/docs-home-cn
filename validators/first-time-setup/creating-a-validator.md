# Creating A Validator创建验证者

{% hint style="info" %}
Wait for your node to sync before creating a validator.

Check your current block height with `./hmy blockchain latest-headers`

Check chain block height with `./hmy blockchain latest-header --node=[endpoint]`

创建验证器之前，请等待您的节点同步。

使用./hmy区块链最新标头检查您当前的区块高度

使用./hmy区块链最新标头--node = \[endpoint\]检查链块高度
{% endhint %}

## Creating a Validator创建一个验证`者` <a id="creating-a-validator"></a>

Replace everything in \[ \] with your own data: 用您自己的数据替换\[\]中的所有内容：

```text
./hmy --node="https://api.s0.t.hmny.io" staking create-validator \    --validator-addr [ONE ADDRESS] --amount 10000 \    --bls-pubkeys [BLS PUBLIC KEY1],[BLS PUBLIC KEY2] \    --name "[NAME]" --identity "[IDENTITY]" --details "DETAILS" \    --security-contact "CONTACT" --website "YOUR-WEBSITE.COM" \    --max-change-rate 0.1 --max-rate 0.1 --rate 0.1 \    --max-total-delegation 100000000 --min-self-delegation 10000 --passphrase
```

Copy the entire command. **Extra white spaces in the command could cause errors.** 复制整个命令。命令中**多余的空格可能导致错误**。

Name, identity, details, security-contact and website need to be put in double quotes if there are more than one word separated by space \(example --name "John the validator"\).‌如果用空格将一个以上的单词分隔开，（如：姓名，身份，详细信息，安全性联系方式和网站）则必须用双英文引号引起来（例如--name“John the validator”）。

The CLI will prompt you to enter your BLS key file password.‌CLI将提示您输入BLS密钥文件密码。

`--validator-addr` is the validator ONE address **\(string\)**‌

`--amount` is the initial amount of ONE you want to stake **\(float\)**‌

`--bls-pubkeys` takes a comma-separated list of BLS public keys **\(string\)**‌

`--name` will be the name displayed on the Staking Explorer **\(string\)**‌

`--identity` is additional information for the validator **\(string\)**‌

`--details` is the description of the validator **\(string\)**‌

`--security-contact` is security contact for the validator **\(string\)**‌

`--website` will be the website displayed on the Staking Explorer **\(string\)**‌

`--max-change-rate` is the maximum rate change the validator can do to their commission rate every epoch **\(float\)**‌

`--max-rate` is the maximum commission rate that the validator can set **\(float\)**‌

`--rate` is the commission rate of the validator **\(float\)**‌

`--max-total-delegation` is the maximum amount of ONE that can be delegated to this validator **\(float\)**‌

`--min-self-delegation` is the minimum amount of ONE the validator must stake to itself **\(float\)**

`--max-rate` and `--max-change-rate` cannot be changed later.

`--min-self-delegation` has to be at least 10,000 ONE.‌



--validator-addr是验证者的地址（字符串）‌

--amount是您要质押（float浮点数）的ONE的初始金额‌

--bls-pubkeys采用逗号分隔的BLS公钥列表（字符串）‌

--name将是在Staking Explorer中显示的名称（字符串）‌

--identity是验证器的附加信息（字符串）‌

--details是验证者（字符串）的描述‌

--security-contact是验证者的联系人（字符串）‌

--website将是在Staking Explorer中显示的网站（字符串）‌

--max-change-rate是验证器可以在每个时期（float浮点数）对其佣金率进行的最大变化率‌

--max-rate是验证者可以设置的最大佣金率（float浮点数 ）‌

--rate是验证者的佣金率（float浮点数）‌

--max-total-delegation是可以委派给此验证器的最大数量（float浮点数）‌

--min-self-delegation是验证者必须向自己抵押的最小数量（float浮点数）

--max-rate和--max-change-rate以后无法更改。

--min-self-delegation必须至少为10,000 ONE。

### When does the validator participate in election? 验证人何时参加选举？ <a id="when-does-the-validator-become-active"></a>

A new validator will be eligible for the election for next epoch. You can see the time until the next epoch on the [Staking Explorer](https://staking.harmony.one/portfolio).‌

Once your validator is elected, the validator will receive rewards and you will be able to see "BINGO" in the logs.

新的验证者将有资格参加下一个epoch的选举。您可以在Staking Dashboard中看到距离下一个epoch的时间。‌

选出验证人后，验证人将获得奖励，您将在日志中看到“ BINGO”。

```text
tail -n 1000 latest/zerolog-validator-*.log | grep -i BINGO
```

Example output输出示例：:

```text
{"level":"info","port":"9000","ip":"213.136.79.89","blockNum":3916,"epochNum":26,"ViewId":3916,"blockHash":"0xca71fc9aa92f694f664aa34d7e3e82cf9b678e3a062d3bbbabebfbc5f0598d84","numTxns":0,"numStakingTxns":0,"caller":"/mnt/jenkins/workspace/harmony-release/harmony/node/node_handler.go:359","time":"2019-12-11T14:49:08.983338784+01:00","message":"BINGO !!! Reached Consensus"}
```

If you don't want to participate in the election anymore, you can turn your validator inactive using an [Edit Validator transaction](https://docs.harmony.one/validators/validator/managing-your-validator/changing-your-validator-profile) with`--active false.`‌ 

如果您不想再参与选举，则可以使用-active false的Edit Validator指令将验证者变为休息状态。

## Checking Validator Information 检查验证者信息 <a id="checking-validator-information"></a>

Use the format command **./hmy --node="**[**https://api.s0.os.hmny.io**](https://api.s0.os.hmny.io/)**" blockchain validator information \[ONE ADDRESS\]** to check your validator information: 使用格式命令 **./hmy --node="**[**https://api.s0.os.hmny.io**](https://api.s0.os.hmny.io/)**" blockchain validator information \[ONE ADDRESS\]** 来检查您的验证者信息[：](https://api.s0.os.hmny.io”区块链验证程序信息[一个地址]检查您的验证程序信息：)

```text
./hmy --node="https://api.s0.t.hmny.io" blockchain validator information one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd
```

Example output: 输出示例：

```text
{  "id": "0",  "jsonrpc": "2.0",  "result": {    "booted-status": null,    "current-epoch-performance": {      "current-epoch-signing-percent": {        "current-epoch-signed": 95,        "current-epoch-signing-percentage": "1.000000000000000000",        "current-epoch-to-sign": 95,        "num-beacon-blocks-until-next-epoch": 21      }    },    "currently-in-committee": true,    "epos-status": "currently elected",    "epos-winning-stake": "6846745750000000000000000.000000000000000000",    "lifetime": {      "apr": "6.268807306506151937",      "blocks": {        "signed": 8602,        "to-sign": 8621      },      "reward-accumulated": 7.076705797578808e+21    },    "metrics": {      "by-bls-key": [        {          "earned-reward": 17373723528937510000,          "key": {            "bls-public-key": "1227f1ef2ba879562c693c2f99af023a9a127b25bfe21fa41c637039bfbd9cc68919d0edce4f2aa57983ffcbc39b1b01",            "earning-account": "one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd",            "effective-stake": "1369349150000000000000000.000000000000000000",            "group-percent": "0.032657375054393815",            "overall-percent": "0.010450360017406021",            "shard-id": 1          }        }      ]    },    "total-delegation": 4.184679e+24,    "validator": {      "address": "one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd",      "bls-public-keys": [        "1227f1ef2ba879562c693c2f99af023a9a127b25bfe21fa41c637039bfbd9cc68919d0edce4f2aa57983ffcbc39b1b01"      ],      "creation-height": 489,      "delegations": [        {          "amount": 1.184679e+24,          "delegator-address": "one1u6c4wer2dkm767hmjeehnwu6tqqur62gx9vqsd",          "reward": 4.383229639373062e+21,          "undelegations": []        },        {          "amount": 3e+24,          "delegator-address": "one167gc5t3f4uvupns2h8fsem9xzdgn2egra9w8d3",          "reward": 2.1040394698378544e+21,          "undelegations": []        }      ],      "details": "Soph #P-OPS Validator node",      "identity": "Soph",      "last-epoch-in-committee": 58,      "max-change-rate": "0.050000000000000000",      "max-rate": "0.900000000000000000",      "max-total-delegation": 1e+27,      "min-self-delegation": 1e+22,      "name": "Soph #P-OPS Validator node",      "rate": "0.100000000000000000",      "security-contact": "Soph",      "update-height": 489,      "website": "soph.harmony.one"    }  }}
```

exit: ⌘↩

If your validator does not sign more than 2/3 of the blocks in an epoch, the validator will be removed from the pool of eligible validators.

In order to be included in the pool again, you will have to use send an [Edit Validator transaction](https://app.gitbook.com/@harmony-one/s/home/validators/first-time-setup/creating-a-validator) with `--active true`.

如果您的验证者在一个epoch内签名的块不超过2/3，则该验证者将不再是合格的验证者。 你可以使用-active true的Edit Validator指令将验证者变为活跃状态。

