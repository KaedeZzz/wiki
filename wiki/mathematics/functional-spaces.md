---
summary: 函数/向量空间的层级结构：度量空间 → 赋范空间 → Banach 空间 → 内积空间 → Hilbert 空间，以及 $L^p$ 空间。
tags: [mathematics, analysis]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-analysis-functional.md
  - raw/mathematics/2026-06-09-analysis-spaces.md
  - raw/mathematics/2026-06-09-analysis-hilbert.md
---
# 函数空间

## 定义

函数空间是以函数为元素的向量空间，其结构按约束强度递增排列：

| 空间 | 结构 |
|------|------|
| 度量空间 (Metric space) | 集合 + 距离函数 $d(x,y)$，满足正定性、对称性、三角不等式 |
| 赋范空间 (Normed space) | 向量空间 + 范数 $\|\cdot\|$（范数诱导度量 $d(x,y) = \|x-y\|$） |
| Banach 空间 | 完备的赋范空间（每个 Cauchy 序列收敛） |
| 内积空间 (Inner product space) | 向量空间 + 内积 $\langle \cdot, \cdot \rangle$（内积诱导范数 $\|x\| = \sqrt{\langle x, x \rangle}$） |
| Hilbert 空间 | 完备的内积空间 |

## 关键点

### 度量空间

距离函数 $d: X \times X \to \mathbb{R}$ 满足：
1. $d(x,y) \geq 0$，且 $d(x,y) = 0 \iff x = y$
2. $d(x,y) = d(y,x)$
3. $d(x,z) \leq d(x,y) + d(y,z)$（三角不等式）

### $L^p$ 空间

$$L^p(\Omega) = \left\{ f : \Omega \to \mathbb{R} \;\middle|\; \|f\|_p = \left(\int_\Omega |f|^p \, d\mu \right)^{1/p} < \infty \right\}$$

- $L^2$ 是 Hilbert 空间（内积 $\langle f, g \rangle = \int f \cdot g \, d\mu$）。
- $L^p$（$1 \leq p \leq \infty$）是 Banach 空间。
- **Hölder 不等式**：$\|fg\|_1 \leq \|f\|_p \|g\|_q$，其中 $1/p + 1/q = 1$。
- **Minkowski 不等式**：$\|f + g\|_p \leq \|f\|_p + \|g\|_p$（三角不等式）。

### 完备性

空间是完备的，当且仅当每个 Cauchy 序列在该空间中收敛。$\mathbb{Q}$ 不完备（有 Cauchy 序列收敛到无理数），$\mathbb{R}$ 完备。

### Hilbert 空间的重要性

- 正交分解：任何元素可投影到闭子空间。
- Riesz 表示定理：连续线性泛函可唯一表示为内积。
- 量子力学、信号处理、核方法 (RKHS) 的数学基础。

## 关联概念

- [[vector-norms]] — 范数的具体种类（$\ell_1, \ell_2, \ell_\infty$ 等）及其性质。
- [[convexity]] — 范数是凸函数；$L^p$ 空间中的凸性分析。
- [[gaussian-process]] — 高斯过程的样本路径存在于特定 RKHS（再生核 Hilbert 空间）中。
