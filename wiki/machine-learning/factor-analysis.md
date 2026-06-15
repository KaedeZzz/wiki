---
summary: 因子分析是一种连续隐变量生成模型，将高维观测建模为低维隐变量的线性变换加独立噪声，当噪声为各向同性时退化为概率 PCA。
tags: [machine-learning, probabilistic-models, dimensionality-reduction]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-factor-analysis.md
  - raw/machine-learning/2026-06-08-basics-concepts-latent-variable-generative-models.md
  - raw/machine-learning/2026-06-08-basics-concepts-generative-models.md
---

# 因子分析

## 定义

观测 $x$ 由低维隐变量 $z$ 通过线性变换加噪声生成：
$$p(z) = \mathcal{N}(0, I), \quad p(x|z) = \mathcal{N}(Cz, \Sigma_{\text{diag}})$$
其中 $C$ 是载荷矩阵，$\Sigma_{\text{diag}}$ 是对角噪声协方差。

## 关键点

- 边缘分布有闭式解：$p(x) = \mathcal{N}(0, CC^T + \Sigma_{\text{diag}})$。
- 当 $\Sigma_{\text{diag}} = \sigma^2 I$ 时，即为概率 PCA。
- 属于隐变量生成模型（latent variable generative model）家族：贝叶斯网络中隐变量 $z$ 生成观测 $x$。

## 关联概念

- [[autoencoder]] — 非线性的编码-解码降维框架
- [[gaussian-mixture-model]] — 另一种隐变量模型（离散隐变量）
- [[graphical-model]] — 因子分析的图模型表示
