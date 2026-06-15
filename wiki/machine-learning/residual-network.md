---
summary: 残差网络通过跳跃连接让每层学习残差 $f(x)$ 而非完整映射，即使 $f'$ 消失梯度仍能回传到输入，解决了深层网络的梯度消失问题。
tags: [machine-learning, deep-learning, architecture]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-residual-network.md
---

# 残差网络（ResNet）

## 定义

传统网络：$h_1 = f_1(x)$，$h_2 = f_2(h_1)$，$y = f_3(h_2)$。
残差网络：$h_1 = x + f_1(x)$，$h_2 = h_1 + f_2(h_1)$，$y = h_2 + f_3(h_2)$。

始终传递 $x$，每层只学习残差。

## 关键点

- 核心思想：即使 $f'$ 消失，梯度仍然可以通过恒等连接回传到 $x$。
- 使训练数百层的网络成为可能。

## 关联概念

- [[neural-network]] — 残差网络是深层神经网络的关键架构创新
- [[cnn]] — ResNet 最初在 CNN 上提出
