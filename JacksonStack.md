---
timezone: Asia/Shanghai
---


# Kylin

1. 自我介绍  
   rust, web3, layer2   
2. 你认为你会完成本次残酷学习吗？  
   Y

## Notes

<!-- Content_START -->

### 2025.01.06
**Optimism Rollup 概述**  
Optimism 是一种基于 “Optimistic Rollup” 的二层扩展解决方案，其核心理念是利用以太坊等“父”区块链的安全性，通过继承其共识机制（如 PoW 或 PoS）而不提供自身的共识机制。  
这种设计确保了 Optimism 可以在提供高效交易和降低成本的同时，依赖以太坊的安全保障和数据完整性。  

在块存储方面，Optimism 通过压缩格式将 L2 区块数据写入以太坊链上（L1）；使用 EIP-4844 blobs 提交交易，降低了存储成本，同时确保了区块数据的不可篡改性。  
在区块生产中，网络主要依赖一个称为“排序器”（sequencer）的单一角色进行管理。  
排序器负责提供交易确认、状态更新，以及构建和执行 L2 区块，同时将用户交易提交到 L1。为了避免 MEV（最大可提取价值）问题，排序器的内存池为私有，每两秒生成一个区块，无论是否为空块。   

Optimism 支持两种交易路由方式：用户可以直接将交易提交到排序器，从而降低费用，但由于排序器的集中性，这类交易不具备抗审查性；  
另一种方式是通过 L1 提交交易（即存款），这些交易最终被纳入相应的 L2 区块中，并继承了以太坊级别的抗审查能力。  
在区块执行方面，Optimism 的执行引擎可以通过点对点网络同步状态，也可以通过从 L1 数据派生 L2 区块实现抗审查的区块同步。  

Optimism 的跨层桥接功能允许用户在 L2 和 L1 之间转移 ETH 或代币（包括 ERC20 代币）。  
当从 L1 到 L2（即存款）时，交易会在与存款相关的 L1 区块对应的 L2 区块中被记录。  
而从 L2 到 L1（即提款）时，整个过程分为初始化提款、提交提款证明以及故障挑战期后完成提款三个阶段，挑战期通常为 7 天，期间可以通过监控系统识别不正确的提款操作。  

Optimistic Rollup 的状态承诺机制会将状态提交到以太坊（L1），但不会直接提供其有效性的证明。这些状态在 7 天的挑战窗口期内会被视为待处理，若无人挑战，则视为最终承诺；若被挑战，则通过“故障证明”流程验证并替换。  
需要注意的是，挑战不会改变 OP 主网的交易顺序和状态，只会影响已发布的状态承诺。  
目前，Optimism 基金会是 OP 主网上唯一的区块生产者，同时其故障证明机制正随着 EVM 等效性更新进行改进，进一步提升系统的稳定性和安全性。    


<!-- Content_END -->
