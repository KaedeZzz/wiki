---
summary: 收敛的多种模式：逐点收敛、一致收敛、上极限/下极限，及它们之间的关系。
tags: [mathematics, analysis]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-analysis-convergence.md
  - raw/mathematics/2026-06-09-analysis-sequences.md
  - raw/mathematics/2026-06-09-analysis-limits.md
---
# 收敛

## 定义

收敛描述序列或函数列趋近某个极限的行为。不同的收敛模式对"趋近"的要求强弱不同。

## 关键点

### 逐点收敛 (Pointwise Convergence)

函数列 $\{f_n\}$ 逐点收敛到 $f$，若对每个 $x$：

$$\lim_{n \to \infty} f_n(x) = f(x)$$

即：对每个固定的 $x$ 和 $\varepsilon > 0$，存在 $N(x, \varepsilon)$ 使得 $n > N \Rightarrow |f_n(x) - f(x)| < \varepsilon$。注意 $N$ 可以依赖于 $x$。

### 一致收敛 (Uniform Convergence)

$$\sup_x |f_n(x) - f(x)| \to 0 \quad (n \to \infty)$$

即：存在统一的 $N(\varepsilon)$（不依赖 $x$）使得所有 $x$ 同时满足 $|f_n(x) - f(x)| < \varepsilon$。

**一致收敛严格强于逐点收敛。** 一致收敛保持连续性：若每个 $f_n$ 连续且 $f_n \rightrightarrows f$，则 $f$ 连续。逐点收敛不保证这一点。

### 上极限与下极限

对实数序列 $\{a_n\}$：

- **上极限**：$\limsup_{n \to \infty} a_n = \lim_{n \to \infty} \sup_{k \geq n} a_k$
- **下极限**：$\liminf_{n \to \infty} a_n = \lim_{n \to \infty} \inf_{k \geq n} a_k$

性质：
- $\liminf a_n \leq \limsup a_n$，恒成立。
- $\lim a_n$ 存在 $\iff$ $\liminf a_n = \limsup a_n$，此时三者相等。
- 上极限是序列的"最大聚点"，下极限是"最小聚点"。

### 其他收敛模式（概率论中）

- **依概率收敛**：$P(|X_n - X| > \varepsilon) \to 0$。
- **几乎必然收敛**：$P(\lim X_n = X) = 1$。
- **依分布收敛**：CDF 逐点收敛。
- 强度关系：几乎必然 → 依概率 → 依分布。

## 关联概念

- [[functional-spaces]] — 完备性即 Cauchy 序列在空间内收敛；一致收敛等价于 $L^\infty$ 范数下的收敛。
- [[limit-theorems]] — 大数定律和中心极限定理分别涉及几乎必然收敛和依分布收敛。
