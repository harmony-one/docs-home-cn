# Generating A BLS Key创建一个新的BLS密钥

You will need to generate a BLS key in order to run a validating node. When generating a BLS key, the CLI will ask you to provide a passphrase to encrypt the BLS key file.‌您将需要生成BLS密钥才能运行验证节点。 生成BLS密钥时，CLI会要求您提供密码来加密BLS密钥文件。

```bash
./hmy keys generate-bls-key --passphrase
```

{% hint style="danger" %}
Remember your passphrase. You will need it to decrypt the BLS key file in order to create a validator & start a node with that key.

Create a backup of your BLS key file or save the BLS private key \(optional\).

记住您的密码。 您将需要它来解密BLS密钥文件，以便创建验证者并使用该密钥启动节点。 对BLS密钥文件进行备份保存BLS私钥。
{% endhint %}

{% hint style="info" %}
The BLS public key is the same as the name of the file, without the `.key`.

BLS公钥与文件名相同，但不带.key。
{% endhint %}

### Checking which Shard the BLS will validate on检查BLS将在哪个分片上进行验证

You can check which shard your key will validate for using the following command. 您可以使用以下命令检查密钥将验证哪个分片。

```bash
./hmy --node="https://api.s0.t.hmny.io" utility shard-for-bls [BLS PUBLIC KEY]
```

Example output:输出示例：

```bash
{"shard-id":1}
```

