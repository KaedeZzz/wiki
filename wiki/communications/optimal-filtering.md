---
summary: Wiener 滤波在 WSS 假设下最小化 E[(d-d̂)²]，给出 H(e^{jΩ})=S_{xd}/S_x（时域为 Wiener-Hopf 方程 h*r_{xx}=r_{xd}）；Matched Filter 在白噪声下最大化 SNR，h_opt ∝ 时间反转的信号本身；两者都可通过设计问题的优化视角推广。
tags: [communications, filter-design, optimal]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-filter-design-wiener-filter.md
  - raw/communications/2026-07-08-filter-design-fir-wiener-filter.md
  - raw/communications/2026-07-08-filter-design-wiener-hopf-equations.md
  - raw/communications/2026-07-08-filter-design-matched-filter.md
  - raw/communications/2026-07-08-filter-design-uncorrelated-signal-filter.md
  - raw/communications/2026-07-08-filter-design-optimal-filtering.md
  - raw/communications/2026-07-08-filter-design-filter-design-by-optimisation.md
---

# 最优滤波

## 定义

不再从"频率规范 → 系数"设计（[[fir-and-iir-filters]]），而是把滤波器系数当作**优化变量**，直接最小化/最大化某种**统计目标**。

- **Wiener 滤波**：$\min$ 均方误差
- **Matched 滤波**：$\max$ 输出 SNR

## 关键点

### Wiener 滤波问题

观测 $x_n = d_n + v_n$（目标信号 + 噪声）。设计线性滤波器 $\{h_p\}$：

$$\hat d_n = \sum_p h_p\,x_{n-p}$$

**目标**：最小化均方误差

$$J = \mathbb{E}[\epsilon_n^2] = \mathbb{E}[(d_n - \hat d_n)^2]$$

**假设**：$\{x_n\}$ 和 $\{d_n\}$ **联合 WSS** 且零均值——所有 [[random-processes]] 相关函数只依赖时间差。

### 正交性原理与 Wiener-Hopf 方程

对每个 $h_q$ 求 $J$ 的偏导 $= 0$：

$$\mathbb{E}[2\epsilon_n\,x_{n-q}] = 0 \quad \forall q$$

即**误差 $\epsilon_n$ 与所有观测正交**——**正交性原理**（最优估计的一般刻画，见 [[estimation-theory]]）。

代入 $\epsilon_n$：

$$\mathbb{E}[d_n\,x_{n-q}] - \sum_p h_p\,\mathbb{E}[x_{n-p}\,x_{n-q}] = 0$$

化为**Wiener-Hopf 方程**：

$$\sum_p h_p\,r_{xx}[q - p] = r_{xd}[q]$$

即 $h * r_{xx} = r_{xd}$——用**输入自相关**和**互相关**（[[power-spectral-density]]）求解 $h$。

### 频域解

对上式做 [[fourier-transform]]：

$$H(e^{j\Omega})\,S_x(e^{j\Omega}) = S_{xd}(e^{j\Omega})$$

$$\boxed{H(e^{j\Omega}) = \frac{S_{xd}(e^{j\Omega})}{S_x(e^{j\Omega})}}$$

**最优滤波器就是互功率谱与输入功率谱之比**——极其简洁。

**最小 MSE**：

$$J_{\min} = r_{dd}[0] - \sum_p h_p\,r_{xd}[p]$$

### 非因果 vs FIR Wiener

- **理想 Wiener**：允许 $h_p$ 从 $-\infty$ 到 $+\infty$（**非因果**）——工程上不能实时实现，只能离线处理
- **因果 Wiener**：限制 $h_p = 0$ for $p < 0$；求解需谱分解 + 因果分离
- **FIR Wiener**：限制 $\{h_p\}_{p=0}^{L-1}$ 有限长——变成**有限维正规方程** $\mathbf{R}_{xx}\mathbf{h} = \mathbf{r}_{xd}$（Toeplitz 系统，可用 Levinson-Durbin 算法 $O(L^2)$ 求解）

**FIR Wiener 是实时应用（自适应滤波、噪声消除、回声抵消）的实际形式**。

### 特殊情况：不相关信号

若 $d_n$ 和 $v_n$ **不相关**（$r_{dv} = 0$），则 $r_{xd} = r_{dd}$ 且 $r_{xx} = r_{dd} + r_{vv}$：

