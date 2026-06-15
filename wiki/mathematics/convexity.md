---
summary: 凸性理论：凸/凹函数定义、Jensen 不等式、对数凹分布、强凸性，及其在优化中的核心地位。
tags: [mathematics, analysis]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-analysis-convexity.md
  - raw/mathematics/2026-06-09-analysis-optimization.md
  - raw/mathematics/2026-06-09-analysis-inequalities.md
---
# 凸性

## 定义

函数 $f: \mathbb{R}^n \to \mathbb{R}$ 是**凸函数** (convex function)，当且仅当对所有 $x, y$ 及 $\lambda \in [0, 1]$：

$$f(\lambda x + (1-\lambda) y) \leq \lambda f(x) + (1-\lambda) f(y)$$

几何直觉：函数图像上任意两点间的弦位于图像上方。

**凹函数** (concave function)：$-f$ 为凸函数。

## 关键点

### Jensen 不等式

若 $f$ 为凸函数，$X$ 为随机变量，则：

$$f(\mathbb{E}[X]) \leq \mathbb{E}[f(X)]$$

凹函数时不等号反向。这是推导 ELBO 等变分下界的基础工具。

### 凸性判定

- **一阶条件**（可微时）：$f(y) \geq f(x) + \nabla f(x)^\top (y - x)$。
- **二阶条件**（二阶可微时）：Hessian 矩阵 $\nabla^2 f(x) \succeq 0$（半正定）。

### 强凸性

$f$ 是 $m$-强凸的，若 $f(x) - \frac{m}{2}\|x\|^2$ 仍为凸函数。等价地：

$$f(y) \geq f(x) + \nabla f(x)^\top (y-x) + \frac{m}{2}\|y - x\|^2$$

强凸性保证全局最小值唯一，且梯度下降线性收敛。

### 对数凹分布

概率密度 $p(x)$ 是**对数凹的** (log-concave)，若 $\log p(x)$ 是凹函数。

- 常见对数凹分布：高斯分布、指数分布、Beta 分布、均匀分布。
- 对数凹分布在卷积下封闭、边缘化下封闭。

### 凸优化

凸函数的局部最小值即全局最小值——这是凸优化可高效求解的根本原因。

## 关联概念

- [[functional-spaces]] — 凸性定义依赖向量空间结构；$L^p$ 范数本身是凸函数。
- [[evidence-lower-bound]] — Jensen 不等式是推导 ELBO 的关键步骤。
