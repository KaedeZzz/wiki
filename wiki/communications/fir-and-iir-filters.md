---
summary: FIR y_n=Σ h_k u_{n-k} 是有限长冲激响应、极点全在原点、内在稳定、可精确线性相位，但需高阶。IIR 有反馈 → 无限冲激、更低阶但可能不稳定。设计 FIR 常用窗方法；IIR 常从模拟原型（Butterworth）经双线性变换获得。
tags: [communications, filter-design, digital-filter]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-discrete-basics-fir-and-iir.md
  - raw/communications/2026-07-08-discrete-basics-properties-of-fir-and-iir.md
  - raw/communications/2026-07-08-discrete-digital-filtering-fir-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-iir-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-iir-design.md
  - raw/communications/2026-07-08-discrete-digital-filtering-butterworth-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-window-methods.md
  - raw/communications/2026-07-08-filter-design-filtering-windows.md
  - raw/communications/2026-07-08-discrete-digital-filtering-fir-design-of-lowpass-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-achieving-linear-phase-for-fir-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-ideal-lowpass-delta-response.md
  - raw/communications/2026-07-08-discrete-digital-filtering-effect-of-truncation-of-ideal-lowpass-filter.md
  - raw/communications/2026-07-08-discrete-digital-filtering-desired-frequency-responses.md
  - raw/communications/2026-07-08-discrete-digital-filtering-realizable-filter-specifications.md
  - raw/communications/2026-07-08-discrete-digital-filtering-band-transformations.md
  - raw/communications/2026-07-08-discrete-digital-filtering-transformations-of-different-filter-types.md
  - raw/communications/2026-07-08-discrete-digital-filtering-hybrid-analog-digital-systems.md
  - raw/communications/2026-07-08-discrete-digital-filtering-digital-filtering.md
  - raw/communications/2026-07-08-filter-design-fir-and-iir-filter.md
---

# FIR 与 IIR 数字滤波器

## 定义

**数字滤波器**：离散 LTI 系统（见 [[signals-and-lti-systems]]），由差分方程给出输出：

$$y_n = -a_1 y_{n-1} - \dots - a_p y_{n-p} + b_0 u_n + b_1 u_{n-1} + \dots + b_q u_{n-q}$$

**FIR**（Finite Impulse Response）：$a_i = 0$，输出只依赖有限个过去输入 → 冲激响应 $\{h_k\}$ 有限长。

**IIR**（Infinite Impulse Response）：有反馈项 → 冲激响应无限长。

## 关键点

### FIR 与 IIR 的性质对比

| 属性 | FIR | IIR |
|---|---|---|
| 冲激响应 | 有限长 $\{g_0,\dots,g_l,0,0,\dots\}$ | 无限长 |
| 传递函数 | $G(z) = \tfrac{b_0 z^m + \dots + b_m}{z^m}$ | $G(z) = \tfrac{b(z)}{a(z)}$，$\deg a > 0$ |
| 极点 | **全部在 $z=0$** | 由 $a(z) = 0$ 决定 |
| 稳定性 | **总是稳定**（无极点在单位圆外） | 需检查极点在 $|z| < 1$ |
| 相位 | **可精确线性** | 一般非线性 |
| 实现效率 | 高阶（多系数）→ 可能高延迟 | 低阶达到同样性能 |
| 设计难度 | 简单（线性方法） | 复杂（非线性，多从模拟原型转） |

**线性相位**（FIR 独有）：$G(e^{j\theta}) = |G(e^{j\theta})|\,e^{-j\alpha\theta}$——所有频率延迟相同 → **保信号波形形状**。语音、雷达、通信里需要"相干"处理时必须。达成条件：系数 $\{h_k\}$ 对称或反对称。

### FIR 的窗方法设计

**核心步骤**：

1. 指定**理想**频响 $H_d(e^{j\theta})$（如理想低通：矩形通带）
2. 逆 DTFT 得理想（**无限长、非因果**）冲激响应 $h_d[n]$
3. 用**窗函数** $w[n]$（有限长）截断：$h[n] = h_d[n]\,w[n]$
4. 加延迟使其**因果**：$h_{\text{final}}[n] = h[n - N/2]$
5. 验证频响是否满足指标，不满足则迭代

**理想低通冲激响应**：$h_d[n] = \tfrac{\sin(\theta_c n)}{\pi n}$（sinc 函数，无限长且缓慢衰减）。

**窗函数的选择**（常用）：

| 窗 | 主瓣宽度 | 旁瓣电平 |
|---|---|---|
| 矩形（直接截断） | 窄 | 差（约 $-13$ dB） |
| Hann（$\cos^2$） | 中 | $-31$ dB |
| Hamming | 中 | $-41$ dB |
| Blackman | 宽 | $-58$ dB |
| Kaiser（可调 $\beta$） | 可调 | 可调 |

