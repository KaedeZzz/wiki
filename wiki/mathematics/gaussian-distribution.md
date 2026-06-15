---
summary: 高斯（正态）分布的一元与多元形式、核心性质（线性变换、边缘化、条件化）及采样方法。
tags: [mathematics, probability]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-basics.md
  - raw/mathematics/2026-06-09-probability-theory-distributions.md
  - raw/mathematics/2026-06-09-misc-gaussian.md
---
# 高斯分布

## 定义

高斯分布（正态分布）是概率论中最重要的连续分布，因中心极限定理而在自然界和工程中广泛出现。

### 一元高斯

$$f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\!\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$$

记作 $X \sim \mathcal{N}(\mu, \sigma^2)$。

### 多元高斯

$$f(\mathbf{x}) = |2\pi\Sigma|^{-1/2} \exp\!\left(-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^T \Sigma^{-1} (\mathbf{x}-\boldsymbol{\mu})\right)$$

记作 $\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \Sigma)$，其中 $\Sigma$ 为协方差矩阵（对称正定）。

## 关键点

### 线性变换封闭性

若 $\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \Sigma)$，则：

$$\mathbf{Y} = A\mathbf{X} + \mathbf{b} \sim \mathcal{N}(A\boldsymbol{\mu}+\mathbf{b},\; A\Sigma A^T)$$

### 边缘分布

联合高斯的任意子集的边缘分布仍为高斯——直接取对应的均值分量和协方差子矩阵即可。

### 条件分布

设 $\mathbf{x} = [\mathbf{x}_1, \mathbf{x}_2]^T$ 联合高斯，分块均值 $\boldsymbol{\mu}_1, \boldsymbol{\mu}_2$ 和协方差 $\Sigma_{11}, \Sigma_{12}, \Sigma_{21}, \Sigma_{22}$，则：

$$\mathbf{x}_1 | \mathbf{x}_2 \sim \mathcal{N}\!\left(\boldsymbol{\mu}_1 + \Sigma_{12}\Sigma_{22}^{-1}(\mathbf{x}_2 - \boldsymbol{\mu}_2),\; \Sigma_{11} - \Sigma_{12}\Sigma_{22}^{-1}\Sigma_{21}\right)$$

条件均值是 $\mathbf{x}_2$ 的仿射函数；条件协方差与 $\mathbf{x}_2$ 的取值无关。

### 采样

从 $\mathcal{N}(\boldsymbol{\mu}, \Sigma)$ 采样：

1. 对 $\Sigma$ 做 Cholesky 分解：$\Sigma = AA^T$。
2. 采样 $\mathbf{z} \sim \mathcal{N}(\mathbf{0}, I)$。
3. 令 $\mathbf{y} = A\mathbf{z} + \boldsymbol{\mu}$。

### 最大熵性质

在均值和方差给定的所有分布中，高斯分布具有**最大微分熵**。

### 独立性判定

对联合高斯随机变量，不相关 $\Leftrightarrow$ 独立（一般分布只有单向蕴含）。

## 关联概念

- [[continuous-distributions]] — 其他连续分布（指数、Beta、Rayleigh 等）
- [[expectation-and-moments]] — 期望与矩的一般理论
- [[gaussian-mixture-model]] — 高斯混合模型，用多个高斯分量建模复杂分布
- [[gaussian-process]] — 高斯过程，函数空间上的高斯分布
