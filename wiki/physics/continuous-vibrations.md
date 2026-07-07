---
summary: 连续介质振动（弦、梁）通过分离变量得到模态形状与自然频率；Euler-Bernoulli 梁 ρA ÿ + EI y''''=f 是 4 阶 PDE，通解含正弦、余弦、指数衰减（evanescent）项；边界条件（clamped/pinned/free）选出可能的 k_n。
tags: [physics, vibrations, continuous, pde]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-vibrations-equation-of-free-vibration-of-string.md
  - raw/physics/2026-07-06-mechanics-vibrations-harmonic-free-motion-theorem.md
  - raw/physics/2026-07-06-mechanics-vibrations-plucked-string-problem.md
  - raw/physics/2026-07-06-mechanics-vibrations-forced-harmonic-response-to-harmonic-excitation.md
  - raw/physics/2026-07-06-mechanics-vibrations-base-oscillation-of-tuning-fork.md
  - raw/physics/2026-07-06-mechanics-vibrations-equation-of-motion-for-euler-bernoulli-bending-beam.md
  - raw/physics/2026-07-06-mechanics-vibrations-vibration-of-euler-bernoulli-bending-beams.md
  - raw/physics/2026-07-06-mechanics-vibrations-modes-of-a-pinned-pinned-beam.md
  - raw/physics/2026-07-06-mechanics-vibrations-modes-of-a-free-free-beam.md
  - raw/physics/2026-07-06-mechanics-vibrations-modes-of-a-clamped-free-beam.md
  - raw/physics/2026-07-06-mechanics-vibrations-continuous-vibration-transfer-function.md
  - raw/physics/2026-07-06-mechanics-vibrations-continuous-transfer-function-with-damping.md
  - raw/physics/2026-07-06-mechanics-vibrations-connected-coupling-system.md
  - raw/physics/2026-07-06-mechanics-vibrations-connected-coupling-system-1.md
  - raw/physics/2026-07-06-mechanics-vibrations-approximation-of-continuous-modes-from-discrete-modes.md
  - raw/physics/2026-07-06-mechanics-vibrations-approximation-of-continuous-system-from-discrete-system.md
---

# 连续介质振动

## 定义

将 [[small-vibrations]] 的 $N$-自由度矩阵推广到**无限自由度**——一维弦、梁、板等连续介质。运动量 $y(x,t)$ 满足 PDE；模态形状 $U_n(x)$ 成为函数，自然频率 $\omega_n$ 仍为离散谱。

## 关键点

### 弦：波动方程

紧张弦满足 $\rho\ddot y = P\,y''$（[[partial-differential-equations]] 中的波动方程）。自由振动解：

$$y(x,t) = \sum_n b_n\,U_n(x)\cos(\omega_n t + \phi)$$

两端固定弦的模态 $U_n = \sin(n\pi x/L)$，$\omega_n \propto n$（谐波梯度）。

**谐运动定理**：*自由运动若时间上是正弦，则空间上必然也是正弦*。因分离变量 $y = U(x)T(t)$ 代入线性 PDE 后两边必须相等一个常数，且解形式对 $x$ 和 $t$ 都是简谐。

### 拨弦（plucked string）初值问题

弦被拉到三角形起始形状后释放（初速度 $=0$、$\phi=0$）。用[[generating-functions]] 意义下的 Fourier 级数分解三角形初值：

$$b_n = \frac{2y_0 L^2}{n^2\pi^2 a(L-a)}\sin\!\left(\frac{n\pi a}{L}\right)$$

振幅按 $1/n^2$ 衰减 → 高次谐波弱；$\sin(n\pi a/L)$ 中含拨弦位置 $a$，$a$ 处于某模态节点时该模态**完全不激发**——吉他手把握位置控制音色的物理根据。

### 弦的谐波受迫响应

单点简谐力 $F\,e^{i\omega t}$ 施在 $x=a$：分区间构造 $U(x) = A\sin(\omega x/c),\ x<a;\ B\sin(\omega(L-x)/c),\ x>a$，由连续性 + 力平衡解 $A, B$：

$$A = \frac{Fc}{\omega P}\cdot\frac{\sin(\omega(L-a)/c)}{\sin(\omega L/c)}$$

**共振** $\omega_n L/c = n\pi$；但当 $\sin(\omega_n a/c) = 0$（即 $a$ 恰好在该模态节点）时不激发——**"无损"共振被驱动位置抵消**。无阻尼系统的极点位于虚轴 → **边缘稳定**（见 [[stability]]），扰动后无衰减振动持续下去。

### Euler-Bernoulli 弯曲梁

含惯性和弯曲刚度：

$$\rho A\,\ddot y + EI\,y'''' = f(x,t)$$

