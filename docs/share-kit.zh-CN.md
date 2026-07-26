# 分享素材包

下列素材把“论文原始综述”和“2026 年技术补充”明确分开，可按平台长度直接改写。

## 30 秒介绍

2023 年，因为对区块链和分布式共识的个人兴趣，我写了这篇综述。最初的问题很简单：没有中央协调者，分布式节点怎样对同一份账本达成一致？论文用入门方式梳理了 PoW、PoS、DPoS、PBFT、Paxos 和 Raft 的基本思想、优点、局限与应用场景。它不提出新协议，核心结论也不是哪一种机制最好，而是：先理解成员关系、故障模型和信任假设，再比较性能与取舍。伴读仓库另外提供了更严格的技术校准和 2026 年延伸阅读。

## 60 秒英文介绍

> Can Proof of Work, PBFT, and Raft be ranked in one table? Only after their assumptions are aligned. PoW, PoS, and DPoS mainly address open membership, Sybil resistance, and validator selection. PBFT provides Byzantine-fault-tolerant state-machine replication for a known validator set, while Paxos and Raft are crash-fault-tolerant protocols. The 2023 paper offers an accessible survey of these six families. This companion repository preserves that overview while adding a stricter taxonomy, primary sources, and a 2026 update covering Ethereum’s Gasper design, Hyperledger Fabric’s Raft and SmartBFT orderers, HotStuff, DAG-based BFT, and Avalanche-style sampling. The practical lesson is simple: do not choose a consensus protocol from a throughput ranking. Start with membership, the adversary, network timing, finality, and governance—then evaluate performance within those constraints.

## GitHub / LinkedIn 短帖

2023 年，因为对区块链和分布式共识的个人兴趣，我写了论文 *The advance of consensus algorithm in blockchain*。它从一个基础问题出发：没有中央协调者，分布式参与者如何对同一份账本达成一致？

这是一篇入门综述，而不是一种新协议。论文梳理了 PoW、PoS、DPoS、PBFT、Paxos 和 Raft 的基本思想、优点、局限与应用场景。它最想传达的并不是一个统一排名，而是：共识算法没有脱离场景的“最好”方案，必须先理解假设，再比较取舍。

现在，我把论文原文、双语导读和分享素材整理成了一个独立仓库。首页保留简洁的论文介绍；更严格的协议分类、常见概念纠错，以及 HotStuff、DAG-BFT、Avalanche 等后续路线，则单独放在专家深读中。

## 微信 / 知乎长帖

### 标题候选

1. PoW、PBFT 和 Raft，为什么不能放在一张榜单里直接排名？
2. 六类共识算法的真正分界：成员关系、故障模型与最终性
3. 从 2023 综述到 2026：区块链共识算法的技术校准

### 正文

谈到区块链共识，人们很容易问：“哪一种算法最先进、最快、最安全？”但这个问题缺了最重要的前提：谁可以成为节点，节点可能怎么坏？

PoW、PoS 和 DPoS 主要服务开放或治理式网络。它们给身份赋予稀缺权重，并决定由谁提议或验证区块。PBFT、Paxos 和 Raft则更接近状态机复制：节点集合通常已知，问题是这些副本怎样对日志顺序达成一致。

这里还有第二条分界。PBFT 假设部分节点可以任意作恶；经典系统用 `3f+1` 个副本容忍 `f` 个 Byzantine fault。Paxos 和 Raft 只建模 crash fault。TLS 和签名可以认证发送者，却不能自动阻止一个已被攻陷的副本对不同节点发送冲突内容。

这意味着“Raft 吞吐更高，所以应该替换 PoW”不是完整结论。两者交换了根本不同的信任模型。真正的协议选型必须先回答：成员是开放还是许可？攻击者会宕机还是恶意作恶？网络多久恢复同步？最终性可以概率收敛还是必须确定提交？抗女巫依靠算力、权益还是外部身份？

2023 年论文 *The advance of consensus algorithm in blockchain* 的价值，是把 PoW、PoS、DPoS、PBFT、Paxos 和 Raft 六类常见机制放到一个入门视野。它的不足也来自同一点：若没有分层，读者会把协议族、抗女巫机制和复制协议当成同类产品。

