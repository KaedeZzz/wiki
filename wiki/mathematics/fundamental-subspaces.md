---
summary: 矩阵的四个基本子空间（列空间、行空间、零空间、左零空间）及秩-零度定理，是理解线性映射结构的基石。
tags: [mathematics, linear-algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-linear-algebra-basics.md
---

# 基本子空间

## 定义

对于 $m \times n$ 矩阵 $A$，其四个基本子空间（Four Fundamental Subspaces）完整刻画了 $A$ 作为线性映射的结构。

## 关键点

### 四个基本子空间

| 子空间 | 符号 | 所在空间 | 维度 |
|--------|------|----------|------|
| 列空间（Column Space） | $\text{Col}(A) = \text{Im}(A)$ | $\mathbb{R}^m$ | $r$ |
| 行空间（Row Space） | $\text{Row}(A) = \text{Col}(A^T)$ | $\mathbb{R}^n$ | $r$ |
| 零空间（Null Space） | $\text{Null}(A) = \ker(A)$ | $\mathbb{R}^n$ | $n - r$ |
| 左零空间（Left Null Space） | $\text{Null}(A^T)$ | $\mathbb{R}^m$ | $m - r$ |

其中 $r = \text{rank}(A)$。

### 秩-零度定理

$$\text{rank}(A) + \text{nullity}(A) = n$$

即列空间的维度加上零空间的维度等于列数。

### 正交补关系

- $\text{Row}(A) \perp \text{Null}(A)$，且 $\text{Row}(A) \oplus \text{Null}(A) = \mathbb{R}^n$
- $\text{Col}(A) \perp \text{Null}(A^T)$，且 $\text{Col}(A) \oplus \text{Null}(A^T) = \mathbb{R}^m$

### 直觉

- **列空间**：$Ax = b$ 有解当且仅当 $b \in \text{Col}(A)$
- **零空间**：齐次方程 $Ax = 0$ 的解集
- 正交补关系意味着 $\mathbb{R}^n$ 被行空间与零空间正交分割

## 关联概念

- [[matrix-decomposition]] — SVD 直接给出四个子空间的正交基
- [[eigendecomposition]] — 特征空间是 $(A - \lambda I)$ 的零空间
