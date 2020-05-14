---
description: Use the below steps to reset your validator
---

# Collecting Rewards收集奖励

You can collect your block rewards with the following command. 您可以使用以下命令收集奖励。

## 使用 Binary:

```bash
./hmy --node="<endpoint-address>" staking collect-rewards \
--delegator-addr [ONE ADDRESS] --passphrase
```

## 使用 Shell Wrapper:

```bash
./hmy.sh -- node="<endpoint-address>" staking collect-rewards \
--delegator-addr [ONE ADDRESS] --passphrase
```

### Example 例:

```bash
./hmy --node="https://api.s0.t.hmny.io" staking collect-rewards \
--delegator-addr one1km7xg8e3xjys7azp9f4xp8hkw79vm2h3f2lade --passphrase
```

The CLI will prompt your for the passphrase of the delegation account.

`--delegator-addr` is the account to collect rewards for

CLI将提示您输入委派帐户的密码。 --delegator-addr是用于收集奖励的帐户

{% hint style="warning" %}
You can only collect ALL of your block rewards at once, not partially. 您只能一次性收集全部块奖励
{% endhint %}

