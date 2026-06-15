---
summary: 量化图中节点重要性的一组指标，包括度中心性、特征向量中心性、介数中心性、PageRank 等。
tags: [mathematics, graph-theory]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-graph-theory-centrality.md
---
# 中心性度量

## 定义

中心性（centrality）是图论中用于量化节点在网络中"重要程度"的一类指标。不同中心性捕捉不同维度的重要性。

## 关键点

### 度中心性

最简单的度量——节点的度（邻居数）：

$$C_D(i) = k_i$$

归一化后除以 $n - 1$。

### 特征向量中心性

节点的重要性与其邻居的重要性成正比：

$$x_i = \frac{1}{\lambda}\sum_j A_{ij} x_j$$

即 $Ax = \lambda x$——$x$ 是邻接矩阵 $A$ 对应最大特征值 $\lambda_1$ 的特征向量（由 Perron-Frobenius 定理保证非负）。

### 介数中心性

节点 $v$ 位于其他节点对之间最短路径上的比例：

$$C_B(v) = \sum_{s \neq v \neq t} \frac{\sigma_{st}(v)}{\sigma_{st}}$$

$\sigma_{st}$ 为 $s$-$t$ 最短路径总数，$\sigma_{st}(v)$ 为经过 $v$ 的数量。介数高的节点是网络的"桥梁"。

### 接近中心性

节点到所有其他节点距离之和的倒数：

$$C_C(i) = \frac{n - 1}{\sum_j d(i, j)}$$

### PageRank

随机游走解释：以概率 $d$（阻尼因子，通常 $d = 0.85$）沿边随机跳转，以概率 $1 - d$ 均匀随机跳转到任意节点。稳态分布即 PageRank 值：

$$\text{PR}(i) = \frac{1-d}{n} + d \sum_{j \to i} \frac{\text{PR}(j)}{k_j^{\text{out}}}$$

### Katz 中心性

对所有长度的游走加权求和：

$$C_{\text{Katz}}(i) = \sum_{k=1}^{\infty} \sum_j \alpha^k (A^k)_{ji}$$

$\alpha < 1/\lambda_1$ 保证收敛。Katz 中心性可视为特征向量中心性的推广。

## 关联概念

- [[graph-fundamentals]] — 中心性基于图的邻接结构定义
- [[eigendecomposition]] — 特征向量中心性直接来自邻接矩阵的谱分解
- [[markov-chain]] — PageRank 本质上是马尔可夫链的稳态分布
