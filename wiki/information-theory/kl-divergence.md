---
summary: KL 散度 D(P‖Q)=E_P[log P/Q] 度量分布 P 相对参考 Q 的"信息距离"；非负、不对称、Gibbs 不等式；交叉熵 H(P,Q)=H(P)+D(P‖Q) 使得机器学习中最小化交叉熵等价于最小化 KL。
tags: [information-theory, divergence]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-basics-kl-divergence.md
  - raw/information-theory/2026-07-06-basics-kl-divergence-between-continuous-random-variables.md
  - raw/information-theory/2026-07-06-basics-kl-divergence-of-gaussians.md
  - raw/information-theory/2026-07-06-basics-kl-divergence-with-jensen's-inequality.md
  - raw/information-theory/2026-07-06-basics-gibbs-inequality.md
  - raw/information-theory/2026-07-06-basics-cross-entropy.md
  - raw/information-theory/2026-07-06-basics-softmax-function.md
---

# KL 散度

## 定义

**Kullback-Leibler 散度**（相对熵）：

$$D_{KL}(P\|Q) = \sum_x P(x)\log\frac{P(x)}{Q(x)} \quad(\text{连续}: \int f(u)\log\tfrac{f(u)}{g(u)}\,du)$$

## 关键点

### Gibbs 不等式（非负性）

$$D_{KL}(P\|Q) \geq 0,\quad \text{等号} \Leftrightarrow P = Q$$

两种证明：

- **用 $\ln x \leq x - 1$**：$-D(P\|Q) = \tfrac{1}{\ln 2}\sum_x P(x)\ln\tfrac{Q(x)}{P(x)} \leq \tfrac{1}{\ln 2}\sum_x P(x)(\tfrac{Q(x)}{P(x)}-1) = 0$。
- **用 Jensen**（见 [[convexity]]）：$D(P\|Q) = \mathbb{E}_P[-\log\tfrac{Q(X)}{P(X)}] \geq -\log\mathbb{E}_P[\tfrac{Q(X)}{P(X)}] = -\log 1 = 0$。

### 不对称

$D(P\|Q) \neq D(Q\|P)$——**不是距离**，只是散度。前项（$P$ 在期望里）叫"forward KL"，后者叫"reverse KL"，两者在生成模型/变分推断里给出不同的优化行为（mode covering vs mode seeking）。

### 高斯闭式解

对 $P = \mathcal{N}(\mu,\sigma^2)$、$Q = \mathcal{N}(0,1)$：

$$D_{KL}(P\|Q) = -\tfrac{1}{2}(1 + \log\sigma^2 - \mu^2 - \sigma^2)$$

这个公式是 [[variational-autoencoder]] 中 ELBO 正则项的显式形式。

### 交叉熵

$$H(P,Q) = \sum_x P(x)\log\frac{1}{Q(x)} = H(P) + D_{KL}(P\|Q)$$

*"以模型 $Q$ 编码由 $P$ 采样的数据时的平均惊奇度"*。因 $H(P)$ 与 $Q$ 无关，**最小化交叉熵 = 最小化 KL**——这是分类问题里 [[loss-function]] 用交叉熵的信息论理由。

### Softmax 是自然搭档

多类分类模型输出 logits，通过 Softmax 转为概率：

$$p(y = k|\mathbf{x}) = \frac{\exp(\mathbf{w}_k^T\tilde{\mathbf{x}})}{\sum_{k'}\exp(\mathbf{w}_{k'}^T\tilde{\mathbf{x}})}$$

再与 one-hot 标签取交叉熵——训练时反向传播的梯度形式极简洁（$\hat{p} - y$）。

### 与互信息、熵的关系

- $I(X;Y) = D(P_{XY}\|P_X P_Y)$（见 [[mutual-information]]）
- $H(P,Q) - H(P) = D(P\|Q)$
- 均匀 $Q$ 下 $D(P\|Q) = \log|\mathcal{X}| - H(P)$（信息熵到均匀分布的"距离"）

## 关联概念

- [[information-entropy]] — 熵是熵到均匀的 KL 的位移
- [[mutual-information]] — MI 是特殊形式的 KL
- [[convexity]] — $D(P\|Q)$ 是 $(P,Q)$ 的凸函数；Jensen 是主要证明工具
- [[gaussian-distribution]] — 高斯之间的 KL 有闭式
- [[variational-autoencoder]] — ELBO 的正则项就是 $D(q_\phi\|p)$
- [[loss-function]] — 分类的交叉熵损失
- [[source-coding]] — 用 $\hat P$ 编码的冗余 = $D(P\|\hat P)$，见 [[source-coding]] 的 Minimax Redundancy
