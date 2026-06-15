---
summary: 矩阵分解是将矩阵表示为特定结构矩阵乘积的方法，包括 SVD、Woodbury 恒等式、秩分解与条件数等核心工具。
tags: [mathematics, linear-algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-linear-algebra-basics.md
---

# 矩阵分解

## 定义

矩阵分解（Matrix Decomposition）是将一个矩阵分解为若干具有特殊结构的矩阵之乘积，以揭示其代数或几何性质，简化计算。

## 关键点

### 奇异值分解（SVD）

任意 $m \times n$ 实矩阵 $A$ 可分解为：

$$A = U \Sigma V^T$$

- $U \in \mathbb{R}^{m \times m}$：左奇异向量矩阵（正交）
- $V \in \mathbb{R}^{n \times n}$：右奇异向量矩阵（正交）
- $\Sigma \in \mathbb{R}^{m \times n}$：对角矩阵，对角元素 $\sigma_1 \geq \sigma_2 \geq \cdots \geq 0$ 为奇异值

**截断 SVD**：保留前 $k$ 个最大奇异值，得到最佳秩-$k$ 近似（Eckart–Young 定理）：

$$A_k = U_k \Sigma_k V_k^T$$

### Woodbury 恒等式

当 $A$ 可逆且受低秩修正 $UCV$ 时：

$$(A + UCV)^{-1} = A^{-1} - A^{-1}U(C^{-1} + VA^{-1}U)^{-1}VA^{-1}$$

特例（Sherman–Morrison 公式）：当 $U = u$, $V = v^T$, $C = 1$ 时简化为秩-1 更新。

### 条件数

$$\kappa(A) = \|A\| \cdot \|A^{-1}\|$$

在 2-范数下等于最大奇异值与最小奇异值之比：

$$\kappa_2(A) = \frac{\sigma_{\max}}{\sigma_{\min}}$$

条件数衡量矩阵对输入扰动的敏感程度。$\kappa(A) \gg 1$ 时称矩阵病态（ill-conditioned）。

### 秩分解

秩为 $r$ 的矩阵 $A \in \mathbb{R}^{m \times n}$ 可写为 $A = BC$，其中 $B \in \mathbb{R}^{m \times r}$，$C \in \mathbb{R}^{r \times n}$。

## 关联概念

- [[eigendecomposition]] — 方阵的特征分解是 SVD 的特殊情形
- [[vector-norms]] — 条件数依赖于所选矩阵范数
- [[pca]] — PCA 的核心计算步骤即为 SVD
