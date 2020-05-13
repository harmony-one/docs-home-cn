# Introduction简介

## **What is Harmony?‌ Harmony 是谁？**

**‌**Harmony is a fast and secure blockchain for decentralized applications. Our production mainnet supports 4 shards of 1000 nodes, producing blocks in 8 seconds with finality.

Our Effective Proof-of-Stake \(EPoS\) reduces centralization while supporting stake delegation, reward compounding and double-sign slashing.

**Harmony是一个去中心化的，快速安全的区块链。 我们产品化主网的生产者支持4个分片，1000个节点，并最终在8秒内生产出块。**

**我们的有效权益证明（EPoS）减少了中心化，同时支持委托、复合奖励复利和分叉签名惩罚双重签名。**

Harmony aims to build an open network of nodes operated and governed by a large community. This node community is called Pangaea.

Are we decentralized yet? There’s no consensus without participation. There are now 1,000 Harmony nodes – so far 320 of them run by the community – in line with thousands of Bitcoin and Ethereum nodes. Pangaea consists of volunteers and validators from more than 100 countries and most of them have never run a node before.

### Secure, Random State Sharding

Harmony has transcended the blockchain trilemma by bringing the best research to production. Sharding is proven to _scale_ blockchains without compromising _security_ and _decentralization_.

We divide not only our network nodes but also the _blockchain states_ into shards, scaling linearly in all three aspects of machines, transactions and storages.

To prevent single shard attacks, we must have a sufficiently large number of nodes per shard and cryptographic randomness to re-shard regularly. Each shard has 250 nodes for strong security guarantee against Byzantine behaviors. We use Verifiable Random Function \(VDF\) for unbiasable and unpredictable shard membership.

**安全随机的状态分片**  


**通过将最前沿的研究工程化，Harmony打破了区块链著名的不可能三角。事实证明，分片技术在不牺牲安全性和去中心化的前提下，能够极大地提升区块链的性能。**  


**我们不仅实现了网络分片，也实现了状态分片，从而在机器、交易和存储三个方面做线性扩容。**  


**为了防止单个分片攻击，我们必须保证每个分片上有足够数量的节点，并且对分片做加密的随机的重分片。每个分片有250个节点，为抗拜占庭行为提供了安全强大的保障。我们将可验证延迟函数（VDF）无差别、不可预测地用于分配分片位置。**  


### Fast Consensus w/ Instant Finality

Harmony has innovated on the battle-tested Practical Byzantine Fault Tolerance \(PBFT\) for fast consensus of block transactions. Our Fast BFT \(FBFT\) leads to low transaction fees and 1-block-time finality in Harmony Mainnet.

We use Boneh–Lynn–Shacham \(BLS\) constant-sized signatures to commit blocks in a single round of consensus messages. We achieve 8-second block time with _view changes in production_ against adversarial or unavailable leaders.

Harmony Mainnet was launched in June 2019. Our network has produced 10M+ blocks with 20k+ transactions in _publicly traded, native_ ONE tokens.

**快速共识和即时结算**  


**Harmony对久经考验的实用拜占庭容错（PBFT）方面进行了创新，从而实现区块链交易的快速共识。 我们的快速BFT（FBFT）可在Harmony主网中带来低廉的交易费用和单区块时间的确定性。**  


**我们使用Boneh–Lynn–Shacham（BLS）恒定大小的签名在单轮共识中提交区块。通过视图更换对抗敌对的或者无领导情况，实现了8秒出块。**  


**Harmony主网在2019年6月启动。我们的网络出块数超1000万，处理了超过2万笔的公开交易。**  


### Effective PoS & Token Economics

Harmony has designed a novel Proof-of-Stake \(PoS\) mechanism for network security and economics. Our Effective Proof-of-Stake \(EPoS\) reduces centralization and _distributes rewards fairly_ to thousands of validators.

Our staking mechanism supports delegation and reward compounding. To support 100% uptime but fully open participation, EPoS slashes validators who double-sign and it penalizes elected but unavailable nodes.

Harmony Economics Model caps the annual insurance at 441 million tokens \(about 3% rate in long term\). Our model gives validators a simple and predictable return. All transaction fees are burnt to offset the insurance, naturally leading to _zero inflation_ when our network usage becomes high.

**有效的PoS和代币经济学**  


**Harmony从网络安全和经济性的角度出发，设计了一种新颖的权益证明（PoS）机制。 我们的有效权益证明（EPoS）避免权益集中，力图将奖励公平地分配给数千个验证者。**  


**我们的抵押机制支持委托和复利。为了保证网络在去中心化的同时达到100%的稳定运行，EPOS机制会惩罚限制双重签名分叉区块的验证者和惩罚运行不稳定节点的验证者。**  


**Harmony的经济模型将每年固定增发4.41亿个代币（长期来看，3%的增发率）。 我们的模型让验证者能够简单地预测收入回报。所有的交易费用都会被销毁，从而抵消了增发，在我们网络使用率变高时，自然地达到零通胀。**  


