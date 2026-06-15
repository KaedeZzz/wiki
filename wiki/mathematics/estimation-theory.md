---
summary: 统计估计的核心框架：MLE、MAP、MMSE，以及偏差-方差权衡、分类器设计与贝叶斯决策。
tags: [mathematics, probability, estimation]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-estimation-basics.md
  - raw/mathematics/2026-06-09-probability-theory-estimation-bayesian.md
---
# 估计理论

## 定义

估计理论研究如何从观测数据 $\mathbf{x}$ 中推断未知参数 $\theta$ 的最优方法，核心问题是在不同准则下设计估计量 $\hat\theta(\mathbf{x})$。

## 关键点

### 最大似然估计 (MLE)

$$\hat\theta^{ML} = \arg\max_\theta f(\mathbf{x}|\theta)$$

- 不使用先验信息，仅基于似然函数。
- 渐近无偏、渐近有效（达到 Cramér-Rao 下界）。
- 实际中常最大化对数似然 $\log f(\mathbf{x}|\theta)$。

### 最大后验估计 (MAP)

$$\hat\theta^{MAP} = \arg\max_\theta f(\theta|\mathbf{x}) = \arg\max_\theta f(\mathbf{x}|\theta) f(\theta)$$

- 引入先验 $f(\theta)$，在后验模式处估计。
- 当先验为均匀分布时退化为 MLE。

### 最小均方误差估计 (MMSE)

$$\hat\theta^{MMSE} = \mathbb{E}[\theta|\mathbf{x}]$$

- 最小化期望平方误差 $\mathbb{E}[(\theta - \hat\theta)^2]$。
- 即后验均值，不一定等于后验模式 (MAP)。

### 估计量的性质

- **无偏性**：$\mathbb{E}[\hat\theta] = \theta$。
- **一致性**：无偏且 $\text{Var}(\hat\theta) \to 0$（$N \to \infty$）。
- **最小方差无偏 (MVU)**：在所有无偏估计量中方差最小。
- **偏差-方差分解**：$\text{MSE} = \text{Bias}^2 + \text{Var}$。有偏估计（如 MAP）可能通过降低方差获得更小 MSE。

### 代价函数与贝叶斯决策

- 一般代价函数 $C(\theta, \hat\theta)$，贝叶斯最优决策最小化期望代价：

$$\hat\theta^{Bayes} = \arg\min_{\hat\theta} \mathbb{E}[C(\theta, \hat\theta)|\mathbf{x}]$$

- 平方代价 → MMSE；绝对值代价 → 后验中位数；0-1 代价 → MAP。

### 分类器：生成式 vs 判别式

- **生成式**：建模联合分布 $p(\mathbf{x}, \omega)$（或等价地 $p(\mathbf{x}|\omega)p(\omega)$），通过 Bayes 定理得到后验。
- **判别式**：直接建模 $p(\omega|\mathbf{x})$，不关心数据生成过程。
- 生成式可处理缺失数据和异常检测；判别式通常在分类精度上更优。

### 隐变量

- 模型中存在未被观测的变量 $\mathbf{z}$（隐变量/潜变量）。
- 通过边缘化 $p(\mathbf{x}|\theta) = \int p(\mathbf{x}, \mathbf{z}|\theta) d\mathbf{z}$ 消除隐变量。
- 直接优化边缘似然通常困难，常用 EM 算法迭代求解。

## 关联概念

- [[probability-foundations]] — 条件概率、Bayes 定理是估计理论的基础
- [[gaussian-distribution]] — 高斯噪声下的估计有解析解
- [[linear-gaussian-model]] — 线性高斯模型中 MLE/MAP/MMSE 的具体形式
- [[expectation-maximisation]] — 处理隐变量的迭代估计算法
