---
summary: LDPC 用稀疏校验矩阵 H 与因子图上的消息传递算法实现高效近容量解码；密度演化预测无限长码性能；对 BEC，逼近 Shannon 极限 1-ε。
tags: [information-theory, coding, graph-algorithms]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-low-density-parity-check-matrix-(ldpc).md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-parity-check-matrix.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-systematic-generator-matrix.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-factor-graph-for-ldpc.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-message-passing.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-message-passing-for-decoding-binary-erasure-channel.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-density-evolution.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-degree-distribution.md
  - raw/information-theory/2026-07-06-coding-channel-coding-ldpc-irregular-ldpc-codes.md
  - raw/information-theory/2026-07-06-coding-channel-coding-shannon-limit-of-bec.md
  - raw/information-theory/2026-07-06-coding-channel-coding-converting-to-systematic-form.md
---

# LDPC 码

## 定义

**低密度奇偶校验（Low-Density Parity-Check）码**是一族 [[channel-coding]] 意义下的**线性块码**，其校验矩阵 $H$ 稀疏（每行/每列 1 的数量远小于矩阵尺寸）。这个稀疏性使得基于**因子图上消息传递**的迭代解码在计算上可行，并能逼近 [[channel-capacity]] 的 Shannon 极限。

## 关键点

### 规则 LDPC

**规则 $(n,k)$ LDPC 码**：

- 每一码位（列）参与 $d_v$ 个校验方程（**变量节点度**）
- 每个校验方程（行）涉及 $d_c$ 个码位（**校验节点度**）

**设计速率**：

$$\frac{k}{n} = 1 - \frac{d_v}{d_c}$$

若 $H$ 各行线性独立，这就是真实速率；否则存在冗余行，删除后真实速率更高。

### 因子图表示

$H$ 天然对应一个二部图：

- 每列 $j$ → 一个**变量节点** $v_j$
- 每行 $i$ → 一个**校验节点** $c_i$
- $H_{ij}=1$ → 边 $v_j - c_i$

这正是 [[factor-graph]] 结构。稀疏 $H$ ⇔ 稀疏图 ⇔ 消息传递可高效运行。

### 消息传递解码

每次迭代交替两步：

1. 变量节点 $v$ 向每个相连的校验节点 $c$ 发送消息 $m_{vc}$
2. 校验节点 $c$ 向每个相连的变量节点 $v$ 发送消息 $m_{cv}$

**外传信息原则**：$v\to c$ 时不使用 $c$ 上一轮传给自己的信息（避免自我强化）；$c\to v$ 亦然。

**BEC 情形**（擦除信道）的直观规则：

- 初始 $m_{vc}$ = 信道输出 $\in\{0,1,?\}$；所有初始 $m_{cv} = ?$
- 变量节点：只要有任一非擦除输入即可锁定值
- 校验节点：只要至多一个"?"就能用奇偶约束解出

复杂度 $\propto$ (边数)$\times$(迭代次数)。

### 密度演化

**问题**：预测 $n\to\infty$ 时，给定度分布下的解码性能。

**关键假设**：每个节点的输入消息**独立**（对稀疏 + 长图近似成立，因局部图无回路）。

**规则 LDPC 在 BEC(ε)**：设 $p_t = \Pr(v\to c$ 消息在第 $t$ 步为 ?$)$，$q_t = \Pr(c\to v$ 为 ?$)$。

$$p_t = \epsilon\,(q_{t-1})^{d_v - 1},\qquad q_t = 1 - (1 - p_t)^{d_c - 1}$$

合并：

$$p_t = \epsilon\bigl(1 - (1 - p_t)^{d_c - 1}\bigr)^{d_v - 1}$$

递推收敛到 0 ⇔ 解码成功；发散 ⇔ 失败。收敛阈值 $\epsilon^*$ 即该码的**噪声容忍上限**。

### 度分布多项式

用多项式简洁地描述图的度结构：

**节点视角**：

$$L(x) = \sum_i L_i x^i,\quad R(x) = \sum_i R_i x^i$$

$L_i$ = 度-$i$ 变量节点占比，$R_i$ = 度-$i$ 校验节点占比。设计速率 $\tfrac{k}{n} = 1 - \tfrac{L'(1)}{R'(1)}$。

**边视角**：

$$\lambda(x) = \sum_i \lambda_i x^{i-1},\quad \rho(x) = \sum_i \rho_i x^{i-1}$$

$\lambda_i$ = 连接度-$i$ 变量节点的边占比。密度演化的通用形式基于 $(\lambda, \rho)$，允许**不规则 LDPC**（各节点度可异）——通过优化度分布可以逼近 Shannon 极限。

### BEC 的 Shannon 极限

对 BEC(ε)，[[channel-capacity]] $C = 1 - \epsilon$。可靠通信最大速率 $R^* = C$，即擦除率上限 $\epsilon = 1 - R$；$R = 1/2$ 时对应 $\epsilon = 0.5$。经良设计的不规则 LDPC 码在 $n\to\infty$ 时**逐点**逼近这一极限。

### 系统形式与实际构造

若 $G = [I_k | P]$（系统生成矩阵），则码字 = $[\mathbf{x} | \mathbf{x}P]$（原文 + 校验位）。校验矩阵 $H = [P^T | I_{n-k}]$。这种形式在 LDPC 的编码器实现中常见。

## 关联概念

- [[channel-coding]] — 线性块码、Hamming 距离、最优解码的通用理论
- [[channel-capacity]] — LDPC 逼近 Shannon 极限
- [[factor-graph]] — 消息传递解码的图结构基础
- [[fundamental-subspaces]] — 校验矩阵与生成矩阵的正交补关系
- [[markov-chain]] — 消息传递中"独立假设"背后的树近似
