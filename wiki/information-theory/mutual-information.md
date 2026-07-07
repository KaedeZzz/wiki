---
summary: 互信息 I(X;Y)=H(X)-H(X|Y)=D(P_XY‖P_X P_Y) 度量两个随机变量的信息共享；对称、非负、独立时为零。数据处理不等式与 Fano 不等式是通信/统计中最常用的两个推论。
tags: [information-theory, entropy]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-basics-mutual-information.md
  - raw/information-theory/2026-07-06-basics-properties-of-mutual-information.md
  - raw/information-theory/2026-07-06-basics-conditional-mutual-information.md
  - raw/information-theory/2026-07-06-basics-chain-rule-of-mutual-information.md
  - raw/information-theory/2026-07-06-basics-the-data-processing-inequality.md
  - raw/information-theory/2026-07-06-basics-fano's-inequality.md
  - raw/information-theory/2026-07-06-basics-proof-of-fano's-inequality.md
---

# 互信息

## 定义

$$I(X;Y) \equiv H(X) - H(X|Y) = H(Y) - H(Y|X) = H(X) + H(Y) - H(X,Y)$$

也可写为：

$$I(X;Y) = \sum_{x,y} P_{XY}(x,y)\log\frac{P_{XY}(x,y)}{P_X(x)P_Y(y)} = D_{KL}(P_{XY}\|P_X P_Y)$$

*"观察 $Y$ 后 $X$ 不确定性的减少量"*。

## 关键点

### 基本性质

1. **对称**：$I(X;Y) = I(Y;X)$
2. **非负**：$I(X;Y) \geq 0$，等号 ⇔ $X\perp Y$（由 [[kl-divergence]] 非负性）
3. **等于 KL**：$I(X;Y) = D(P_{XY}\|P_X P_Y)$（"联合与独立乘积的差距"）

### 条件互信息与链式法则

$$I(X;Y|Z) := H(X|Z) - H(X|Y,Z)$$

链式：

$$I(X_1,\dots,X_n;Y) = \sum_{i=1}^n I(X_i;Y|X_{i-1},\dots,X_1)$$

### 数据处理不等式

若 $X\to Y\to Z$ 构成 Markov 链（$Z$ 只通过 $Y$ 依赖于 $X$，见 [[markov-chain]]），则

$$I(X;Y) \geq I(X;Z)$$

*"处理 $Y$ 不能凭空增加关于 $X$ 的信息"*——这正当化了"预处理不改善贝叶斯风险"的直觉，也是 [[hidden-markov-model]] 中隐状态不可能通过下游观测被完全恢复的原因。

### Fano 不等式

考虑估计问题 $X\to Y\to \hat X = g(Y)$，误差概率 $P_e = \Pr(\hat X\neq X)$。对**任何**这样的估计器：

$$P_e \geq \frac{H(X|Y) - 1}{\log|\mathcal{X}|}$$

等价形式：$1 + P_e\log|\mathcal{X}| \geq H(X|\hat X) \geq H(X|Y)$。

**推导要点**：引入误差指示 $E=\mathbb{1}[\hat X\neq X]$，两次展开 $H(E,X|\hat X)$：

- $H(E|X,\hat X) = 0$（$E$ 是 $(X,\hat X)$ 的函数）
- $H(E|\hat X) \leq H_2(P_e) \leq 1$
- $H(X|\hat X, E) = P_e\cdot H(X|\hat X, E=1) \leq P_e\log|\mathcal{X}|$

Fano 是 **[[channel-coding]] 逆定理**的核心（连同 [[joint-conditional-entropy]] 的链式法则一起给出 $R\leq C$）。

## 关联概念

- [[information-entropy]] / [[joint-conditional-entropy]] — 定义所依赖的基础
- [[kl-divergence]] — $I$ 是特定形式的 KL
- [[channel-capacity]] — $C = \max_{P_X} I(X;Y)$
- [[channel-coding]] — Fano 不等式是逆向界的关键
- [[markov-chain]] — 数据处理不等式所依赖的结构
- [[hidden-markov-model]] — 隐状态推断本质上受数据处理不等式约束
- [[posterior-distribution]] — 贝叶斯推断的信息论视角
- [[variational-autoencoder]] — VAE 的编码器"信息瓶颈"部分用互信息刻画
