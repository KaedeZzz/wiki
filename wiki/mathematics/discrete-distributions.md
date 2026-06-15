---
summary: 常见离散分布包括 Bernoulli、二项、几何、Poisson、多项和 Categorical 分布，是建模计数型随机现象的基本工具。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-distributions.md
---

# 离散分布

## 定义

离散分布（Discrete Distribution）是取值为可数集的随机变量所服从的概率分布，由概率质量函数（PMF）完全刻画。

## 关键点

### Bernoulli 分布

$$X \sim \text{Bernoulli}(p): \quad P(X=1) = p, \quad P(X=0) = 1-p$$

- $\mathbb{E}[X] = p$，$\text{Var}[X] = p(1-p)$
- 单次二值试验的模型

### 二项分布

$$X \sim \text{Binomial}(n, p): \quad P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$$

- $\mathbb{E}[X] = np$，$\text{Var}[X] = np(1-p)$
- $n$ 次独立 Bernoulli 试验的成功次数之和

### 几何分布

$$X \sim \text{Geometric}(p): \quad P(X=k) = (1-p)^{k-1} p, \quad k = 1, 2, \ldots$$

- $\mathbb{E}[X] = 1/p$，$\text{Var}[X] = (1-p)/p^2$
- 首次成功所需的试验次数
- 唯一具有无记忆性的离散分布

### Poisson 分布

$$X \sim \text{Poisson}(\lambda): \quad P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \ldots$$

- $\mathbb{E}[X] = \lambda$，$\text{Var}[X] = \lambda$
- 固定时间/区域内稀有事件发生次数的模型

### 多项分布

$$\mathbf{X} \sim \text{Multinomial}(n, \mathbf{p}): \quad P(X_1=k_1, \ldots, X_K=k_K) = \frac{n!}{k_1! \cdots k_K!} p_1^{k_1} \cdots p_K^{k_K}$$

- 二项分布到 $K$ 个类别的推广
- 约束：$\sum_i k_i = n$，$\sum_i p_i = 1$

### Categorical 分布

单次试验（$n=1$）的多项分布，输出一个 $K$ 维 one-hot 向量。

### 近似关系

- **二项 → Poisson**：当 $n \to \infty$，$p \to 0$，$np \to \lambda$ 时，$\text{Binomial}(n,p) \to \text{Poisson}(\lambda)$
- **二项 → 正态**：当 $n$ 足够大时，$\text{Binomial}(n,p) \approx \mathcal{N}(np, np(1-p))$（中心极限定理）

## 关联概念

- [[probability-foundations]] — 离散分布由 PMF 定义，基于概率空间
- [[continuous-distributions]] — 连续型对应物（如 Poisson 过程与指数分布的关系）
- [[generating-functions]] — 矩母函数和概率母函数用于推导分布性质