四阶 PDE → **需 4 个边界条件**。分离变量得 $EI\,U'''' = \rho A\omega^2 U$，通解：

$$U(x) = D_1 e^{ikx} + D_2 e^{-ikx} + D_3 e^{kx} + D_4 e^{-kx}$$

$k^4 = \omega^2\,\rho A/EI$。前两项是**传播波**；后两项是**衰减波（evanescent waves）**——不传播，只在边界附近局部影响。梁与弦的关键差别就在这两个衰减模式，也导致梁的 $\omega_n \propto n^2$（不是 $n$）。

### 边界条件类型

| 类型 | 条件（在 $x=0$） |
|---|---|
| **Clamped**（夹紧） | $y = 0$，$y' = 0$（无位移、无转角） |
| **Pinned**（铰接） | $y = 0$，$EI\,y'' = 0$（无位移、无弯矩） |
| **Free**（自由） | $EI\,y'' = 0$，$EI\,y''' = 0$（无弯矩、无剪力） |

### 常见梁的模态

- **Pinned-Pinned**：$\omega_n = (n\pi/L)^2\sqrt{EI/(\rho A)}$，模态 $U_n = \sin(n\pi x/L)$（与弦形状相同，但频率间距不等）
- **Free-Free**：$\cos kL\cosh kL = 1$
- **Clamped-Free**（悬臂）：$\cos kL\cosh kL = -1$，$k_n L \approx (n-1/2)\pi$

### 连续系统的传递函数

极限 $N\to\infty$：

$$G(x, y, \omega) = \sum_{n=1}^{\infty} \frac{u_n(x)\,u_n(y)}{\omega_n^2 - \omega^2} \qquad (\text{无阻尼})$$

$$G(x, y, \omega) \approx \sum_n \frac{u_n(x)\,u_n(y)}{\omega_n^2 + 2i\zeta_n\omega_n\omega - \omega^2} \qquad (\text{加轻阻尼})$$

模态必须**质量归一化**：$\int_0^M u_n^2(x)\,dm = 1$，且**M-正交**：$\int u_n u_m\,dm = 0$（$n\neq m$）。冲激响应 $g \approx \sum_n \tfrac{u_n(x)u_n(y)}{\omega_n}\,e^{-\zeta_n\omega_n t}\sin(\omega_n t)$——每模态一衰减正弦。

### 连接耦合系统

两系统在一点连接：**位移相等 + 力和为外力**：

$$G_{\text{combined}} = \frac{G_1 G_2}{G_1 + G_2}$$

- 峰位于 $G_1 = -G_2$
- 反共振位于 $G_1 = 0$ 或 $G_2 = 0$
- $|G_1|\gg|G_2|$ 时 $G\approx G_1$（弱子系统被主导）
- 相同子系统 $G_1 = G_2$：$G = G_1/2$，反对称模态（在耦合点有节点）从频响消失

### 音叉底部握住的例子

音叉主要模式是两臂反对称摆动（左右对称的向内向外）。**次要**上下振动是主振动的**倍频**（两次左右 = 一次上下）。当底部按到桌面上，这个上下振动传给桌面激发桌面振动 → 声音**变强且高一个八度**。

### 连续系统的离散近似

工程实际中往往用**离散方法逼近连续系统**：

| 方法 | 思路 |
|---|---|
| **集中质量** | 分成小段，每段视为质点 + 无质量弹簧 |
| **模态截断** | 保留前 $n$ 个模态（低频精度好，高频略去）|
| **Galerkin** | 假设形状函数线性叠加，系数为自由度 |
| **有限元法（FEM）** | 划分小段 + 每段假设形状函数 + 拼接 |

低频模态 → 离散近似最准确；高频模态误差累积。

## 关联概念

- [[small-vibrations]] — 有限维版本；连续化即 $N\to\infty$
- [[partial-differential-equations]] — 波动方程/热方程等背景
- [[eigendecomposition]] — 模态就是无限维算子的谱
- [[vibration-transfer-functions]] — 频响的一般理论，本页给出连续版
- [[functional-spaces]] — 模态构成的 Hilbert 空间基
- [[stability]] — 无阻尼系统的极点在虚轴
