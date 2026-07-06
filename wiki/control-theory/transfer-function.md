---
summary: 线性时不变系统的传递函数 G(s) 或 G(z) 是输入到输出的比值（Laplace/z 域），闭环系统由 H=KG/(1+KG) 给出，闭环极点是 1+KG 的零点。
tags: [control-theory, linear-systems]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-basics-transfer-function.md
  - raw/control-theory/2026-07-06-basics-poles.md
  - raw/control-theory/2026-07-06-basics-closed-loop-control-system.md
  - raw/control-theory/2026-07-06-basics-closed-loop-transfer-function.md
  - raw/control-theory/2026-07-06-basics-closed-loop-stability.md
  - raw/control-theory/2026-07-06-discrete-systems-polynomial-degrees.md
---

# 传递函数

## 定义

对线性时不变（LTI）系统，**传递函数** $G$ 是零初始条件下输出对输入的比值，在连续时间用 [[laplace-transform]] 表示为 $G(s)$，在离散时间用 z 变换表示为 $G(z)$。它是一个**有理函数**：分子多项式 $b(\cdot)$ 与分母多项式 $a(\cdot)$ 的商。

## 关键点

### 极点与零点

对 $G(z)=b(z)/a(z)$：

- **极点（poles）**：$a(z)=0$ 的解，即分母零点。
- **零点（zeros）**：$b(z)=0$ 的解。

极点位置决定系统的动态行为（衰减速率、振荡频率、稳定性）。见 [[stability]] 与 [[z-transform-discrete-systems]]。

### 规范形式与多项式次数

将 $G(z)$ 写成负幂形式：

$$G(z)=\frac{b_0+b_1 z^{-1}+\dots+b_m z^{-m}}{1+a_1 z^{-1}+\dots+a_n z^{-n}}$$

化为正幂形式后，分子分母都是 $\max(m,n)$ 次多项式。这个观察在 [[nyquist-stability]] 的证明里用于极点数守恒。

### 闭环传递函数

考虑单位负反馈回路（增益为 $K$、被控对象为 $G$）：

$$H(z)=\frac{KG(z)}{1+KG(z)}$$

将 $G(z)=b(z)/a(z)$ 代入：

$$1+KG(z)=\frac{a(z)+Kb(z)}{a(z)}$$

由此：

- **闭环极点** = $a(z)+Kb(z)=0$ 的解 = $1+KG(z)$ 的**零点**。
- **开环极点** = $a(z)=0$ 的解 = $1+KG(z)$ 的**极点**。

反馈把 $G$ 的零点/极点重新组合成闭环特征方程 $1+KG=0$ 的根，增益 $K$ 是"设计旋钮"。

## 关联概念

- [[laplace-transform]] — 连续 LTI 系统传递函数所在的复频域
- [[z-transform-discrete-systems]] — 离散 LTI 的等价工具与极点位置解释
- [[stability]] — 极点位置决定稳定性
- [[nyquist-stability]] — 通过频率响应上 $-1/K$ 被 $G(e^{j\theta})$ 环绕次数判定闭环稳定性
- [[frequency-response]] — Bode 图是传递函数在 $s=j\omega$ 或 $z=e^{j\theta}$ 上的取值
- [[eigendecomposition]] — 状态空间形式下，极点即状态矩阵的特征值
