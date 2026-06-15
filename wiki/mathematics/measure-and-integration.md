---
summary: 测度与积分理论为概率论和泛函分析提供严格基础，涵盖 σ-代数、Lebesgue 积分、概率测度、Gauss 测度、Wasserstein 距离及 Hilbert 空间上的 Bayes 推断。
tags: [mathematics, measure-theory]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-measure-theory-basics.md
---

# 测度与积分

## 定义

测度（Measure）是定义在 σ-代数上的可数可加非负集函数，将"大小"概念推广到一般集合。Lebesgue 积分基于测度理论，将积分从 Riemann 框架推广到更广泛的函数类。

## 关键点

### σ-代数与测度

- **σ-代数** $\mathcal{F}$：集合 $\Omega$ 上的子集族，对补运算和可数并封闭
- **测度** $\mu: \mathcal{F} \to [0, \infty]$，满足：
  - $\mu(\emptyset) = 0$
  - 可数可加性：$\mu\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty \mu(A_i)$（不相交时）

### Lebesgue 积分

将 Riemann 积分从"对定义域分割"改为"对值域分割"，可处理更广泛的函数（如 Dirichlet 函数）。

$$\int f \, d\mu = \sup\left\{\int s \, d\mu : s \text{ 为简单函数}, 0 \leq s \leq f\right\}$$

### 概率测度

测度 $P$ 满足 $P(\Omega) = 1$ 时称为概率测度，三元组 $(\Omega, \mathcal{F}, P)$ 构成概率空间。

### Gauss 测度

将有限维 Gauss 分布推广到无穷维空间（如函数空间）。在 Hilbert 空间 $H$ 上，Gauss 测度由均值元素 $m \in H$ 和协方差算子 $C: H \to H$（迹类、正定、自伴）唯一确定。

### Wasserstein 距离

度量两个概率测度之间的最优传输代价：

$$W_p(\mu, \nu) = \left(\inf_{\gamma \in \Pi(\mu,\nu)} \int \|x - y\|^p \, d\gamma(x, y)\right)^{1/p}$$

其中 $\Pi(\mu,\nu)$ 为边际分别为 $\mu, \nu$ 的联合分布（耦合）全体。

### Hilbert 空间上的 Bayes 定理

在无穷维设定下进行后验推断：给定先验测度 $\mu_0$（通常为 Gauss 测度），通过似然更新得到后验测度 $\mu^y$，常用 Radon–Nikodym 导数表示。

## 关联概念

- [[functional-spaces]] — Gauss 测度和 Bayes 推断的自然载体
- [[gaussian-distribution]] — Gauss 测度是 Gauss 分布的无穷维推广
- [[bayes-theorem]] — Hilbert 空间 Bayes 定理是有限维 Bayes 公式的推广
