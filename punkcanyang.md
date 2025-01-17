---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容


---

# {Punkcan}

1. Optimism 治理新手...
2. 你认为你会完成本次残酷学习吗？
	- 应该是可以的

## Notes

<!-- Content_START -->

### 2025.01.06

后续的笔记我都尽可能白话

### 用最白话的方式，解释Optimism是什么？
好的，用最白話的方式來解釋 Optimism 是什麼：

假设以太坊是一条高速公路，但是他限速100，當大家都想在上面開車時，就會開始塞車，導致速度變慢、而且上公路要费用，如果人太多就只能把手續費變貴，让出的起较高手续的车子先上。

Optimism 就是在高速公路旁邊蓋了一條新的快速道路。
虽然他也有限速，但是设计不同，所以他限速更高，例如300，這條快速道路的目標是讓大家可以在上面快速、便宜地開車（進行交易），然後再把結果匯回高速公路（以太坊），以確保安全。

把结果存回以太坊的这个动作很重要，因为Optimism跟L1相比，并没有所谓的验证者，所以他仰赖以太坊上面的安全机制，来确保他的数据是可信任的。

### Optimistic Rollup

Optimism 使用一種叫做「Optimistic Rollup」的技術。

就是先假設所有交易都是沒問題的，除非有人跳出來說有問題。

如果沒人說有問題，那這些交易就被視為有效。然後再將很多筆交易「捲起來」打包成一批，再送回以太坊。

### OP Stack

Optimism 的技術是基於 OP Stack 開發的，OP Stack 是一套開源的軟體組件，可以讓大家更容易建立新的 Layer 2 區塊鏈。

**主要特点：**
- 将区块链的各个功能拆分成独立的模块，如数据存储、交易排序、执行等。开发者可以根据需要选择、替换或修改这些模块。
- 支持不同的虚拟机（如 EVM），开发者可以根据应用需求选择最适合的执行环境。
- 支持不同链之间的互操作性。

### Superchain愿景

Optimism 的目標是建立一個「Superchain」，也就是一個由很多條鏈組成的網路，這些鏈都可以共享安全、溝通層和開發工具。

另外Optimism 有自己的代幣，叫做 OP 代幣。OP 代幣持有者可以參與 Optimism 的治理，也就是決定 Optimism 的未來發展方向。

---

### OP 的 Gas 是怎么计算的？

在 Optimism 网络中，交易费用（Gas 费）主要由两部分组成：

1. L2 执行费用：这部分费用与在以太坊主网（L1）上执行交易类似，按照交易在 L2 上执行所消耗的 Gas 量计算。由于 L2 的 Gas 价格较低，这部分费用通常占总费用的比例很小。
2. L1 数据费用：这是将 L2 交易数据打包并提交到以太坊主网时产生的费用。具体而言，Optimism 会将多笔 L2 交易打包成一个批次（batch），并以 calldata 的形式提交到 L1。每个字节的 calldata 在 L1 上都会产生相应的 Gas 费用。因此，交易数据越大，L1 数据费用就越高。

L1 数据费用通常占总交易费用的绝大部分，超过 90%。
Optimism 通过数据压缩等技术手段，努力减少提交到 L1 的数据量，降低用户的交易成本。

为了将交易数据从 Layer 2（L2）提交到以太坊主网（Layer 1，L1），需要支付一定的费用。为确保这些费用的合理性并应对 L1 Gas 价格的波动，Optimism 引入了以下参数：

- **固定开销（Fixed Overhead）**：每笔交易都会产生一个固定的基础费用，用于覆盖将交易数据打包并提交至 L1 的基本处理成本。例如，Optimism 曾将固定开销从 2750 Gas 减少至 2100 Gas，以降低用户的交易费用。
- **费用比例系数（Fee Scalar）**：这是一个动态调整的系数，用于应对 L1 Gas 价格的波动。当 L1 Gas 价格上涨时，费用比例系数可以提高，以确保有足够的资金覆盖提交数据的成本；当 L1 Gas 价格下降时，该系数可以降低，以减少用户的交易费用。Optimism 曾将费用比例系数从 1.5 降低到 1.24，以优化用户的交易成本。

公式：`L1 数据费用 = 费用比例系数 × L1 Gas 价格 ×（交易数据大小 + 固定开销）`

举例：`L1 数据费用 = 1.24 × L1 Gas 价格 ×（交易数据大小 + 2100）`

### 2025.01.07


### 2025.01.08



<!-- Content_END -->
