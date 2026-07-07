---
summary: PAC-Bayes 界用先验/后验权重分布之间的 KL 散度控制泛化误差，将贝叶斯推断和 PAC 学习理论桥接起来；对深度网络的"隐含正则"提供了信息论式解释。
tags: [information-theory, learning-theory, generalization]
updated: 2026-07-06
sources:
  - raw/information-theory/2026-07-06-pac-bayes-bound.md
---

# PAC-Bayes 界

## 定义

考虑机器学习模型：权重 $w$、训练集 $\mathcal{D}$、损失 $L$。**PAC-Bayes 界**是一族泛化不等式，形式（原始笔记里所用一种）：

$$L_p \leq \frac{1}{1 - \tfrac{1}{2\beta}}\!\left(\mathbb{E}_w[L_\mathcal{D}] + \frac{\beta}{N}\,D_{KL}(q(w|\mathcal{D})\,\|\,p(w))\right)$$

其中：

- $L_p$：期望泛化损失（未来数据）
- $L_\mathcal{D}$：经验损失（训练数据）
- $p(w)$：**先验**权重分布（数据未见前）
- $q(w|\mathcal{D})$：**后验**权重分布（拟合 $\mathcal{D}$ 后）
- $N$：训练样本数
- $\beta > 1/2$：温度/尺度参数

**核心思想**：泛化差距被后验相对于先验的 [[kl-divergence]] 所控制——学习"跑离"先验越远，越容易过拟合。

## 关键点

### 与 PAC 与贝叶斯的关系

- **PAC 学习**：给出与具体假设无关的一致收敛式界（VC 维等），常常悲观。
- **贝叶斯**：把权重当作随机变量，但没有直接的泛化保证。
- **PAC-Bayes**：在 PAC 框架内允许"后验分布"作为假设，KL 项作为复杂度惩罚——两者优势兼得。

$D(q\|p)$ 类似正则化项：先验描述"我们对权重的信念"，后验描述"数据促使我们相信的"，差距代表学习"消化"的信息量。

### Vacuous bound 陷阱

若 $q$ 是 $\delta$-函数（权重完全收敛），$D_{KL} \to \infty$，界完全无信息（**vacuous**）。

**修复思路**：把 $q(w|\mathcal{D})$ 建模为**围绕收敛权重的多元高斯**，某些维度可以任意窄（对应"关键权重"），某些维度可以任意宽（对应"不重要权重"，可自由变动不改结果）。这与深度网络"多数参数是冗余的"经验事实吻合，也是**神经网络"平坦极小值泛化好"**观察的一种理论解释。

### 最小 KL 与互信息

$$\min_{p(w)} D_{KL}(q(w|\mathcal{D})\|p(w))$$

在 $p(w) = \mathbb{E}_\mathcal{D}[q(w|\mathcal{D})]$（后验对所有数据集的边缘）处取到最小；此时 KL 恰为 $I(W;\mathcal{D})$——**权重与数据集的互信息**。

*"记住的数据越少（$I$ 越小），泛化越好"*——与信息瓶颈理论、[[variational-autoencoder]] 中的编码器压缩项一脉相承。

## 关联概念

- [[kl-divergence]] — 界的核心正则项
- [[mutual-information]] — 最优先验下 KL = $I(W;\mathcal{D})$
- [[posterior-distribution]] — 权重的贝叶斯后验框架
- [[variational-autoencoder]] — 编码器压缩项与 PAC-Bayes 是同族思想
- [[regularisation]] — KL 项作为正则化的信息论解读
- [[neural-network]] — 对深度网络"隐含正则"的候选理论解释之一