$$H(e^{j\Omega}) = \frac{S_d}{S_d + S_v}$$

- 目标信号强的频段（$S_d \gg S_v$）→ $H \approx 1$（保留）
- 噪声主导频段（$S_v \gg S_d$）→ $H \approx 0$（抑制）

**Wiener 是"频域信噪比加权"的最优形式**——这是所有信号增强算法（谱减法、维纳降噪、图像去噪）的理论基石。

### Matched 滤波（检测问题）

**问题**：在噪声中检测已知波形 $\{s_n\}$。观测 $x_n = s_n + v_n$。设计 $h$ 使输出

$$y_{N-1} = \sum_{m=0}^{N-1} h_m\,x_{N-1-m} = \mathbf{h}^T\tilde{\mathbf{x}}$$

（$\tilde{\mathbf{x}}$ 时间反转）的**输出 SNR** 最大：

$$\text{SNR} = \frac{|\mathbf{h}^T \tilde{\mathbf{s}}|^2}{\mathbb{E}[|\mathbf{h}^T \tilde{\mathbf{v}}|^2]}$$

### 白噪声下的 Matched 滤波器

假设 $v_n$ 白噪声、方差 $\sigma_v^2$：$\mathbb{E}[\tilde{\mathbf{v}}\tilde{\mathbf{v}}^T] = \sigma_v^2\mathbf{I}$。分子

$$|\mathbf{h}^T\tilde{\mathbf{s}}|^2 = \mathbf{h}^T\,(\tilde{\mathbf{s}}\tilde{\mathbf{s}}^T)\,\mathbf{h}$$

$\tilde{\mathbf{s}}\tilde{\mathbf{s}}^T$ 是**秩 1**矩阵，唯一非零特征值 $\lambda = \tilde{\mathbf{s}}^T\tilde{\mathbf{s}}$，特征向量 $\mathbf{e}_0 = \tilde{\mathbf{s}}/\|\tilde{\mathbf{s}}\|$。所以最大化 SNR 的 $\mathbf{h}$ 方向必须**平行 $\tilde{\mathbf{s}}$**：

$$\boxed{\mathbf{h}_{\text{opt}} = \frac{\tilde{\mathbf{s}}}{\|\tilde{\mathbf{s}}\|},\qquad \text{SNR}_{\text{opt}} = \frac{\|\mathbf{s}\|^2}{\sigma_v^2}}$$

**Matched Filter = 信号的时间反转**——直觉：**"用信号自身作为模板做相关"**。信号能量与噪声方差之比 = 最大 SNR，与信号形状无关（只要能量固定）。

**应用**：雷达（脉冲压缩）、通信（符号检测）、GPS（PN 码相关）、生物信息（模板匹配）——但凡"找已知模板"，Matched Filter 是理论最优。

### Wiener vs Matched 对比

|  | Wiener | Matched |
|---|---|---|
| 目标 | 估计 $d_n$（回归） | 检测/检出 $s_n$（分类） |
| 优化 | $\min$ MSE | $\max$ SNR |
| 假设 | WSS 统计 | 已知波形 + 白噪声（可推广） |
| 输出 | 信号估计 $\hat d_n$ | 检测统计量 |

### 通用优化视角

**滤波器设计 by 优化**：把任何滤波器目标（频响误差、群延迟平滑、旁瓣抑制…）写成 $\{h_k\}$ 的凸/非凸目标 → 用凸优化工具求解。**Parks-McClellan / Remez 算法**（等纹波 FIR 设计）是这种视角的经典实例；现代深度学习里的**学习滤波器**也是同样思路的非线性推广。

## 关联概念

- [[power-spectral-density]] — Wiener 频域解直接使用 PSD
- [[random-processes]] — WSS 假设的背景
- [[estimation-theory]] — 正交性原理与 MMSE 估计
- [[eigendecomposition]] — Matched 滤波的秩 1 分析
- [[fir-and-iir-filters]] — 结构上仍是数字滤波器
- [[discrete-state-space-and-particle-filter]] — 时序 Bayesian 最优估计（Kalman 是线性高斯的另一路）
- [[kalman-filter]] — Wiener 的时序推广（含状态方程与非平稳假设）
- [[hypothesis-testing]] — Matched 滤波背后的检测理论
