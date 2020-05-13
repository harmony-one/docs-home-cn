# Block Reward区块奖励

For each of the blocks produced and confirmed within a shard, it should contain signatures from the keys with more than 2/3 of the total voting power of the shard committee. Each confirmed block will produce 28 ONE as block reward for the validators behind the committee. The 28 ONE is initially allocated to all the validators whose BLS key\(s\) signed on the block, proportionally to the voting power of the key\(s\) that signed.

The allocated block reward for a validator will be further distributed to delegators proportionally to their stake after the commission fee is charged. For example, a validator with a commission rate of 25% got allocated 4 ONE for a block it signed. The validator staked 1000 ONE itself and it has 2 delegations each with 1000 ONE. The block reward distribution for this validator works as follows:

1. The commission fee of 1 ONE \(4 ONE \* 25%\) is cut from the original reward and credited to the validator.
2. The rest of the reward of 3 ONE is then distributed to all the stakers \(including both the validator and its delegators\) proportionally based on their stake. Since the stakers \(the validator and the two delegators\) each staked/delegated 1000 ONE, they each receive 1 ONE in the reward distribution.

For more information about block reward, please read our [token economics model](https://medium.com/harmony-one/harmonys-new-tokenomics-bcdac0db60d7).

对于在分片中产生并确认的每个区块，它应包含来自分片委员会总投票权的2/3以上的密钥签名。 每个确认的区块将为委员会后面的验证者产生28 ONE的区块奖励。 28 ONE最初分配给在块上签名的BLS私钥的所有验证者，与签名的私钥的投票权成比例。

在收取佣金之后，验证者得到的整体奖励将进一步按比例分配给委托者们。 例如，佣金率为25％的验证者为其签名的区块分配了4个“ 1”。 验证者自己抵押了1000 ONE，它有2个委托者，每个委托者都有1000 ONE。 该验证者的整体奖励分配方式如下：

1. 从原始奖励中扣除1个ONE（4 ONE \* 25％）的佣金，并记入验证者的帐户。
2. 然后，剩余的3个ONE奖励将根据他们的抵押按比例分配给所有抵押者（包括验证者及其委托人）。 由于抵押者们（验证者和两个委托人）各自抵押/委托了1000 ONE，因此他们在奖励分配中各获得1 ONE。

欲知更多区块奖励的相关信息，请参阅我们的[代币经济模型](https://mp.weixin.qq.com/s/NKMGwUbvL1muBFL57ysMIQ)。

