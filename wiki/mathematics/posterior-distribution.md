---
summary: 后验分布通过贝叶斯定理将先验信念与似然函数结合，表达观测数据后对参数的更新认知。
tags: [mathematics, probability, bayesian]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inferenceposterior-distribution.md
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inferenceposterior-inference-of-linear-gaussian-model.md
---

# 后验分布

## 定义

给定观测 $\mathbf{x}$，参数 $\boldsymbol{\theta}$ 的后验分布为：

$$p(\boldsymbol{\theta}|\mathbf{x}) = \frac{p(\mathbf{x}|\boldsymbol{\theta}) \, p(\boldsymbol{\theta})}{p(\mathbf{x})}$$

其中 $p(\mathbf{x}|\boldsymbol{\theta})$ 为似然，$p(\boldsymbol{\theta})$ 为先验，$p(\mathbf{x})$ 为边缘似然。

## 关键点

### 正比形式

$$p(\boldsymbol{\theta}|\mathbf{x}) \propto p(\mathbf{x}|\boldsymbol{\theta}) \, p(\boldsymbol{\theta})$$

边缘似然：$p(\mathbf{x}) = \int p(\mathbf{x}|\boldsymbol{\theta}) p(\boldsymbol{\theta}) \, d\boldsymbol{\theta}$

### 先验的影响

- **弱先验**（diffuse）：后验主要由似然决定，接近 MLE
- **强先验**：后验受先验显著影响
- 当 $N \to \infty$ 时，贝叶斯解趋向 ML 解

### 线性高斯模型的后验

模型 $\mathbf{x} = \mathbf{G\theta} + \mathbf{e}$，$\mathbf{e} \sim \mathcal{N}(0, \sigma_e^2 I)$，先验 $\boldsymbol{\theta} \sim \mathcal{N}(\mathbf{m}_\theta, \mathbf{C}_\theta)$ 时，后验仍为高斯：

$$p(\boldsymbol{\theta}|\mathbf{x}) = \mathcal{N}(\boldsymbol{\theta}^{MAP}, \sigma_e^2 \boldsymbol{\Phi}^{-1})$$

其中 $\boldsymbol{\Phi} = \mathbf{G}^T\mathbf{G} + \sigma_e^2 \mathbf{C}_\theta^{-1}$。此时 MMSE = MAP = 后验均值。

## 关联概念

- [[probability-foundations]] — 贝叶斯定理
- [[estimation-theory]] — MLE、MAP、MMSE 均可从后验导出
- [[linear-gaussian-model]] — 线性高斯模型的完整后验推断
- [[gaussian-distribution]] — 高斯先验 + 高斯似然 → 高斯后验（共轭）
