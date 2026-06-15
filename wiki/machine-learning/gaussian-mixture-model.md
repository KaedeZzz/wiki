---
summary: 高斯混合模型将观测数据建模为多个高斯分量的加权混合，每个数据点由一个隐变量指示其来源分量，参数通过 EM 算法估计。
tags: [machine-learning, probabilistic-models]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-concepts-gaussian-mixture-model.md
  - raw/machine-learning/2026-06-08-expectation-maximisation-em-algorthm-on-gaussian-mixture-model.md
---

# 高斯混合模型

## 定义

$$p(x) = \sum_{m=1}^{M} \pi_m \mathcal{N}(x; \mu_m, \Sigma_m)$$
其中 $c_m$ 是隐分量标签，$\pi_m = p(c_m)$ 是分量先验，参数集 $\theta = \{\pi_k, \mu_k, \Sigma_k\}_{k=1}^{K}$。

## 关键点

**EM 算法求解 GMM**：

E-step：计算后验（软计数）：
$$\gamma_{nk} = \frac{\pi_k \mathcal{N}(x_n|\mu_k, \Sigma_k)}{\sum_k \pi_k \mathcal{N}(x_n|\mu_k, \Sigma_k)}$$

M-step：
- 先验：$\pi_k = N_k / N$（软计数的比例）
- 均值：$\mu_k = \frac{\sum_n \gamma_{nk} x_n}{N_k}$（加权均值）
- 协方差：$\Sigma_k = \frac{1}{N_k} \sum_n \gamma_{nk}(x_n - \mu_k)(x_n - \mu_k)^T$（加权协方差）

其中 $N_k = \sum_n \gamma_{nk}$。

## 关联概念

- [[expectation-maximisation]] — GMM 参数估计的标准方法
- [[clustering]] — GMM 是聚类的概率化推广
- [[factor-analysis]] — 另一种连续隐变量生成模型
