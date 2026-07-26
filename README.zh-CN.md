<p align="right">
  <strong>语言：</strong>
  <a href="./README.md"><img src="https://img.shields.io/badge/English-switch-d0d7de?style=flat-square" alt="切换到英文"></a>
  <a href="./README.zh-CN.md"><img src="https://img.shields.io/badge/%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-%E5%BD%93%E5%89%8D-0969da?style=flat-square" alt="简体中文（当前）"></a>
</p>

# 区块链共识算法综述：一篇兴趣驱动的学习与梳理

[论文 PDF](paper/the-advance-of-consensus-algorithm-in-blockchain.pdf) · [专家深读](docs/expert-analysis.zh-CN.md) · [分享素材](docs/share-kit.zh-CN.md)

[![DOI](https://img.shields.io/badge/DOI-10.54254%2F2755--2721%2F18%2F20230954-blue)](https://doi.org/10.54254/2755-2721/18/20230954)
[![Applied and Computational Engineering](https://img.shields.io/badge/ACE-2023-2e8b57)](https://ace.ewapub.com/article/view/4657)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

<p align="center">
  <img src="assets/paper-first-page.png" width="420" alt="论文首页">
</p>

> 2023 年，我因为对区块链与分布式共识的个人兴趣，开始思考一个简单的问题：在没有中央协调者的情况下，分布式参与者如何对同一份账本达成一致？这份兴趣最终变成了这篇简短的综述。

## 我为什么写这篇论文

当时，区块链是我的一个个人兴趣方向。我想系统理解的不是某一种数字资产，而是它背后的基础问题：互不完全信任的节点，为什么能够对交易顺序和账本状态形成共同结果？

因此，我选择了文献中经常被放在一起讨论的六种代表性机制：工作量证明（PoW）、权益证明（PoS）、委托权益证明（DPoS）、实用拜占庭容错（PBFT）、Paxos 和 Raft，整理它们的基本思路、优点、局限和适用场景。

我的目的不是提出一种名为 “Advance Consensus” 的新协议，而是把当时的学习与思考组织成一篇入门综述。

## 论文信息

| 项目 | 内容 |
|---|---|
| 正式题名 | *The advance of consensus algorithm in blockchain* |
| 作者 | Runze Wei |
| 出版载体 | *Applied and Computational Engineering*, Volume 18, pp. 5–15 |
| 日期 | 2023-10-23 |
| DOI | [10.54254/2755-2721/18/20230954](https://doi.org/10.54254/2755-2721/18/20230954) |
| 出版方 | [EWA Publishing 文章页](https://ace.ewapub.com/article/view/4657) |
| 许可 | CC BY 4.0 |

这是一篇综述/比较文章，不提出新协议，也不包含协议实现或实验代码。

## 这篇综述讲了什么

| 机制 | 最简单的理解 |
|---|---|
| **工作量证明（PoW）** | 用可验证的计算工作量决定出块权重，并提高重写历史的成本 |
| **权益证明（PoS）** | 用质押权益选择验证者，并以经济约束规范其行为 |
| **委托权益证明（DPoS）** | 由权益持有人选举少量代表参与出块、验证与治理 |
| **PBFT** | 让一组已知副本在有限拜占庭故障下仍能达成一致 |
| **Paxos** | 通过相交多数派，在崩溃故障模型下对一个结果达成一致 |
| **Raft** | 用更容易理解的 leader 与复制日志机制处理崩溃故障 |

论文先介绍六种机制的基本流程，再从效率、能耗、安全假设、去中心化程度和应用场景等角度进行比较。

## 我想传达的核心结论

共识算法没有脱离场景的“最好”方案。不同机制是在不同条件下做选择：

- 开放网络通常需要工作量或权益一类抗女巫机制；
- 较小且身份已知的节点集合可以更快达成一致，但更依赖准入与治理；
- 容忍 Byzantine fault 通常比只处理 crash fault 需要更多通信；
- 吞吐、延迟和能耗只有与网络、攻击者、成员关系和最终性假设一起说明才有意义。

所以，这篇综述真正想做的不是给六种机制排出一个名次，而是建立一个基本认识：**先理解假设，再比较取舍。**

## 今天如何阅读这篇论文

论文发表后，共识技术仍在持续演进。这六种机制也并不完全处于同一抽象层：PoW、PoS、DPoS 常被用于讨论区块链的成员权重和验证者选择；PBFT 属于 Byzantine-fault-tolerant 状态机复制；Paxos 与 Raft 则属于 crash-fault-tolerant 复制协议。

为了让首页保持简单并忠实于原论文，更严格的协议纠错、实际系统案例和截至 2026 年的技术背景都放在[专家深读](docs/expert-analysis.zh-CN.md)中。需要结构化比较时，可以查看[`共识机制矩阵`](comparison/consensus-matrix.csv)。

## 这个仓库包含什么

- 出版方开放获取 PDF、来源说明与 SHA-256 校验值；
- 中英双语论文介绍；
- 六类机制的结构化比较；
- 独立的专家深读与延伸资料；
- 可用于 GitHub、LinkedIn、微信、知乎和技术分享会的文案。

## 仓库结构

```text
.
├── README.md
├── README.zh-CN.md
├── CITATION.cff
├── LICENSE
├── assets/
│   └── paper-first-page.png
├── comparison/
│   └── consensus-matrix.csv
├── docs/
│   ├── expert-analysis.zh-CN.md
│   ├── share-kit.zh-CN.md
│   └── sources.md
└── paper/
    ├── README.md
    ├── references.bib
    ├── SHA256SUMS
    └── the-advance-of-consensus-algorithm-in-blockchain.pdf
```

## 引用

```bibtex
@article{Wei2023Consensus,
  author  = {Wei, Runze},
  title   = {The advance of consensus algorithm in blockchain},
  journal = {Applied and Computational Engineering},
  volume  = {18},
  number  = {1},
  pages   = {5--15},
  year    = {2023},
  doi     = {10.54254/2755-2721/18/20230954}
}
```

## 许可与范围

论文和论文首页衍生图由 Runze Wei (2023) 按出版方的 CC BY 4.0 条款发布。仓库独立解读与分享材料同样按 CC BY 4.0 提供。外部链接材料遵循各自许可。本项目用于技术教育，不构成投资建议，也不替代具体协议的安全审计。
