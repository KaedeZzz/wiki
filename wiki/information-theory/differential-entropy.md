---
summary: 微分熵 h(X)=∫f log(1/f) 是熵在连续分布上的对应；高斯在给定二阶矩下取最大微分熵 ½ log(2πeσ²)，这是"最大熵原理"最重要的一例。
tags: [information-theory, entropy, continuous]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-basics-differential-entropy.md
  - raw/information-theory/2026-07-06-basics-differential-entropy-of-gaussian.md
  - raw/information-theory/2026-07-06-basics-differential-entropy-of-multiple-rvs.md
  - raw/information-theory/2026-07-06-basics-maximum-differential-entropy-theorem.md
---

# 微分熵

## 定义

对连续随机变量 $X$ 且 PDF $f_X$（见 [[continuous-distributions]]），**微分熵**定义为：

$$h(X) = \int_{-\infty}^{\infty} f_X(u)\log\tfrac{1}{f_X(u)}\,du$$

**注意**：微分熵可以为负（例如极窄分布），也不是绝对量——它衡量 $X$ 相对于 $\text{Unif}[0,1]$ 基线（$h=0$）的不确定性。真正的绝对量是与参考分布的 KL（即 [[kl-divergence]]）。

## 关键点

### 高斯的微分熵

$X\sim\mathcal{N}(\mu,\sigma^2)$：

$$h(X) = \tfrac{1}{2}\log(2\pi e\,\sigma^2)$$

推导：把 $\log \phi(x)$ 拆成常数项 $-\log\sqrt{2\pi\sigma^2}$ 和二次项 $-\tfrac{(x-\mu)^2}{2\sigma^2}$，二次项的期望是方差比 $\tfrac{1}{2}$，最后合成 $\tfrac{1}{2}\log 2\pi e\sigma^2$。仅与 $\sigma^2$ 有关（与均值无关，因熵是平移不变的）。

### 最大微分熵定理

在**功率约束** $\mathbb{E}[X^2] \leq P$ 下，最大微分熵由**零均值高斯** $X\sim\mathcal{N}(0,P)$ 达到：

$$h_{\max} = \tfrac{1}{2}\log(2\pi e P)$$

推广：给定协方差矩阵 $\Sigma$ 的所有分布中，多元高斯 $\mathcal{N}(0,\Sigma)$ 熵最大，$h = \tfrac{1}{2}\log((2\pi e)^n\det\Sigma)$。这个结论支撑：
- [[channel-capacity]] 中 Shannon-Hartley 定理的推导（AWGN 通道最优输入是高斯）
- [[statistical-mechanics]] 中"最大熵原理"的经典对应
- 变分推断里选高斯变分族的合理性（[[variational-autoencoder]]）

### 联合与条件（连续）

$$h(X,Y) = \iint f_{XY}(u,v)\log\tfrac{1}{f_{XY}(u,v)}\,du\,dv$$

$$h(X|Y) = \iint f_{XY}(u,v)\log\tfrac{1}{f_{X|Y}(u|v)}\,du\,dv$$

[[joint-conditional-entropy]] 的链式法则、[[mutual-information]] 的定义在连续情形完全平行。

## 关联概念

- [[information-entropy]] — 离散版本
- [[gaussian-distribution]] — 二阶矩约束下的最大熵分布
- [[continuous-distributions]] — 连续 PDF 的一般背景
- [[statistical-mechanics]] — 物理最大熵原理
- [[channel-capacity]] — Shannon-Hartley 中 AWGN 最优输入为高斯
- [[kl-divergence]] — 用 KL 才能得到绝对的、平移/尺度不变的信息距离
- [[variational-autoencoder]] — 潜变量用高斯的一部分动机
