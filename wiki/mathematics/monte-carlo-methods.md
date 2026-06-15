---
summary: 蒙特卡洛方法族：基本 MC 积分、重要性采样、MCMC（Metropolis-Hastings、Gibbs）、序贯 MC 与粒子滤波。
tags: [mathematics, probability, monte-carlo]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inference-monte-carlo.md
---
# 蒙特卡洛方法

## 定义

蒙特卡洛方法利用随机采样近似计算积分、期望或复杂分布。当解析解不可得或维度过高时，MC 方法往往是唯一可行的途径。

## 关键点

### 基本蒙特卡洛积分

$$I = \int f(x)\, p(x)\, dx \approx \frac{1}{N}\sum_{i=1}^{N} f(x^{(i)}), \quad x^{(i)} \sim p$$

- 无偏估计，方差 $\text{Var}(f)/N$，收敛速率 $O(1/\sqrt{N})$，与维度无关。

### 重要性采样 (Importance Sampling)

当无法直接从 $p$ 采样，或 $p$ 下方差过大时，从提议分布 $q$ 采样：

$$I = \int f(x)\frac{p(x)}{q(x)} q(x)\, dx \approx \frac{1}{N}\sum_{i=1}^{N} f(x^{(i)})\frac{p(x^{(i)})}{q(x^{(i)})}, \quad x^{(i)} \sim q$$

- 权重 $w(x) = p(x)/q(x)$。
- **最优提议**：$q^*(x) \propto |f(x)|\, p(x)$，此时方差最小。
- $q$ 的支撑必须覆盖 $p$ 的支撑。

### MCMC：Metropolis-Hastings

构造以目标分布 $\pi$ 为平稳分布的 Markov 链：

1. 从当前状态 $x$ 按提议分布 $q(y|x)$ 生成候选 $y$。
2. 以概率 $\alpha = \min\!\left(1,\; \frac{\pi(y)\, q(x|y)}{\pi(x)\, q(y|x)}\right)$ 接受 $y$；否则留在 $x$。

- 只需知道 $\pi$ 的未归一化形式（归一化常数抵消）。
- 需要 burn-in 期，且连续样本有相关性。
- 当 $q$ 对称时（$q(y|x) = q(x|y)$）退化为 Metropolis 算法。

### MCMC：Gibbs 采样

多维分布的特殊 MCMC 方法，轮流从每个变量的条件分布采样：

$$x_i^{(t+1)} \sim p(x_i \mid x_1^{(t+1)}, \ldots, x_{i-1}^{(t+1)}, x_{i+1}^{(t)}, \ldots, x_d^{(t)})$$

- 无需设计提议分布，接受率恒为 1。
- 前提：所有全条件分布 $p(x_i | x_{-i})$ 可采样。
- 高维强相关变量时混合可能很慢。

### 序贯蒙特卡洛 / 粒子滤波

针对一系列逐步变化的目标分布 $\pi_1, \pi_2, \ldots, \pi_T$：

- 维护一组带权重的粒子 $\{(x^{(i)}, w^{(i)})\}$。
- 每步通过重要性权重更新和重采样跟踪目标分布的演化。
- 粒子滤波是序贯 MC 在状态空间模型中的具体应用，用于在线贝叶斯滤波。

### 控制变量法 (Control Variates)

利用与目标量相关、且均值已知的辅助统计量 $Z$ 降低 MC 方差：

$$\hat\mu_{CV} = \hat\mu - c(Z - \mathbb{E}[Z])$$

最优 $c^* = \text{Cov}(\hat\mu, Z) / \text{Var}(Z)$，方差缩减因子 $1 - \rho^2$。

## 关联概念

- [[estimation-theory]] — MC 方法用于近似贝叶斯估计中的后验积分
- [[markov-chain]] — MCMC 基于 Markov 链的平稳分布理论
- [[gaussian-distribution]] — 高斯提议分布在 MH 和重要性采样中常用
