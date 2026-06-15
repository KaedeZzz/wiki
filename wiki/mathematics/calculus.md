---
summary: 微积分核心工具：Riemann 积分、Jacobian 矩阵、梯度/散度/旋度等微分算子，以及换元公式。
tags: [mathematics, calculus]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-calculus-integral.md
  - raw/mathematics/2026-06-09-calculus-vector.md
  - raw/mathematics/2026-06-09-calculus-multivariate.md
---
# 微积分

## 定义

微积分研究函数的局部变化率（微分）和累积量（积分）。向量微积分将这些概念推广到多元函数和向量场。

## 关键点

### Riemann 积分

将区间 $[a, b]$ 分割为子区间，取 Riemann 和：

$$S = \sum_{i=1}^n f(x_i^*) \Delta x_i$$

当分割无限细化时，若 Riemann 和的极限存在且与分割方式和取样点无关，则函数 Riemann 可积：

$$\int_a^b f(x) \, dx = \lim_{\|\Delta\| \to 0} \sum_{i=1}^n f(x_i^*) \Delta x_i$$

连续函数在闭区间上一定 Riemann 可积。

### Jacobian 矩阵

对映射 $\mathbf{f}: \mathbb{R}^n \to \mathbb{R}^m$，Jacobian 矩阵是所有偏导数组成的矩阵：

$$J = \begin{pmatrix} \frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_n} \\ \vdots & \ddots & \vdots \\ \frac{\partial f_m}{\partial x_1} & \cdots & \frac{\partial f_m}{\partial x_n} \end{pmatrix}$$

- **链式法则**的矩阵形式：$J_{\mathbf{g} \circ \mathbf{f}} = J_{\mathbf{g}} \cdot J_{\mathbf{f}}$。
- **换元公式**：多重积分中，$dx\,dy = |\det J| \, du\,dv$。
- Jacobian 行列式的绝对值衡量变换对体积的局部缩放因子。

### 梯度、散度、旋度

对标量场 $f$ 和向量场 $\mathbf{F} = (F_1, F_2, F_3)$：

- **梯度** (Gradient)：$\nabla f = \left(\frac{\partial f}{\partial x_1}, \dots, \frac{\partial f}{\partial x_n}\right)$，指向函数增长最快的方向。
- **散度** (Divergence)：$\nabla \cdot \mathbf{F} = \frac{\partial F_1}{\partial x} + \frac{\partial F_2}{\partial y} + \frac{\partial F_3}{\partial z}$，衡量向量场的"源"强度。
- **旋度** (Curl)：$\nabla \times \mathbf{F}$，衡量向量场的旋转程度。

### 重要恒等式

- $\nabla \times (\nabla f) = \mathbf{0}$（梯度场无旋）
- $\nabla \cdot (\nabla \times \mathbf{F}) = 0$（旋度场无散）

## 关联概念

- [[gradient-descent]] — 梯度是优化中确定下降方向的核心工具。
- [[vector-norms]] — 梯度的范数衡量函数变化的剧烈程度。
