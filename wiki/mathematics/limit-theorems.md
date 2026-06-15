---
summary: 中心极限定理 (CLT) 与大数弱定律 (WLLN)，以及依概率收敛与依分布收敛的定义。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics-limit-theorems.md
---
# 极限定理

## 定义

极限定理刻画大量随机变量之和（或均值）在样本量趋于无穷时的渐近行为，是概率论与统计推断的理论基石。

## 关键点

### 收敛类型

- **依概率收敛**：$X_n \xrightarrow{P} X$ 当且仅当 $\forall \epsilon > 0,\; P(|X_n - X| > \epsilon) \to 0$。
- **依分布收敛**：$X_n \xrightarrow{d} X$ 当且仅当 $F_{X_n}(x) \to F_X(x)$ 在 $F_X$ 的所有连续点成立。
- 依概率收敛蕴含依分布收敛，反之不然。

### 大数弱定律 (WLLN)

设 $X_1, X_2, \ldots$ i.i.d.，$\mathbb{E}[X_i] = \mu$，$\text{Var}(X_i) = \sigma^2 < \infty$，则：

$$\bar{X}_n = \frac{1}{n}\sum_{i=1}^n X_i \xrightarrow{P} \mu \quad (n \to \infty)$$

**证明思路**（Chebyshev 不等式）：

$$P(|\bar{X}_n - \mu| > \epsilon) \leq \frac{\text{Var}(\bar{X}_n)}{\epsilon^2} = \frac{\sigma^2}{n\epsilon^2} \to 0$$

### 中心极限定理 (CLT)

设 $X_1, X_2, \ldots$ i.i.d.，$\mathbb{E}[X_i] = \mu$，$\text{Var}(X_i) = \sigma^2 \in (0, \infty)$，令 $S_n = \sum_{i=1}^n X_i$，则：

$$\frac{S_n - n\mu}{\sigma\sqrt{n}} \xrightarrow{d} \mathcal{N}(0,1)$$

- 无论 $X_i$ 的原始分布如何，标准化后的和收敛到标准正态。
- 这解释了高斯分布在自然界中的普遍性。

**证明思路**（MGF 方法）：

1. 计算 $Z_n = (S_n - n\mu)/(\sigma\sqrt{n})$ 的 MGF。
2. 对单个标准化变量的 MGF 做 Taylor 展开至二阶项。
3. 取 $n \to \infty$ 极限，得到 $M_{Z_n}(t) \to e^{t^2/2}$，即 $\mathcal{N}(0,1)$ 的 MGF。

### CLT 的实用意义

- 为大样本近似提供理论依据：$\bar{X}_n \approx \mathcal{N}(\mu, \sigma^2/n)$。
- 经验法则：$n \geq 30$ 时近似通常足够好（但取决于原始分布的偏度）。

## 关联概念

- [[expectation-and-moments]] — 均值和方差是 WLLN/CLT 的前提条件
- [[concentration-inequalities]] — Chebyshev 不等式用于证明 WLLN；更精细的集中不等式提供非渐近界
- [[gaussian-distribution]] — CLT 的极限分布
- [[generating-functions]] — MGF/特征函数是证明 CLT 的核心工具
