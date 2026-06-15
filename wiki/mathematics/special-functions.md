---
summary: 特殊函数包括 Gamma 函数、Beta 函数、Stirling 近似和 Gauss 积分等，是概率论与组合数学中的基本分析工具。
tags: [mathematics, special-functions]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-misc-special-functions.md
---

# 特殊函数

## 定义

特殊函数（Special Functions）是在数学分析、概率论和数学物理中反复出现的一类具有特殊性质的函数，通常由积分或递推关系定义。

## 关键点

### Stirling 近似

$$n! \approx \sqrt{2\pi n}\left(\frac{n}{e}\right)^n$$

更精确的形式：

$$n! = \sqrt{2\pi n}\left(\frac{n}{e}\right)^n \left(1 + \frac{1}{12n} + O(n^{-2})\right)$$

应用：简化含阶乘的渐近分析（如二项式系数的估计）。

### Gamma 函数

$$\Gamma(z) = \int_0^\infty t^{z-1} e^{-t} \, dt, \quad \text{Re}(z) > 0$$

关键性质：
- $\Gamma(n) = (n-1)!$（正整数）
- 递推关系：$\Gamma(z+1) = z\Gamma(z)$
- $\Gamma(1/2) = \sqrt{\pi}$
- 与 Stirling 近似的联系：$\Gamma(n+1) = n! \approx \sqrt{2\pi n}(n/e)^n$

### Beta 函数

$$B(a, b) = \int_0^1 t^{a-1}(1-t)^{b-1} \, dt = \frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}$$

Beta 分布的归一化常数即为 $B(a,b)$。

### Gauss 积分

$$\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}$$

推广形式：

$$\int_{-\infty}^{\infty} e^{-ax^2+bx} \, dx = \sqrt{\frac{\pi}{a}} \, e^{b^2/(4a)}, \quad a > 0$$

这是 Gauss 分布归一化和矩计算的基础。

## 关联概念

- [[discrete-distributions]] — 二项式系数通过 Gamma/Beta 函数表达
- [[continuous-distributions]] — Gamma 分布、Beta 分布直接以同名函数为参数
- [[gaussian-distribution]] — Gauss 积分是正态分布归一化的核心
