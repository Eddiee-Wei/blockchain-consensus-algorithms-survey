# Sources and Further Reading

Accessed 2026-07-25. Original protocol papers and official project documentation are preferred.

## Paper record

- Wei, Runze. “The advance of consensus algorithm in blockchain.” *Applied and Computational Engineering* 18.1 (2023): 5–15. [Publisher page](https://ace.ewapub.com/article/view/4657), [publisher PDF](https://ace.ewapub.com/article/view/4657.pdf), [DOI](https://doi.org/10.54254/2755-2721/18/20230954).
- [Applied and Computational Engineering author guide](https://ace.ewapub.com/proceedings_guide/for_authors): publication and CC BY 4.0 information.
- [CONF-CDS 2023 conference record](https://www.confcds.org/5th.html).

## Foundational protocols

- Nakamoto, Satoshi. “Bitcoin: A Peer-to-Peer Electronic Cash System.” [Official Bitcoin paper](https://bitcoin.org/en/bitcoin-paper).
- Castro, Miguel, and Barbara Liskov. “Practical Byzantine Fault Tolerance.” OSDI 1999. [USENIX page](https://www.usenix.org/conference/osdi-99/presentation/practical-byzantine-fault-tolerance).
- Lamport, Leslie. “Paxos Made Simple.” 2001. [Microsoft Research](https://www.microsoft.com/en-us/research/publication/paxos-made-simple/).
- Ongaro, Diego, and John Ousterhout. “In Search of an Understandable Consensus Algorithm.” USENIX ATC 2014. [Raft project and paper](https://raft.github.io/).

## Current system documentation

- Ethereum. [Consensus mechanisms](https://ethereum.org/developers/docs/consensus-mechanisms/).
- Ethereum. [Gasper: Casper FFG + LMD-GHOST](https://ethereum.org/developers/docs/consensus-mechanisms/pos/gasper/).
- Ethereum. [The Merge](https://ethereum.org/roadmap/merge/).
- Ethereum. [Single-slot finality research](https://ethereum.org/roadmap/single-slot-finality/). This is roadmap research, not presented here as a deployed feature.
- Hyperledger Fabric. [The ordering service](https://hyperledger-fabric.readthedocs.io/en/latest/orderer/ordering_service.html).
- Hyperledger Fabric. [Migrating from Raft to BFT](https://hyperledger-fabric.readthedocs.io/en/latest/raft_bft_migration.html).
- Solana. [Whitepaper](https://solana.com/solana-whitepaper.pdf).
- Apache ZooKeeper. [ZooKeeper internals](https://zookeeper.apache.org/doc/current/zookeeperInternals.html).

## Protocol developments beyond the paper

- Yin, Maofan, et al. “HotStuff: BFT Consensus with Linearity and Responsiveness.” PODC 2019. [arXiv](https://arxiv.org/abs/1803.05069).
- Danezis, George, et al. “Narwhal and Tusk: A DAG-based Mempool and Efficient BFT Consensus.” EuroSys 2022. [arXiv](https://arxiv.org/abs/2105.11827).
- Spiegelman, Alexander, et al. “Bullshark: DAG BFT Protocols Made Practical.” CCS 2022. [arXiv](https://arxiv.org/abs/2201.05677).
- Avalanche. [Official whitepapers](https://www.avalabs.org/whitepapers), [consensus architecture](https://build.avax.network/docs/nodes/architecture/consensus).

## Reading note

Protocol names are not complete specifications. Production behavior depends on the exact software version, validator-set configuration, cryptography, network assumptions, execution layer, and governance. Links in this repository are research context, not an endorsement of any token or deployment.
