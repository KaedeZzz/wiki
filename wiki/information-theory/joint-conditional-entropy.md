---
summary: 联合熵 H(X,Y) 和条件熵 H(Y|X) 度量多个变量的不确定性；链式法则 H(X,Y)=H(X)+H(Y|X) 是所有推导的基石；独立 ⇔ H(X,Y)=H(X)+H(Y)。
tags: [information-theory, entropy]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-basics-joint-and-conditional-entropy.md
  - raw/information-theory/2026-07-06-basics-chain-rule-of-joint-entropy.md
  - raw/information-theory/2026-07-06-basics-entropy-and-independence.md
  - raw/information-theory/2026-07-06-basics-correlation-and-entropy.md
---

# 联合熵与条件熵

## 定义

**联合熵**：

$$H(X,Y) = -\sum_{x,y} P_{XY}(x,y)\log P_{XY}(x,y)$$

**条件熵**："已知 $X$ 后 $Y$ 剩余的不确定性"

$$H(Y|X) = \sum_{x,y} P_{XY}(x,y)\log\tfrac{1}{P_{Y|X}(y|x)} = \sum_x P_X(x)\, H(Y|X=x)$$

## 关键点

### 链式法则

单步：

$$H(X,Y) = H(X) + H(Y|X)$$

多步（$n$ 个变量）：

$$H(X_1,\dots,X_n) = \sum_{i=1}^n H(X_i|X_{i-1},\dots,X_1)$$

这是 [[posterior-distribution]] 的概率链式法则在信息量层面的直接对应。

### 独立性刻画

$$H(X,Y) = H(X) + H(Y) \Leftrightarrow X \perp Y$$

实用意义：判独立时通过 [[random-vectors]] 的联合分布需检查所有 $(x,y)$；用熵只需三次标量计算。

### 熵 vs 相关系数

对 $(X,Y)$ 之间关系的度量有两种视角：

- **相关系数**（$\text{Cov}$、$\rho$，见 [[expectation-and-moments]]）：从数据直接算，但**只捕捉线性关系**，非线性变换会掩盖。
- **条件熵/互信息**：捕捉**任意关系**，对分布变换稳健，但需要**完整分布**（数据稀疏时估计困难）。

工程实践里 correlation 是"快速廉价"，MI/entropy 是"细致昂贵"。

## 关联概念

- [[information-entropy]] — 基础定义
- [[mutual-information]] — $I(X;Y) = H(X) - H(X|Y)$，正是条件熵下降量
- [[posterior-distribution]] — 概率链式法则的信息版本
- [[differential-entropy]] — 连续情形；链式法则同样成立
- [[expectation-and-moments]] — 相关系数作为对偶度量
