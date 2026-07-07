---
summary: AEP 是弱大数定律在信息论中的对应——i.i.d. 序列的负对数概率 -1/n log P(X^n) 依概率收敛到 H(X)；由此定义典型集，其大小约为 2^{nH}，是无损压缩与信道编码所有渐近结果的基石。
tags: [information-theory, asymptotic, aep]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-typicality-asymptotic-equipartition-property-(aep).md
  - raw/information-theory/2026-07-06-typicality-typical-set.md
  - raw/information-theory/2026-07-06-typicality-properties-of-the-typical-set.md
  - raw/information-theory/2026-07-06-typicality-weak-&-strong-typicality.md
  - raw/information-theory/2026-07-06-typicality-jointly-typical.md
  - raw/information-theory/2026-07-06-typicality-joint-aep.md
---

# 典型性与 AEP

## 定义

**渐近均分性质（Asymptotic Equipartition Property）**：$X_1,X_2,\dots$ i.i.d. $\sim P_X$，对任意 $\epsilon>0$：

$$\lim_{n\to\infty}\Pr\left(\left|-\tfrac{1}{n}\log P_X(X_1,\dots,X_n) - H(X)\right| < \epsilon\right) = 1$$

即 $-\tfrac{1}{n}\log P(X^n) \xrightarrow{p} H(X)$。这是 [[limit-theorems]] 中弱大数定律的直接推论：令 $Y_i = -\log P_X(X_i)$，则 $\mathbb{E}[Y] = H(X)$ 且 $\tfrac{1}{n}\sum Y_i \to H(X)$。

## 关键点

### 典型集

$\epsilon$-**弱典型集**：

$$A_{\epsilon,n} = \{x^n : 2^{-n(H(X)+\epsilon)} < P(x^n) < 2^{-n(H(X)-\epsilon)}\}$$

即概率"聚集在 $2^{-nH}$ 附近"的序列。

### 三个基本性质

1. $\Pr(X^n \in A_{\epsilon,n}) \to 1$（几乎所有采样都是典型的）
2. $|A_{\epsilon,n}| \leq 2^{n(H(X)+\epsilon)}$（典型集**小**）
3. 对充分大 $n$：$|A_{\epsilon,n}| \geq (1-\epsilon)\,2^{n(H(X)-\epsilon)}$（也**不太小**）

综合：$|A_{\epsilon,n}| \approx 2^{nH(X)}$。这解释了熵作为压缩下界（[[source-coding]]）的直觉：只需给每个典型序列分配 $nH$ 比特。

### 弱典型 vs 强典型

- **弱典型**：只要求 $-\tfrac{1}{n}\log P(x^n)\approx H$（"分布对数值对"）
- **强典型**：要求**每个符号的经验频率**接近其真实概率，如 $\tfrac{n_0}{n}\approx P_X(0)$

**反例**：对 $\text{Bernoulli}(0.5)$ 序列，$H=1$，所有 $2^n$ 长度-$n$ 序列都是弱典型的（无法压缩）；强典型集则严格更小。

### 联合典型集与联合 AEP

对 $(X^n,Y^n)$ i.i.d. $\sim P_{XY}$：

$$A_{\epsilon,n}^{(XY)} = \left\{(x^n,y^n) : \Big|-\tfrac{1}{n}\log P_X(x^n) - H(X)\Big|<\epsilon,\ \dots\ P_Y,\ P_{XY}\right\}$$

**联合 AEP 关键推论**：设 $(\tilde X^n,\tilde Y^n)$ 独立采样自 $P_X\otimes P_Y$（即两个 marginal 的乘积，而**不是**联合分布），则

$$\Pr\!\left((\tilde X^n,\tilde Y^n)\in A_{\epsilon,n}^{(XY)}\right) \leq 2^{-n(I(X;Y)-3\epsilon)}$$

*"独立生成的序列偶然联合典型的概率呈指数衰减，指数率为互信息"*——这是 [[channel-coding]] 可达性证明中的核心估计。

## 关联概念

- [[information-entropy]] — 典型集大小的指数即 $H$
- [[mutual-information]] — 联合 AEP 里的指数即 $I(X;Y)$
- [[limit-theorems]] — AEP 就是弱大数定律的信息论面孔
- [[concentration-inequalities]] — 提供强典型集的更强收敛（Chebyshev/Chernoff 版本）
- [[source-coding]] — 使用典型集直接给出 $H+\epsilon$ 比特的压缩方案
- [[channel-coding]] — 联合典型解码是可达性证明的核心
