---
summary: 概率生成函数 (PGF)、矩生成函数 (MGF) 和特征函数的定义、性质及应用。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics-generating-functions.md
---
# 生成函数

## 定义

生成函数将随机变量的分布信息编码为一个函数，使得求矩、证明极限定理等操作转化为函数的代数运算。

## 关键点

### 概率生成函数 (PGF)

$$G_X(z) = \mathbb{E}[z^X] = \sum_{k=0}^{\infty} P(X=k)\, z^k$$

- 适用于**非负整数值**随机变量。
- $P(X=k) = \frac{G_X^{(k)}(0)}{k!}$，即 PGF 唯一确定分布。
- 阶乘矩：$\mathbb{E}[X(X-1)\cdots(X-k+1)] = G_X^{(k)}(1)$。

### 矩生成函数 (MGF)

$$M_X(t) = \mathbb{E}[e^{tX}]$$

- 若在 $t=0$ 的某邻域存在，则唯一确定分布。
- $k$ 阶矩：$\mathbb{E}[X^k] = M_X^{(k)}(0)$。
- 独立随机变量之和的 MGF 等于各自 MGF 的乘积。

### 特征函数

$$\phi_X(t) = \mathbb{E}[e^{itX}]$$

- **始终存在**（MGF 可能不存在，但特征函数总存在）。
- 唯一确定分布。
- 本质上是 PDF 的 Fourier 变换（符号差异取决于约定）。
- 反演公式可从特征函数恢复 PDF。

### 随机和

若 $S = X_1 + X_2 + \cdots + X_N$，$N$ 与 $X_i$ 独立，$X_i$ i.i.d.，则：

$$G_S(z) = G_N(G_X(z))$$

### 与变换的联系

| 生成函数 | 对应变换 |
|---------|---------|
| MGF $M_X(t)$ | 双边 Laplace 变换 $\mathcal{L}\{f\}(-t)$ |
| 特征函数 $\phi_X(t)$ | Fourier 变换 $\mathcal{F}\{f\}(t)$ |
| PGF $G_X(z)$ | Z 变换（离散情况） |

## 关联概念

- [[expectation-and-moments]] — 矩的定义；生成函数是计算矩的工具
- [[limit-theorems]] — CLT 的经典证明依赖 MGF / 特征函数
- [[discrete-distributions]] — PGF 主要用于离散分布
