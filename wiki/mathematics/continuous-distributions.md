---
summary: 常见连续概率分布（指数、Beta、Dirichlet、Rayleigh、均匀）的定义与性质。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics.md
  - raw/mathematics/2026-06-09-probability-theory-distributions.md
---
# 连续概率分布

## 定义

连续随机变量的概率分布由概率密度函数 (PDF) 描述，满足 $f(x) \geq 0$ 且 $\int f(x)dx = 1$。本页覆盖指数分布、Beta 分布、Dirichlet 分布、Rayleigh 分布和均匀分布。高斯分布见 [[gaussian-distribution]]。

## 关键点

### 指数分布 (Exponential)

$$f(x) = \lambda e^{-\lambda x}, \quad x \geq 0$$

- 均值 $1/\lambda$，方差 $1/\lambda^2$。
- **无记忆性**：$P(X > s+t \mid X > s) = P(X > t)$，是唯一具有无记忆性的连续分布。
- 常用于建模事件间隔时间（与 Poisson 过程对偶）。

### Beta 分布

$$f(x) = \frac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha,\beta)}, \quad x \in [0,1]$$

- $B(\alpha,\beta) = \frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+\beta)}$。
- 均值 $\frac{\alpha}{\alpha+\beta}$。
- 是 Bernoulli / 二项分布的**共轭先验**：若先验 $\theta \sim \text{Beta}(\alpha,\beta)$，观测 $k$ 次成功和 $n-k$ 次失败后，后验 $\theta | \text{data} \sim \text{Beta}(\alpha+k, \beta+n-k)$。
- $\alpha = \beta = 1$ 退化为均匀分布。

### Dirichlet 分布

$$f(\mathbf{x}) = \frac{\Gamma(\sum \alpha_i)}{\prod \Gamma(\alpha_i)} \prod_{i=1}^{K} x_i^{\alpha_i - 1}, \quad \sum x_i = 1$$

- Beta 分布的多元推广，定义在 $K$-维单纯形上。
- 是 Categorical / Multinomial 分布的共轭先验。
- 当所有 $\alpha_i = 1$ 时为单纯形上的均匀分布。

### Rayleigh 分布

$$f(r) = \frac{r}{\sigma^2} e^{-r^2/(2\sigma^2)}, \quad r \geq 0$$

- 若 $X, Y \sim \mathcal{N}(0, \sigma^2)$ 独立，则 $R = \sqrt{X^2 + Y^2} \sim \text{Rayleigh}(\sigma)$。
- 即**二维高斯向量模长**的分布。
- 均值 $\sigma\sqrt{\pi/2}$，众数 $\sigma$。

### 均匀分布 (Uniform)

$$f(x) = \frac{1}{b-a}, \quad x \in [a,b]$$

- 均值 $(a+b)/2$，方差 $(b-a)^2/12$。
- 最大熵分布（在给定支撑区间、无其他约束条件下）。

## 关联概念

- [[gaussian-distribution]] — 高斯分布单独成页；Rayleigh 分布是二维高斯模长
- [[discrete-distributions]] — 离散分布对应页；Beta/Dirichlet 分别是 Bernoulli/Categorical 的共轭先验
- [[probability-foundations]] — 概率论基础概念
