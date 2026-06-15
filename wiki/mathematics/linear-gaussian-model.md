---
summary: 线性高斯模型 (GLM) 下的 OLS、ML、MAP、MMSE 估计及后验推断的完整推导。
tags: [mathematics, probability, linear-models]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-estimation-linear-gaussian.md
---
# 线性高斯模型

## 定义

线性高斯模型（General Linear Model, GLM）假设观测值是参数的线性函数加高斯噪声：

$$\mathbf{x} = \mathbf{G}\boldsymbol{\theta} + \mathbf{e}, \quad \mathbf{e} \sim \mathcal{N}(\mathbf{0}, \sigma_e^2 \mathbf{I})$$

其中 $\mathbf{G}$ 为设计矩阵（$N \times p$），$\boldsymbol{\theta}$ 为待估参数。

## 关键点

### OLS 估计

最小化残差平方和 $\|\mathbf{x} - \mathbf{G}\boldsymbol{\theta}\|^2$：

$$\hat{\boldsymbol{\theta}}^{OLS} = (\mathbf{G}^T\mathbf{G})^{-1}\mathbf{G}^T\mathbf{x}$$

### ML 估计

当 $\mathbf{e} \sim \mathcal{N}(\mathbf{0}, \sigma_e^2 \mathbf{I})$ 时，最大化似然等价于最小化平方误差：

$$\hat{\boldsymbol{\theta}}^{ML} = \hat{\boldsymbol{\theta}}^{OLS}$$

### MAP 估计（高斯先验）

设先验 $\boldsymbol{\theta} \sim \mathcal{N}(\mathbf{m}_\theta, \mathbf{C}_\theta)$，则：

$$\hat{\boldsymbol{\theta}}^{MAP} = \left(\mathbf{G}^T\mathbf{G} + \sigma_e^2 \mathbf{C}_\theta^{-1}\right)^{-1} \left(\mathbf{G}^T\mathbf{x} + \sigma_e^2 \mathbf{C}_\theta^{-1}\mathbf{m}_\theta\right)$$

- 等价于带 $L_2$ 正则化的回归（Ridge regression），正则项 $\sigma_e^2 \mathbf{C}_\theta^{-1}$ 来自先验。
- 当 $\mathbf{C}_\theta \to \infty \mathbf{I}$（先验趋于扩散），MAP → ML。

### 后验分布

在高斯先验+高斯似然下，后验也是高斯的：

$$p(\boldsymbol{\theta}|\mathbf{x}) = \mathcal{N}\!\left(\hat{\boldsymbol{\theta}}^{MAP},\; \sigma_e^2 \boldsymbol{\Phi}^{-1}\right)$$

其中 $\boldsymbol{\Phi} = \mathbf{G}^T\mathbf{G} + \sigma_e^2 \mathbf{C}_\theta^{-1}$。

- 因后验为高斯，MAP = 后验均值 = MMSE。

### 多项式回归

多项式回归是 GLM 的特例：取基函数 $g_k(t) = t^k$，设计矩阵 $G_{ij} = t_i^j$。

- 高阶多项式易过拟合 → 先验（正则化）的作用在此尤为重要。

### 控制变量法 (Control Variates)

在蒙特卡洛估计中，若存在与目标量相关且均值已知的辅助统计量 $Z$，可构造：

$$\hat\mu_{CV} = \hat\mu - c(Z - \mathbb{E}[Z])$$

最优系数 $c^* = \text{Cov}(\hat\mu, Z)/\text{Var}(Z)$，方差缩减比例为 $1 - \rho^2$（$\rho$ 为相关系数）。此技术与线性高斯模型中的条件化公式结构一致。

## 关联概念

- [[estimation-theory]] — MLE/MAP/MMSE 的一般框架
- [[gaussian-distribution]] — 高斯条件化公式是后验推导的基础
- [[matrix-decomposition]] — OLS 求解涉及矩阵求逆，实践中用 QR/SVD 分解
- [[regularisation]] — MAP 估计与正则化的等价关系
