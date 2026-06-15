---
summary: ELBO（证据下界）是对数似然的下界，由 Jensen 不等式导出，是 EM 算法实际优化的目标。当提议分布等于真实后验时，下界紧。
tags: [machine-learning, probabilistic-models]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-expectation-maximisation-evidence-lower-bound-(elbo).md
  - raw/machine-learning/2026-06-08-expectation-maximisation-derivation-of-elbo.md
---

# 证据下界（ELBO）

## 定义

对含隐变量模型，引入任意分布 $q(z)$ 后，由 Jensen 不等式得：
$$\log p(x|\theta) \geq \sum_z q(z) \log \frac{p(x,z|\theta)}{q(z)} = \mathcal{F}(q, \theta)$$

数据集上的 ELBO：
$$\mathcal{F}(q,\theta) = \sum_{i=1}^{N} \mathbb{E}_{q_i}\left[\log \frac{p(x_i, z_i|\theta)}{q_i(z_i)}\right]$$

## 关键点

- 对数似然的精确分解：$\log p(x|\theta) = \mathcal{F}(q,\theta) + \mathrm{KL}(q(z) \| p(z|x,\theta))$
- 当 $q(z) = p(z|x,\theta)$（提议分布等于真实后验）时 KL 项为零，下界紧。
- ELBO 可分解为两部分：期望联合对数似然 + 熵 $H(q)$。
- 也称为自由能（free energy）。

## 关联概念

- [[expectation-maximisation]] — EM 的 M-step 实际最大化 ELBO
- [[variational-autoencoder]] — VAE 的损失函数基于 ELBO
