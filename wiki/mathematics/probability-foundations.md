---
summary: 概率论基础涵盖概率空间、Kolmogorov 公理、随机变量、分布函数、条件概率、独立性与 Bayes 定理，是所有概率推理的出发点。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics.md
---

# 概率论基础

## 定义

概率论是研究随机现象数学规律的学科。其严格基础由 Kolmogorov 于 1933 年建立，以测度论为数学框架。

## 关键点

### 概率空间

概率空间是三元组 $(\Omega, \mathcal{F}, P)$：

- $\Omega$：样本空间（所有可能结果的集合）
- $\mathcal{F}$：事件 σ-代数（$\Omega$ 的子集族）
- $P$：概率测度，$P: \mathcal{F} \to [0,1]$

### Kolmogorov 公理

1. **非负性**：$P(A) \geq 0$
2. **归一性**：$P(\Omega) = 1$
3. **可数可加性**：对两两不相交事件 $\{A_i\}$，$P\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty P(A_i)$

### 随机变量

随机变量 $X: \Omega \to \mathbb{R}$ 是从样本空间到实数的可测函数。

### 分布函数

- **CDF**：$F_X(x) = P(X \leq x)$，右连续、单调不减、$F(-\infty)=0$、$F(+\infty)=1$
- **PDF**（连续型）：$f_X(x) \geq 0$，$\int_{-\infty}^{\infty} f_X(x)\,dx = 1$，$F_X(x) = \int_{-\infty}^x f_X(t)\,dt$
- **PMF**（离散型）：$P_X(x_i) = P(X = x_i)$，$\sum_i P_X(x_i) = 1$

### 条件概率与独立性

- **条件概率**：$P(A|B) = \frac{P(A \cap B)}{P(B)}$，$P(B) > 0$
- **独立性**：$P(X, Y) = P(X)P(Y)$，等价于 $P(X|Y) = P(X)$
- **条件独立**：$(X \perp Y \mid Z)$ 当且仅当 $P(X, Y | Z) = P(X|Z)P(Y|Z)$

### Bayes 定理

$$P(A|B) = \frac{P(B|A)\,P(A)}{P(B)}$$

全概率公式展开分母：$P(B) = \sum_i P(B|A_i)P(A_i)$。

## 关联概念

- [[expectation-and-moments]] — 基于分布函数定义期望与矩
- [[discrete-distributions]] — 常见离散型分布
- [[continuous-distributions]] — 常见连续型分布