**折衷**：窄主瓣（陡过渡带）需要弱旁瓣抑制；两者不可兼得（Heisenberg-Gabor 的时频对应，见 [[fourier-transform]]）。

### 截断的影响

直接矩形截断 → **Gibbs 现象**：在通带-阻带过渡处出现约 $9\%$ 过冲，即使增加长度过冲振幅也不减小（宽度变窄但幅度不变）——这就是矩形窗旁瓣差的直接后果。换 Hann/Hamming/Kaiser 窗即可**用主瓣加宽换旁瓣压低**。

### 可实现滤波器规范

真实滤波器不可能是理想矩形。工程指标通常用**四段规范**：

- **通带纹波**：$1 - \delta_p \leq |G| \leq 1 + \delta_p$，$\theta \in [0, \theta_p]$
- **过渡带**：$\theta \in [\theta_p, \theta_s]$，无要求
- **阻带衰减**：$|G| \leq \delta_s$，$\theta \in [\theta_s, \pi]$

**过渡带宽度** $\theta_s - \theta_p$ 越窄 → 需要**滤波器阶数越高**（成本更高、延迟更大）。

### 常见带型间的变换

先设计**低通原型**，再通过 $z$ 域**代数变换**得到高通/带通/带阻：

| 目标 | 变换（从低通到目标） |
|---|---|
| 高通 | $z^{-1} \to -z^{-1}$（谱翻转） |
| 带通 | $z^{-1} \to \tfrac{z^{-2} - \alpha z^{-1} + \beta}{\beta z^{-2} - \alpha z^{-1} + 1}$ |
| 带阻 | 类似双线性代数变换 |

只需**一个低通设计工具箱**+ 变换表 → 覆盖所有带型。

### IIR 的经典设计路线

不像 FIR 有直接的窗方法，IIR 通常是**从模拟原型转换**：

1. 设计连续时间原型 $G_c(s)$（Butterworth / Chebyshev / Elliptic 等）
2. 用**双线性变换**（见 [[sampling-and-a-d-conversion]]）映射 $s = (2/T)\,(z-1)/(z+1)$
3. 预扭曲截止频率补偿双线性的 $\tan(\theta/2)$ 扭曲

### Butterworth 滤波器（经典模拟原型）

$N$ 阶低通：

$$|G_c(j\omega)|^2 = \frac{1}{1 + (\omega/\omega_c)^{2N}}$$

或用极点：

$$G_c(s)G_c(-s) = \frac{1}{1 + (s/(j\omega_c))^{2N}}$$

**性质**：

- **通带最平坦**（在 $\omega = 0$ 处所有导数为零；无纹波）
- $|G_c(j\omega_c)| = 1/\sqrt{2}$（$-3$ dB 截止频率）
- **阶数越高，过渡越陡**：过 $\omega_c$ 后衰减 $-20N$ dB/十倍频

**极点位置**：$s = j\omega_c\,e^{j(2k+1)\pi/(2N)}$——分布在 $s$ 平面上圆心原点、半径 $\omega_c$ 的圆周上。取**左半平面**的 $N$ 个作为 $G_c(s)$ 的极点（右侧对称的属于 $G_c(-s)$）。

$$G_c(s) = \prod_{i=1}^{N}\frac{1}{s + p_i},\quad p_i \in \text{左半平面圆弧}$$

其他经典模拟原型：**Chebyshev-I**（通带纹波、更陡）、**Chebyshev-II**（阻带纹波）、**Elliptic**（通阻带均纹波、最陡）——工程中按容忍纹波换取阶数下降。

### 混合模拟-数字系统

某些系统是**模拟前端**（如放大器 + 抗混叠滤波器）+ **数字后端**（DSP 处理）。总体传递函数是级联；分析时把模拟部分做双线性映射后与数字部分合并即可。

## 关联概念

- [[signals-and-lti-systems]] — FIR/IIR 都是离散 LTI 特例
- [[z-transform]] — 传递函数与稳定性判据的域
- [[sampling-and-a-d-conversion]] — IIR 通过双线性变换来自模拟原型
- [[fourier-transform]] — 频响与窗函数的 Gibbs 现象
- [[discrete-fourier-transform-and-fft]] — 长 FIR 用 Overlap-Save 加速
- [[stability]] — IIR 极点位置判定
- [[frequency-response]] — 滤波指标的频域可视化
- [[optimal-filtering]] — Wiener/Matched 是特定意义下的最优滤波器
