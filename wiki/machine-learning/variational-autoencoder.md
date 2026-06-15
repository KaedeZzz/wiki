---
summary: VAE 通过强制潜空间服从高斯分布来组织潜空间结构，使用 ELBO 作为损失函数（重建项 + KL 散度正则项），并通过重参数化技巧实现反向传播。
tags: [machine-learning, deep-learning, generative-model]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-variational-autoencoder.md
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-variational-bayes.md
---

# 变分自编码器（VAE）

## 定义

目标：从给定数据分布 $p(x)$ 生成新数据。引入潜分布 $p(z)$，假设 $p(z) \sim \mathcal{N}(0, I)$，用高斯 $q(z|x) = \mathcal{N}(\mu, \sigma)$ 近似后验 $p(z|x)$，其中 $\mu$ 和 $\sigma$ 由编码器学习。

## 关键点

**损失函数**（即 ELBO）：
$$\mathcal{L}(x) = \underbrace{L_2(x, x')}_{\text{重建}} + \underbrace{D_{KL}(\mathcal{N}(\mu, \sigma) \| \mathcal{N}(0, 1))}_{\text{潜空间正则}}$$
本质上是 EM！

**重参数化技巧**：直接从 $q(z|x)$ 采样无法反向传播。引入 $\epsilon \sim \mathcal{N}(0, 1)$，解码 $\mu + \sigma \cdot \epsilon$，使偏导对 $\mu$ 和 $\sigma$ 可计算。

**优势**：
- 参考向量附近的向量能生成相似图像
- 潜空间连续、紧凑、光滑，支持插值

**劣势**：
- 生成模糊图像（损失函数问题，非架构问题）
- 缺乏选择生成特定图像的能力

**变体**：CVAE、β-VAE、VQ-VAE。

## 关联概念

- [[autoencoder]] — VAE 是对普通自编码器潜空间的正则化
- [[evidence-lower-bound]] — VAE 的损失函数基于 ELBO
- [[expectation-maximisation]] — VAE 训练与 EM 的联系
