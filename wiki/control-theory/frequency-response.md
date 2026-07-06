---
summary: 频率响应是传递函数在虚轴 s=jω（或单位圆 z=e^{jθ}）上的取值，用 Bode 图（幅频/相频）或 Nyquist 图可视化；增益裕度与相位裕度量化系统离不稳定的余量。
tags: [control-theory, frequency-domain]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-basics-bode-diagram.md
  - raw/control-theory/2026-07-06-basics-margins.md
---

# 频率响应

## 定义

**频率响应**：LTI 系统的 [[transfer-function]] 在虚轴上的取值——连续系统为 $G(j\omega)$，离散系统为 $G(e^{j\theta})$。因任意输入信号可分解为正弦分量之和（Fourier 视角），$G(j\omega)$ 完全表征系统对每个频率的稳态放大与相移。

## 关键点

### Bode 图

将频率响应的**幅值** $|G(j\omega)|$（通常对数 dB 坐标）与**相位** $\angle G(j\omega)$ 分别画成对数频率的函数。因为整个信号可分解为正弦之和，Bode 图是描述滤波器/系统行为的自然表达。

### 稳定裕度

裕度衡量系统离**闭环失稳**的余量——即当反馈回路增益或相位被扰动时，系统还能保持稳定多久。

- **增益裕度（Gain Margin）**：在 $\angle G(j\omega)=-180^\circ$ 的频率处，$|G|$ 距离穿越 $0$ dB（即幅值 $1$）还有多少 dB。
- **相位裕度（Phase Margin）**：在 $|G(j\omega)|=1$ 的频率处，$\angle G$ 距离 $-180^\circ$ 还有多少度。

裕度越大越"安全"，但过大意味着响应保守（慢）。它们与 [[nyquist-stability]] 中 Nyquist 轨迹距离 $-1$（对应 $K=1$）的最短距离/角度直接对应。

## 关联概念

- [[transfer-function]] — 频率响应就是 $G$ 在虚轴/单位圆上的取值
- [[laplace-transform]] — $s=j\omega$ 是 Laplace 域到频域的桥梁
- [[nyquist-stability]] — Nyquist 图是频率响应在复平面上的极坐标表示；裕度对应轨迹到临界点 $-1/K$ 的最短距离/角度
- [[stability]] — 裕度小 → 极点靠近稳定边界
