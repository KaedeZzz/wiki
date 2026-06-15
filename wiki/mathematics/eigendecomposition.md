---
summary: 矩阵的特征值分解，包括谱定理、正定矩阵、Perron-Frobenius 定理与对角化条件。
tags: [mathematics, linear-algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-linear-algebra-eigen.md
---
# 特征分解

## 定义

矩阵 $A \in \mathbb{R}^{n \times n}$ 的特征分解将其表示为特征值与特征向量的组合。标量 $\lambda$ 和非零向量 $x$ 满足：

$$Ax = \lambda x$$

时，$\lambda$ 称为特征值，$x$ 称为对应的特征向量。特征值由特征多项式确定：

$$\det(A - \lambda I) = 0$$

## 关键点

### 对角化

若 $A$ 有 $n$ 个线性无关的特征向量，则可对角化：

$$A = P \Lambda P^{-1}$$

$P$ 的列为特征向量，$\Lambda = \text{diag}(\lambda_1, \dots, \lambda_n)$。对角化将矩阵乘幂简化为 $A^k = P \Lambda^k P^{-1}$。

### 谱定理

**实对称矩阵**（更一般地，Hermitian 矩阵 $A = A^*$）满足：
- 所有特征值为**实数**
- 不同特征值对应的特征向量**正交**
- 可正交对角化：$A = Q \Lambda Q^T$，其中 $Q$ 为正交矩阵

谱定理是 PCA、谱聚类等方法的理论基础。

### 半正定矩阵（PSD）

$A$ 为半正定当且仅当以下等价条件之一成立：
- 所有特征值 $\lambda_i \geq 0$
- 对任意 $x$，$x^T A x \geq 0$
- 存在 $B$ 使 $A = B^T B$

PSD 矩阵在优化（凸性判定）和统计（协方差矩阵）中至关重要。

### Perron-Frobenius 定理

设 $A$ 为**非负不可约矩阵**（所有元素 $\geq 0$，对应图强连通），则：
- 存在唯一的最大正特征值 $\lambda_1 >0$（Perron 根）
- 对应特征向量的所有分量严格为正
- $\lambda_1$ 是单根

该定理保证了 PageRank 和特征向量中心性的良定义性。

### Hermitian 矩阵

复方阵 $A$ 满足 $A = A^*$（共轭转置等于自身）。实对称矩阵是 Hermitian 矩阵的特例。谱定理对 Hermitian 矩阵同样成立，特征值为实数，特征向量可取为酉正交基。

## 关联概念

- [[vector-norms]] — 谱范数由最大奇异值（与特征值相关）决定
- [[matrix-decomposition]] — 特征分解是 SVD、Cholesky 等分解的基础
- [[pca]] — PCA 本质上是对协方差矩阵做特征分解
- [[centrality-measures]] — 特征向量中心性直接使用邻接矩阵的主特征向量
