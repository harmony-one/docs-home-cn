# Changing Validator Information编辑验证者信息

You can edit your validator’s information using the CLI with the following command. 您可以使用CLI执行以下命令来编辑验证者的信息。

## Using the Binary使用Binary:

```bash
./hmy --node="<endpoint-address>" staking edit-validator \
    --validator-addr [ONE ADDRESS] [FIELDS TO EDIT] --passphrase
```

## Using the Shell Wrapper使用Shell Wrapper:

```bash
./hmy.sh -- node="<endpoint-address>" staking edit-validator \
    --validator-addr [ONE ADDRESS] [FIELDS TO EDIT] --passphrase
```

The CLI will prompt you to enter your BLS key file password. Only the `--validator-addr` field is required; all other fields are optional. CLI将提示您输入BLS密钥文件密码。只有--validator-addr字段是必须；所有其他字段都是可选的。

* `--validator-addr` is the validator ONE address that you want to edit **\(string\)**
* `--active` to set validator as eligible or not to be elected **\(bool\)**
* `--name` to change the name displayed on the Staking Explorer **\(string\)**
* `--identity` to change the identity field **\(string\)**
* `--website` to change the website field **\(string\)**
* `--details` to change the details field **\(string\)**
* `--security-contact` to change the security contact field **\(string\)**
* `--rate` to change the current commission rate **\(float\)**
* `--min-self-delegation` to change the minimum stake by the validator **\(float\)**
* `--max-total-delegation` to change the maximum stake that the validator can take **\(float\)**
* `--remove-bls-key` to remove a BLS public key associated with your validator **\(string\)**
* `--add-bls-key` to add another BLS public key to your validator **\(string\)**

--validator-addr是验证者的地址（字符串）‌

--active将验证者设置为活跃（参与竞选）或休息（不参与竞选）（bool）

--bls-pubkeys采用逗号分隔的BLS公钥列表（字符串）‌

--name将是在Staking Explorer中显示的名称（字符串）‌

--identity是验证器的附加信息（字符串）‌

--details是验证者（字符串）的描述‌

--security-contact是验证者的联系人（字符串）‌

--website将是在Staking Explorer中显示的网站（字符串）‌

--rate是验证者的佣金率（float浮点数）‌

--max-total-delegation是可以委派给此验证者的最大数量（float浮点数）‌

--min-self-delegation是验证者必须向自己抵押的最小数量（float浮点数）

--remove-bls-key 删除与验证者的BLS公钥 （字符串）

--add-bls-key将另一个BLS公钥添加到您的验证者（字符串）

{% hint style="info" %}
`--validator-addr`is the only field that is required.

Sending the command without the arguments will leave those fields of your validator as is.

--validator-addris是唯一需要的字段。 发送不带参数的命令将使验证器的那些字段保持原样。
{% endhint %}

{% hint style="danger" %}
`--max-rate` and `--max-change-rate` cannot be changed later.

`--min-self-delegation` has to be at least 10,000 ONE

--max-rate和--max-change-rate以后无法更改。 

--min-self-delegation必须至少为10,000 ONE。
{% endhint %}

