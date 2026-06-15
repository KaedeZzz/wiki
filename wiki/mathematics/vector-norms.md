---
summary: 向量与矩阵的范数定义，包括 $L^p$ 范数、算子范数、Frobenius 范数及有限维范数等价性。
tags: [mathematics, linear-algebra]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-linear-algebra-norms.md
---
# 向量范数与矩阵范数

## 定义

范数是赋予向量空间"长度"概念的函数 $\|\cdot\|: V \to \mathbb{R}_{\geq 0}$，满足正定性、齐次性和三角不等式。

## 关键点

### $L^p$ 范数

$$\|x\|_p = \left(\sum_{i=1}^n |x_i|^p\right)^{1/p}, \quad p \geq 1$$

常用特例：
- **$L^1$（Manhattan 范数）**：$\|x\|_1 = \sum_i |x_i|$，在稀疏优化 / LASSO 中常用
- **$L^2$（Euclidean 范数）**：$\|x\|_2 = \sqrt{\sum_i x_i^2}$，最常见的距离度量
- **$L^\infty$（最大范数）**：$\|x\|_\infty = \max_i |x_i|$

### 算子范数（诱导范数）

矩阵 $A$ 在给定向量范数下的算子范数：

$$\|A\| = \sup_{x \neq 0} \frac{\|Ax\|}{\|x\|}$$

- $\|A\|_2$（谱范数）$= \sigma_{\max}(A)$（最大奇异值）
- $\|A\|_1 = \max_j \sum_i |A_{ij}|$（列绝对值和的最大值）
- $\|A\|_\infty = \max_i \sum_j |A_{ij}|$（行绝对值和的最大值）

### Frobenius 范数

$$\|A\|_F = \sqrt{\text{tr}(A^T A)} = \sqrt{\sum_{i,j} |A_{ij}|^2}$$

等价于将矩阵展平为向量后取 $L^2$ 范数。注意 Frobenius 范数**不是**算子范数。

### 范数等价性

在有限维空间 $\mathbb{R}^n$ 中，任意两个范数 $\|\cdot\|_a$ 和 $\|\cdot\|_b$ 拓扑等价：

$$c_1 \|x\|_a \leq \|x\|_b \leq c_2 \|x\|_a$$

常数 $c_1, c_2$ 依赖于维度 $n$。这意味着有限维中范数的选择不影响收敛性，但影响收敛速度和优化行为。

## 关联概念

- [[eigendecomposition]] — 谱范数等于最大奇异值，与特征值直接相关
- [[functional-spaces]] — 无穷维空间中范数等价性不再成立
- [[regularisation]] — $L^1$ / $L^2$ 范数在正则化中控制模型复杂度
