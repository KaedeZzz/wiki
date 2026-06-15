---
summary: 卷积神经网络通过局部连接的卷积核提取空间特征，配合池化和步幅实现下采样，膨胀卷积扩大感受野而不增加参数。
tags: [machine-learning, deep-learning, architecture]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-convolution-neural-network-(cnn).md
  - raw/machine-learning/2026-06-08-deep-learning-pooling.md
  - raw/machine-learning/2026-06-08-deep-learning-stride.md
  - raw/machine-learning/2026-06-08-deep-learning-dilated-convolution.md
---

# 卷积神经网络（CNN）

## 定义

利用局部连接和权值共享的卷积操作从输入中提取空间特征的神经网络架构。

## 关键点

- **池化（Pooling）**：每隔 $n$ 个元素取一个，丢弃其余，实现下采样。
- **步幅（Stride）**：卷积核每步移动 $n$ 个像素而非 1 个，也起下采样作用。
- **膨胀卷积（Dilated Convolution）**：卷积核元素之间间隔 $n-1$ 个像素（膨胀率为 $n$），在不增加参数的情况下扩大感受野。

## 关联概念

- [[neural-network]] — CNN 是神经网络的特化架构
- [[residual-network]] — 在 CNN 基础上加入跳跃连接
- [[autoencoder]] — CNN 常用于编码器/解码器结构
