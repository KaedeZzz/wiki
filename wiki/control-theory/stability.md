---
summary: 系统稳定性有三种等价刻画：瞬态响应衰减为零、BIBO（有界输入有界输出）、以及极点位置判据（连续：左半 s 平面；离散：单位圆内）。
tags: [control-theory, stability]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-stability-stability.md
  - raw/control-theory/2026-07-06-stability-bibo-stability.md
  - raw/control-theory/2026-07-06-stability-open-loop-stability-criterion.md
  - raw/control-theory/2026-07-06-stability-conditions-for-stability-of-a-discrete-time-system.md
  - raw/control-theory/2026-07-06-stability-proofs-of-conditions-for-stability-of-a-discrete-time-system.md
---

# 稳定性

## 定义

**稳定**系统：瞬态响应随时间衰减到零。等价地，这可以从输入-输出行为或系统内部结构两个角度刻画。

## 关键点

### BIBO 稳定性

**有界输入 → 有界输出**：存在正常数 $M$、$N$，使得**对任意**满足 $|u_k|\leq M$ 的输入信号，输出满足 $|y_k|\leq N$。

- 若某个有界输入产生无界输出 → 系统不稳定。
- 存在这样一族有界输入：每个都产生有界输出，但**不存在统一上界**能同时限制所有输出 → 系统也不稳定（"边缘不稳定"的一种形式）。

### 三条等价条件（离散 LTI）

对 z 域 [[transfer-function]] $G(z)$，以下三条**等价**：

1. $G$ BIBO 稳定
2. 所有极点 $p_i$ 满足 $|p_i|<1$（即位于开单位圆盘内）
3. 冲激响应 $\{g_k\}$ 绝对可和：$\sum_{k=0}^{\infty}|g_k|<\infty$

证明思路（要点）：

- $(1)\Rightarrow(2)$：若某 $|p|\geq 1$，通过部分分式分解定位到该极点对应的项，构造一个有界输入使输出无界（例如对 $|p|=1$ 的极点用其对应频率的谐波输入，输出线性增长）。
- $(3)\Rightarrow(1)$：由离散卷积 $y_k=\sum_i g_i u_{k-i}$ 直接三角不等式 $|y_k|\leq M\sum |g_i|$。
- $(2)\Rightarrow(3)$：部分分式分解 + 每项 $\sum_k k^{l-1}|p|^k$ 收敛当且仅当 $|p|<1$。

### 开环稳定性判据（连续 LTI）

对连续 [[transfer-function]] $G(s)$，稳定域是 s 平面的开**左半平面**：

- **任一极点**有正实部 → **不稳定**
- **虚轴上有重根** → **不稳定**
- 虚轴上有**孤立**极点 → **边缘稳定**（振荡不衰减也不发散）
- **所有极点**都有负实部 → **渐近稳定**

s 平面稳定域（开左半平面）与 z 平面稳定域（开单位圆盘）通过 $z=e^{sT}$ 相互映射。

## 关联概念

- [[transfer-function]] — 极点/零点定义
- [[z-transform-discrete-systems]] — 离散极点位置 → 时域衰减/振荡行为
- [[nyquist-stability]] — 通过开环频率响应判定**闭环**稳定性
- [[frequency-response]] — 相位/增益裕度是稳定性"余量"的定量度量
- [[eigendecomposition]] — 状态空间下，稳定 ⇔ 系统矩阵 $A$ 的特征值满足极点条件
