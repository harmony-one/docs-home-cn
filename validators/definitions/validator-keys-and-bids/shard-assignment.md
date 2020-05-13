# Shard Assignment分片分配

After a validator is elected, each of its elected BLS keys will be semi-randomly assigned to a shard in the network \(fully random shard assignment will come in the final phase of mainnet\). In the current stage of mainnet, the rule of assignment is simply based on the modulus of the BLS public key’s underlying bytes. For example, with 4 shards, a BLS public key like “xxxxxx8ad5” will be assigned to shard 1 because 5 % 4 = 1. Note that, for each of the elected BLS keys, the validator is obligated to spin up a validator node and validate blocks in the assigned shard.

一个验证者被选出之后，入选的BLS密钥将被半随机地分配给网络中的一个分片（完全随机的分片分配将在主网的最后阶段进行）。 在主网的当前阶段，分配规则仅基于BLS公钥基础字节的模数。例如，对于4个分片，会将BLS公钥（例如“ xxxxxx8ad5”）分配给分片1，因为5％4 =1。请注意，对于每个选举出的BLS私钥，验证者都有义务旋转验证者节点，并且验证分配的分片中的区块。

