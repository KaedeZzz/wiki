---
summary: 神经网络是由多层参数化非线性变换组成的函数逼近器，涵盖 ReLU 激活、CNN、残差网络等架构，以及 dropout、层归一化等训练技巧。
tags: [machine-learning, deep-learning]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-deep-learning-neural-network.md
  - raw/machine-learning/2026-06-08-basics-concepts-relu.md
  - raw/machine-learning/2026-06-08-deep-learning-layer-normalisation.md
---

# 神经网络

## 定义

由多层参数化变换组成的函数逼近器，每层通常包含线性变换和非线性激活。

## 关键点

**ReLU 激活函数**：$\phi(t) = \max(0, t)$，计算简单且缓解梯度消失。

**层归一化**：对向量 $z \in \mathbb{R}^D$ 做归一化：
$$N(z)_i = \frac{z_i - \text{mean}(z)}{\text{std}(z) + \epsilon}$$

**不变变换**：若对任意变换 $\phi$ 有 $F(X*\phi) = F(X)$，可从非不变网络 $g$ 构造不变网络：$f(X) = \max_\phi g(X*\phi)$。

## 关联概念

- [[cnn]] — 卷积神经网络，利用局部连接和权值共享
- [[residual-network]] — 通过跳跃连接解决深层网络梯度消失
- [[dropout]] — 训练时随机丢弃神经元的正则化方法
- [[optimisers]] — 训练神经网络的优化算法
