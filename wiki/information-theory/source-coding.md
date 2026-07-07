---
summary: 无损压缩的极限是熵 H(X)。Shannon-Fano、Huffman、算术编码依次逼近；Kraft 不等式给出前缀码的存在条件；用错分布 P̂ 编码的冗余恰为 KL 散度 D(P‖P̂)。
tags: [information-theory, coding, compression]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-coding-source-coding-source-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-source-coding-theorem.md
  - raw/information-theory/2026-07-06-coding-source-coding-expected-code-length.md
  - raw/information-theory/2026-07-06-coding-source-coding-fundamental-limit-of-compression.md
  - raw/information-theory/2026-07-06-coding-source-coding-discrete-memoryless-source.md
  - raw/information-theory/2026-07-06-coding-source-coding-fixed-length-source-code.md
  - raw/information-theory/2026-07-06-coding-source-coding-naive-compression-code.md
  - raw/information-theory/2026-07-06-coding-source-coding-naive-compression-with-typical-set.md
  - raw/information-theory/2026-07-06-coding-source-coding-prefix-free-code.md
  - raw/information-theory/2026-07-06-coding-source-coding-extension-codes.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-kraft-inequality.md
  - raw/information-theory/2026-07-06-coding-source-coding-coding-theorem-for-a-random-variable.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-shannon-fano-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-construction-of-shannon-fano-coding-by-shannon,-1948.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-huffman-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-optimality-of-the-huffman-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-properties-of-an-optimal-prefix-free-code.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-properties-of-the-huffman-code.md
  - raw/information-theory/2026-07-06-coding-source-coding-arithmetic-coding-arithmetic-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-arithmetic-coding-arithmetic-coding-optimality.md
  - raw/information-theory/2026-07-06-coding-source-coding-arithmetic-coding-uniqueness-of-arithmetic-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-comparison-of-shannon-fano-coding-and-arithmetic-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-symbol-coding-minimax-redundancy.md
  - raw/information-theory/2026-07-06-coding-source-coding-redundancy-in-source-coding.md
  - raw/information-theory/2026-07-06-coding-source-coding-error-exponent.md
  - raw/information-theory/2026-07-06-coding-source-coding-path-length-lemma.md
---

# 信源编码

## 定义

将离散无记忆信源（DMS，i.i.d. $\sim P$）产生的符号序列 $X^n = (X_1,\dots,X_n)$ **唯一**映射为二进制串 $c(X^n)$（码字）。目标：最小化**期望码长**：

$$\mathbb{E}[\ell(X^n)] = \sum_{x^n} P(x^n)\,\ell(x^n)$$

## 关键点

### 信源编码定理与压缩极限

**任何**唯一可译码满足：

$$\mathbb{E}\!\left[\tfrac{1}{n}\ell(X^n)\right] \geq H(X)$$

*"熵是无损压缩的下界，不可逾越"*。上界可达：对足够大 $n$，存在编码使 $\mathbb{E}[\tfrac{1}{n}\ell(X^n)] \leq H(X) + \epsilon$。

**构造性证明**（用 [[typicality-and-aep]]）：

