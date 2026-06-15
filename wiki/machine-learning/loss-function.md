---
summary: 损失函数衡量模型预测与真实值之间的差异，是训练优化的目标。包括实际损失、经验损失、最小二乘损失、交叉熵损失、均方误差等。
tags: [machine-learning, basics, optimisation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-loss-function.md
  - raw/machine-learning/2026-06-08-basics-theories-actual-loss.md
  - raw/machine-learning/2026-06-08-basics-theories-empirical-loss.md
  - raw/machine-learning/2026-06-08-basics-theories-cross-entropy-loss.md
  - raw/machine-learning/2026-06-08-basics-concepts-least-squares-loss.md
  - raw/machine-learning/2026-06-08-basics-theories-mean-squared-error.md
---

# 损失函数

## 定义

损失函数是衡量模型预测好坏的数学度量。

## 关键点

**实际损失（Actual Loss）**：对所有可能输入的期望损失：
$$\mathcal{L}_{act} = \int \left[\sum_{i=1}^{K} \mathcal{L}(f(x,\theta), \omega_i) P(\omega_i|x)\right] p(x) dx$$
由于真实分布 $p(\omega|x)$ 和 $p(x)$ 通常未知，无法直接计算。

**经验损失（Empirical Loss）**：用训练数据近似：
$$\mathcal{L}_{emp} = \frac{1}{N} \sum_{i=1}^{N} \mathcal{L}(f(x_i, \theta), y_i)$$

**常见损失函数**：
- **最小二乘损失**：$L(y, \hat{y}) = \|y - \hat{y}\|^2$，常用于回归。
- **均方误差**：$J = \mathbb{E}[\epsilon_n^2]$。
- **交叉熵损失**：分类任务中定义为正确分类的负对数似然，通过 softmax 将 logits 转为概率后计算：$L = \log(\sum_{k'} \exp(w_{k'}^T \tilde{x})) - w_k^T \tilde{x}$。

## 关联概念

- [[gradient-descent]] — 最小化损失的方法
- [[regularisation]] — 在损失函数中加入额外项以防过拟合
- [[supervised-and-unsupervised-learning]] — 损失函数在监督学习框架中的角色
