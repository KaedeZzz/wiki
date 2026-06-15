---
summary: 高斯过程是多元高斯到无穷维的推广，由均值函数和协方差函数完全指定，是函数空间上的分布。通过条件化训练数据得到后验过程用于预测。
tags: [machine-learning, probabilistic-models, bayesian]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-gaussian-process-gaussian-process.md
  - raw/machine-learning/2026-06-08-gaussian-process-posterior-gaussian-process.md
  - raw/machine-learning/2026-06-08-gaussian-process-matérn-covariance-functions.md
---

# 高斯过程

## 定义

一组随机变量的集合，其中任意有限子集服从联合高斯分布。由均值函数 $m(x)$ 和协方差函数 $k(x, x')$ 完全指定：$f \sim \mathcal{GP}(m(x), k(x, x'))$。

非形式化地说：无穷长向量 ≈ 函数，反复从 GP 采样就是反复从多元高斯采样，给出 $f(x)$ 的不同实现。

## 关键点

**后验高斯过程**：以 GP 为先验做贝叶斯推断。已知训练数据 $\mathbf{f}$ 和测试输入 $\mathbf{f}^*$ 的联合分布后，条件化得到预测分布：
$$\mathbf{f}^*|\mathbf{f} \sim \mathcal{N}(\mu_* + \Sigma_*^T \Sigma^{-1}(\mathbf{f} - \mu),\; \Sigma_{**} - \Sigma_*^T \Sigma^{-1} \Sigma_*)$$

后验过程：$f|\mathcal{D} \sim \mathcal{GP}(m_\mathcal{D}, k_\mathcal{D})$，后验方差总小于先验方差（数据提供了信息）。

**Matérn 协方差函数**：$\nu$ 控制平滑度，样本函数 $\lfloor \nu - 1 \rfloor$ 次可微，$l$ 是特征长度尺度。

## 关联概念

- [[graphical-model]] — GP 可在贝叶斯框架中使用
- [[gaussian-mixture-model]] — 另一种基于高斯的概率模型（有限混合 vs 无限维）