- 典型集大小 $\leq 2^{n(H+\epsilon)}$，每个典型序列用 $\lceil n(H+\epsilon)\rceil + 1$ 比特（含前缀标志）编码；
- 非典型序列用 $\lceil n\log|\mathcal{X}|\rceil + 1$ 比特（少见，可以浪费）；
- 加权求和 $\leq n(H+\epsilon') \to nH$。

### 前缀码与 Kraft 不等式

**前缀码**：无码字是另一码字的前缀 → 无需分隔符，可即时解码。

**Kraft 不等式**：$\{l_i\}$ 是某唯一可译码的码长集合 $\Rightarrow$

$$\sum_i 2^{-l_i} \leq 1$$

也是**存在性**条件：任何满足 Kraft 的长度序列都能构造前缀码。

**几何解释**（二叉树上）：给深度 $l_i$ 分配一个码字后，深度 $l_{\max}$ 上有 $2^{l_{\max}-l_i}$ 个叶子被封禁；所有封禁叶子之和 $\leq 2^{l_{\max}}$。

### 单变量编码定理（$L \geq H(X)$）

$L - H(X) = \sum_i p_i(l_i - \log\tfrac{1}{p_i}) = \tfrac{-1}{\ln 2}\sum_i p_i \ln\tfrac{2^{-l_i}}{p_i} \geq \tfrac{-1}{\ln 2}\sum_i p_i(\tfrac{2^{-l_i}}{p_i}-1) \geq 0$

（$\ln x \leq x - 1$ + Kraft 不等式）

### Shannon-Fano 编码

**直觉**：让高概率符号有短码字。取 $l_i = \lceil\log_2\tfrac{1}{p_i}\rceil$，则

$$L < \sum_i p_i(\log_2\tfrac{1}{p_i} + 1) = H(X) + 1$$

Shannon 1948 构造：按概率降序排列，$l_i$ 位的编码 = 累积概率 $P_s = \sum_{i<s}p_i$ 的二进制展开前 $l_i$ 位。相邻概率至少差 $2^{-l_s}$，保证前缀性质。

### Huffman 编码

**最优前缀码**（对给定 $P$，无前缀码期望长度更短）。算法：

1. 每步合并两个最低概率符号（概率相加）
2. 递归直到只剩一个节点
3. 沿树赋 0/1

**最优前缀码的两个必要条件**：

- 长度反序：$p_j > p_k \Rightarrow l_j \leq l_k$
- 两个最低概率符号有**相同长度**且是相邻叶子（只差最后一位）

复杂度：$m-1$ 次合并（$m$ 为字母表大小）。

**路径长度引理**：Huffman 树中，所有节点（内部 + 叶子）的概率之和 = 期望码长。

### 算术编码

用 $[0,1)$ 的**嵌套子区间**表示序列——每个符号把当前区间按其概率切分。

- 序列长度 $n$ 后，区间长度 = 序列概率 $p(x^n)$
- 用**最大二进制小数区间** $[\tfrac{j}{2^l}, \tfrac{j+1}{2^l})$ 内点表示；$2^{-l}\leq p \Rightarrow l\geq\lceil\log_2\tfrac{1}{p}\rceil$
- 每序列比每符号编码多用 $\leq 2$ 比特，per-symbol：$\tfrac{L_n}{n} < H(X) + \tfrac{2}{n} \to H(X)$

**vs Shannon-Fano**：算术编码不需要预排序（对长序列更实用），代价是有时多 1 比特（两个二进制区间共存的情形）。**算术编码是当今 zstd/GZip 系压缩器的核心**。

### 用错分布的冗余

若真实分布是 $P$、我们用估计 $\hat P$ 设计码长 $l_i = \log\tfrac{1}{\hat p_i}$，则：

$$L = \sum_i p_i\log\tfrac{1}{\hat p_i} = H(P) + D(P\|\hat P)$$

**冗余 = KL 散度**（每符号）。这就是 [[kl-divergence]] 的另一物理解释。

**Minimax 冗余**：真分布未知但属于集合 $\mathcal{P}$ 时，最优编码策略：

$$R^* = \min_{\hat P}\max_{P\in\mathcal{P}} D(P\|\hat P)$$

### 错误指数（有损情形）

带 $M = e^{nR}$ 码字的信源码错误概率满足 $p_e \leq e^{-n\,e(R)}$，其中可靠性函数 $e(R) = \max_{\rho>0}[\rho R - E_s(\rho)]$。刻画错误概率随分组长度衰减的速率。

## 关联概念

- [[information-entropy]] — 熵是压缩下界
- [[typicality-and-aep]] — 典型集给出构造性上界证明
- [[kl-divergence]] — 冗余 = KL；交叉熵损失的经典对应
- [[loss-function]] — ML 中交叉熵损失 = 学习 $\hat P$ 以最小化 $\hat P$-编码冗余
- [[channel-coding]] — 通信另一半（源 vs 信道）
- [[discrete-distributions]] — 编码对象的概率结构
