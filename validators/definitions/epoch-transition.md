# Epoch TransitionEpoch转换

In Harmony mainnet, there are 4 shards each producing new blocks separately and in parallel. The block heights between shards are not synchronized so you will see different shards have different block heights.

An epoch is a period of time when the beacon shard \(i.e. shard 0, the coordinator for other shards\) produces a fixed number of blocks. In Harmony mainnet, an epoch is 2¹⁴ = 16384 blocks \(~1.5 days\) in the beacon shard. Once an epoch is completed in the beacon shard, that change is also passed onto the other shards, thus all shards are synchronized by epoch.

At the end of each epoch, the committee election process will take place to elect the committees for the next epoch. The election process takes into account all the staking transactions confirmed before the election happens. The election result will take effect immediately, so we encourage all candidate validators to spin up their nodes even before the election happens.

在Harmony主网和Stake Heist中，有4个分片，每个分片分别并行地产生新的区块。 分片之间的区块高度不同步，因此您将看到不同的分片具有不同的区块高度。

一个epoch是信标分片（比如分片0，其他分片的协调器）产生固定数量的区块的时间段。 在Harmony主网中，信标分片中，一个epoch是²¹⁴ = 16384个块（约1.5天）。在信标分片中完成一个epoch后，该更改也将传递给其他分片，因此所有分片都将在一个epoch内进行同步。

在每个epoch结束时，将进行新一轮选举程序，以选出下一个epoch的委员会。 选举过程将考虑在选举发生之前确认所有抵押交易。 选举结果一旦选出，立即生效，因此我们鼓励所有候选验证者尽量在选举发生之前就提前运转起其节点。