截至 2026 年，现实系统又提供了更丰富的组合。Ethereum 用 Gasper 把 LMD-GHOST fork choice 与 Casper FFG finality 结合；Hyperledger Fabric 文档同时区分 Raft CFT orderer 与 SmartBFT BFT orderer；Solana 的 Proof of History更准确地说是可验证时钟，需与 stake 和 Tower BFT 一起解释。

研究前沿也不止原文六类。HotStuff 改进 leader-based BFT 的结构与通信；Narwhal/Tusk、Bullshark 把数据传播与排序解耦；Avalanche 用反复随机抽样形成亚稳态偏好；Ethereum single-slot finality则仍在探索如何缩短最终化而不让聚合和网络负担失控。

所以，共识算法没有脱离场景的“冠军”。更专业的比较顺序应该是：先写信任边界，再写安全和活性；先说明最终性和网络假设，再测吞吐与延迟；最后把权益集中、治理、运维恢复和真实攻击成本纳入同一张图。

## 8 页分享大纲

1. **问题**：为什么“最快共识算法”是一个不完整问题？
2. **分类轴**：开放/许可成员，Crash/Byzantine fault。
3. **PoW**：工作量、概率最终性和 51% 算力。
4. **PoS/DPoS**：协议族、经济安全与治理集中。
5. **PBFT**：`3f+1`、quorum、确定性与通信代价。
6. **Paxos/Raft**：CFT 日志复制，不等于 BFT。
7. **2026 地图**：Gasper、SmartBFT、HotStuff、DAG、Avalanche。
8. **选型**：成员 → 对手 → 网络 → 最终性 → 性能 → 治理。

## 常见问答

### Q1：论文提出了新的 Advance Consensus 算法吗？

没有。标题意为“区块链共识算法的发展/进展”，正文是一篇比较六类机制的综述，没有新协议伪代码、实现或实验。

### Q2：PoW 的 51% 是 51% 的节点吗？

不是。它指攻击者控制足以主导相关链选择的哈希算力/工作量份额。大量非挖矿全节点不会等比例增加出块工作量。

### Q3：PoS 一定比 PoW 更安全吗？

不能脱离协议和威胁模型判断。PoS 可降低持续能耗并通过 slashing 提供经济约束，但还需评价权益集中、长距离攻击、弱主观性、客户端多样性和社会层恢复。

### Q4：PBFT 为什么通常不直接扩到几万个验证者？

经典正常路径存在大量副本间消息和签名验证，带宽与延迟随成员规模迅速上升。现代方案常用委员会、聚合签名、线性通信或 DAG 数据层缓解。

### Q5：Paxos 和 Raft 能防恶意节点吗？

基础模型不能。它们保证的是 crash fault 下的一致性；恶意副本可违反协议，需要 BFT 设计和相应 quorum。

### Q6：Proof of History 是一种共识吗？

更准确地说，它是可验证时间/事件排序机制。Solana 的完整共识还依赖 stake-weighted voting 和 Tower BFT。

### Q7：吞吐最高的协议就是最好的吗？

不是。TPS 依赖硬件、网络、交易大小、批量和执行逻辑，而且更小的许可验证者集本来就更容易获得高吞吐。必须同时报告信任和故障假设。

### Q8：仓库里的 2026 观点属于原论文吗？

不属于。仓库明确标记独立技术校准，原始论文 PDF 保持不变。

## 发布检查清单

- 使用正式题名、唯一作者、页码与 DOI；
- 写成 survey/review，不包装成新协议实现；
- 明确六类机制的成员关系和故障模型；
- 不把 PoW 51% 写成节点数；
- 不把某种早期币龄规则概括为全部 PoS；
- 不把 Paxos/Raft 写成 Byzantine fault tolerant；
- 不把 PoH 单独写成 Solana 的完整共识；
- 区分 2023 原文、2026 更新与仍在研究的路线图；
- 不用理论 TPS 做投资或生产安全承诺。
