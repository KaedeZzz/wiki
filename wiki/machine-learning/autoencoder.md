---
summary: 自编码器通过编码器-瓶颈-解码器结构将数据压缩到低维潜空间再重建，实现降维。潜空间质量 = 重建质量，但普通自编码器的潜空间缺乏组织，由此衍生出 VAE。
tags: [machine-learning, deep-learning, generative-model]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-autoencoder.md
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-latent-space.md
  - raw/machine-learning/2026-06-08-deep-learning-autoencoders-u-net.md
---

# 自编码器

## 定义

由三部分组成：编码器 → 潜空间 → 解码器。目标是最小化重建数据与原始输入之间的差异。

## 关键点

- 核心用途是**降维**：潜空间是数据的压缩特征表示。
- **潜空间质量 = 重建质量**。
- 局限性：普通自编码器的潜空间无组织、不连续，中点无意义，对噪声输入重建差。
- 解决方案：对潜空间加正则 → [[variational-autoencoder]]。
- **U-Net** 是自编码器的变体，加入了编码器到解码器的跳跃连接。

**潜空间可视化方法**（按速度排序）：
1. [[pca]] — 快速、可解释，但只能处理线性结构
2. [[umap]] — 高质量，保持相对位置
3. [[t-sne]] — 非线性，但较慢

## 关联概念

- [[variational-autoencoder]] — 通过正则化潜空间解决普通自编码器的缺陷
- [[pca]] — 线性降维，自编码器是其非线性推广
- [[factor-analysis]] — 线性隐变量模型，概率版 PCA
