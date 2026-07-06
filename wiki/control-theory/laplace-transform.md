---
summary: Laplace 变换把时域函数 f(t) 映射到复频域 F(s)，是连续 LTI 系统分析的核心工具：微分方程 → 代数方程，传递函数在此定义。
tags: [control-theory, transforms]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-laplace-transform-laplace-transform.md
---

# Laplace 变换

## 定义

单边 Laplace 变换（假设 $f(t)$ 在 $t\geq 0^+$ 上非零）：

$$F(s)=\int_0^{\infty} f(t)\,e^{-st}\,dt$$

其中 $s=\sigma+j\omega$ 是复变量。

## 关键点

- **主要用途**：把线性常系数微分方程转化为 $s$ 域的代数方程；由此定义连续时间 LTI 系统的 [[transfer-function]] $G(s)=Y(s)/U(s)$。
- **分析瞬态响应**：通过检查 $G(s)$ 的极点在 $s$ 平面上的位置判断系统的暂态衰减/振荡行为，进而给出连续时间稳定性判据（见 [[stability]] 的 s 平面版本）。
- **与其他变换的关系**：
  - 令 $s=j\omega$ → **Fourier 变换**（傅立叶变换是 Laplace 变换在虚轴上的取值），此即 [[frequency-response]] 的来源。
  - 双边 Laplace 变换即 [[generating-functions]] 中的**矩生成函数** $M_X(-t)$。
  - 离散时间对应物是 z 变换（见 [[z-transform-discrete-systems]]），关系 $z=e^{sT}$（采样周期 $T$）。

## 关联概念

- [[transfer-function]] — Laplace 域中定义的输入-输出比
- [[z-transform-discrete-systems]] — 离散时间对应物
- [[frequency-response]] — Bode 图是 $G(j\omega)$ 的可视化
- [[generating-functions]] — 概率中的 MGF 是双边 Laplace 变换的伪装形式
- [[state-space-model]] — $\Phi(t)=e^{At}$ 通过 $\mathcal{L}^{-1}\{(sI-A)^{-1}\}$ 计算
