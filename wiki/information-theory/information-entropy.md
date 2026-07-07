---
summary: 信息熵 H(X)=E[-log P(X)] 度量随机变量的不确定性，取值范围 [0, log|X|]（均匀分布取最大），是无损压缩的下界，也是所有信息量度（联合/条件/互信息/KL）的基础。
tags: [information-theory, entropy]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-information-content.md
  - raw/information-theory/2026-07-06-basics-information-entropy.md
  - raw/information-theory/2026-07-06-basics-binary-entropy-function.md
  - raw/information-theory/2026-07-06-basics-properties-of-information-entropy.md
  - raw/information-theory/2026-07-06-basics-entropy-of-functions.md
  - raw/information-theory/2026-07-06-basics-perplexity.md
  - raw/information-theory/2026-07-06-basics-differentiating-entropy.md
---

# 信息熵

## 定义

**信息内容**（自信息）：单次事件 $x$ 的"惊奇度"

$$I_X(x) = -\log_2 P_X(x)$$

**信息熵**是信息内容的期望，单位为比特：

$$\mathbb{H}[X] = \mathbb{E}[I_X(X)] = -\sum_{x\in\mathcal{X}} P_X(x)\log_2 P_X(x)$$

*"从观察 $X$ 的取值中期望获得多少信息"*，也等价于对 $X$ 的**不确定性**的度量。

## 关键点

### 二元熵函数

$X\sim\text{Bernoulli}(p)$（见 [[discrete-distributions]]）时：

$$\mathcal{H}_2(p) = p\log_2\tfrac{1}{p} + (1-p)\log_2\tfrac{1}{1-p}$$

在 $p=1/2$ 达到最大 $1$ bit。

### 基本性质

1. **非负**：$H(X)\geq 0$（因为 $P\leq 1$）。
2. **上界为字母表对数**：$H(X)\leq \log|\mathcal{X}|$，等号当且仅当 $X$ **均匀分布**。

上界证明用 $\ln x \leq x-1$：

$$H(X)-\log M = \tfrac{1}{\ln 2}\sum_x P(x)\ln\tfrac{1}{MP(x)} \leq \tfrac{1}{\ln 2}\sum_x P(x)\left(\tfrac{1}{MP(x)}-1\right) = 0$$

均匀分布使熵最大化 → 与 [[statistical-mechanics]] 的**最大熵**原理一致。

3. **函数不增熵**：$H(g(X))\leq H(X)$（确定性映射不能新增信息；这也是 [[mutual-information]] 数据处理不等式的雏形）。

### Perplexity

$$PP(p) := 2^{H(p)}$$

可解释为"等价的均匀分布字母表大小"——语言模型评估的常见指标（越低越好）。

### 求导技巧

对熵求导时（用于最大熵、Lagrangian 等），先将 $\log_2$ 换为 $\ln$：$\log_2 x = \ln x / \ln 2$，避免链式法则里的常数因子出错。

## 关联概念

- [[joint-conditional-entropy]] — 多变量情形与条件熵
- [[mutual-information]] — 两个随机变量的信息共享
- [[kl-divergence]] — 熵是 KL 的一种极限；交叉熵 = 熵 + KL
- [[differential-entropy]] — 连续版本
- [[source-coding]] — 熵是无损压缩的**下界**
- [[typicality-and-aep]] — 熵通过 AEP 与"典型序列"的数量挂钩：$|A_\epsilon|\approx 2^{nH}$
- [[statistical-mechanics]] — 物理熵与 Boltzmann 分布：均匀分布最大熵原理的物理对应
- [[discrete-distributions]] — Bernoulli 及其他离散分布
- [[zipfs-law]] — 语言符号分布的熵接近 $\log|\mathcal{X}|$ 的上界
