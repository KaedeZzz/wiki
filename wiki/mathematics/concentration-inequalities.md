---
summary: 集中不等式：Markov、Chebyshev、Chernoff 界及 union bound，用于约束随机变量偏离期望的概率。
tags: [mathematics, analysis, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-analysis-probability.md
  - raw/mathematics/2026-06-09-analysis-inequalities.md
  - raw/mathematics/2026-06-09-analysis-concentration.md
---
# 集中不等式

## 定义

集中不等式 (concentration inequalities) 给出随机变量偏离其期望值的概率上界。使用的信息越多（期望 → 方差 → 矩生成函数），界越紧。

## 关键点

### Markov 不等式

对非负随机变量 $X$ 和 $a > 0$：

$$P(X \geq a) \leq \frac{\mathbb{E}[X]}{a}$$

最弱但适用最广——只需要 $X \geq 0$ 和有限期望。

### Chebyshev 不等式

对有限方差的随机变量 $X$：

$$P(|X - \mu| \geq k\sigma) \leq \frac{1}{k^2}$$

其中 $\mu = \mathbb{E}[X]$，$\sigma^2 = \text{Var}(X)$。本质是对 $(X - \mu)^2$ 应用 Markov 不等式。

### Chernoff 界

对任意 $t > 0$：

$$P(X \geq a) = P(e^{tX} \geq e^{ta}) \leq \frac{\mathbb{E}[e^{tX}]}{e^{ta}} = \frac{M_X(t)}{e^{ta}}$$

其中 $M_X(t) = \mathbb{E}[e^{tX}]$ 是矩生成函数。对 $t$ 取最小值可得最紧的指数尾界。

对独立 Bernoulli 随机变量之和 $S_n = \sum X_i$，$\mu = \mathbb{E}[S_n]$：

$$P(S_n \geq (1+\delta)\mu) \leq \left(\frac{e^\delta}{(1+\delta)^{(1+\delta)}}\right)^\mu$$

### Union Bound (Boole 不等式)

$$P\left(\bigcup_{i=1}^n A_i\right) \leq \sum_{i=1}^n P(A_i)$$

简单但实用——常与 Chernoff 界组合：先对单个事件用 Chernoff 得指数界，再对所有事件用 union bound。

### 强度比较

$$\text{Markov（最弱）} \subset \text{Chebyshev} \subset \text{Chernoff（最强）}$$

信息需求递增：期望 → 方差 → 矩生成函数。

## 关联概念

- [[expectation-and-moments]] — 集中不等式的输入；矩越高阶，界越紧。
- [[limit-theorems]] — 集中不等式是有限样本版本，大数定律是渐近版本。
- [[generating-functions]] — Chernoff 界直接使用矩生成函数。
