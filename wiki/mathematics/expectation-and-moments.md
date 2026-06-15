---
summary: 期望与矩涵盖期望、方差、协方差、相关系数、全期望公式（塔式法则）及随机变量变换，是概率计算的核心工具。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics.md
---

# 期望与矩

## 定义

期望（Expectation）是随机变量取值的概率加权平均，矩（Moment）是期望的推广形式，用于刻画分布的位置、散布和形状。

## 关键点

### 期望

$$\mathbb{E}[X] = \int_{-\infty}^{\infty} x \, f_X(x) \, dx \quad \text{（连续型）}$$

$$\mathbb{E}[X] = \sum_i x_i \, P(X = x_i) \quad \text{（离散型）}$$

线性性：$\mathbb{E}[aX + bY] = a\mathbb{E}[X] + b\mathbb{E}[Y]$（无需独立性）。

### 方差

$$\text{Var}[X] = \mathbb{E}[(X - \mathbb{E}[X])^2] = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$$

- $\text{Var}[aX + b] = a^2 \text{Var}[X]$
- 独立时：$\text{Var}[X + Y] = \text{Var}[X] + \text{Var}[Y]$

### 协方差与相关系数

$$\text{Cov}(X, Y) = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]$$

$$\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sqrt{\text{Var}[X] \cdot \text{Var}[Y]}}, \quad -1 \leq \rho \leq 1$$

独立 $\Rightarrow$ 不相关（$\text{Cov} = 0$），但反之不一定成立。

### 全期望公式（塔式法则）

$$\mathbb{E}[Y] = \mathbb{E}\left[\mathbb{E}[Y | X]\right]$$

类似地，全方差公式：

$$\text{Var}[Y] = \mathbb{E}[\text{Var}[Y|X]] + \text{Var}[\mathbb{E}[Y|X]]$$

### 独立随机变量的期望

若 $X \perp Y$：

$$\mathbb{E}[XY] = \mathbb{E}[X] \cdot \mathbb{E}[Y]$$

### 随机变量变换

若 $Y = r(X)$ 且 $r$ 单调可逆：

$$f_Y(y) = f_X(r^{-1}(y)) \left|\frac{dr^{-1}}{dy}\right|$$

多元情形使用 Jacobian 行列式的绝对值。

### 独立随机变量之和

若 $X \perp Y$，则 $Z = X + Y$ 的 PDF 为卷积：

$$f_Z(z) = (f_X * f_Y)(z) = \int_{-\infty}^{\infty} f_X(t) \, f_Y(z - t) \, dt$$

## 关联概念

- [[probability-foundations]] — 期望与矩的定义建立在概率空间和分布函数之上
- [[concentration-inequalities]] — 利用矩信息（期望、方差）给出概率尾界
- [[generating-functions]] — 矩母函数和特征函数系统地编码所有矩
