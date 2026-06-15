---
summary: 随机向量将多个随机变量组合为向量，通过联合 PDF、边缘分布和变量变换进行分析。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basicsrandom-vectors.md
  - raw/mathematics/2026-06-09-probability-theory-miscsum-of-random-variables.md
  - raw/mathematics/2026-06-09-probability-theory-basicsrandom-sum-of-distributions.md
---

# 随机向量

## 定义

$n$ 个随机变量 $X_1, \dots, X_n$ 组成随机向量 $\mathbf{X} = (X_1, \dots, X_n) \in \mathbb{R}^n$。

联合 PDF：

$$P(X_1 \in A_1, \dots, X_n \in A_n) = \int \cdots \int f(x_1, \dots, x_n) \, dx_1 \cdots dx_n$$

## 关键点

### 边缘分布

$$f_{X_i}(x_i) = \int \cdots \int f(x_1, \dots, x_n) \, dx_1 \cdots dx_{i-1} \, dx_{i+1} \cdots dx_n$$

### 独立性

$$f(x_1, \dots, x_n) = f_{X_1}(x_1) \cdots f_{X_n}(x_n)$$

### 变量变换

若 $\mathbf{Y} = G(\mathbf{X})$ 且 $G$ 可逆，则利用 Jacobian 行列式。对标量 $Y = r(X)$：

$$f_Y(y) = f_X(r^{-1}(y)) \left|\frac{d}{dy} r^{-1}(y)\right|$$

### 随机变量之和

独立 $X, Y$ 之和的 PDF 为卷积：$f_S(s) = \int f_X(k) f_Y(s-k) \, dk$

### 随机个数求和

$S = \sum_{i=1}^N X_i$（$N$ 为随机整数，$X_i$ i.i.d.）的生成函数：$G_S(z) = G_N(G_X(z))$

## 关联概念

- [[probability-foundations]] — 随机变量的基本定义
- [[expectation-and-moments]] — 向量的期望与协方差矩阵
- [[gaussian-distribution]] — 多维高斯是最重要的连续随机向量分布
- [[calculus]] — Jacobian 行列式在变量变换中的作用
