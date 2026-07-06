---
summary: Kalman 滤波器是线性高斯状态空间模型下滤波密度 p(x_t|y_{1:t}) 的闭式递推，交替执行"预测（先验传播）"与"更新（用观测修正）"，最优性来自高斯共轭。
tags: [control-theory, bayesian-inference, state-estimation]
updated: 2026-07-06
sources:
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-kalman-filter.md
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-kalman-gain.md
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-derivation-of-kalman-filter.md
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-filtering-density-recursion.md
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-extended-kalman-filter.md
  - raw/control-theory/2026-07-06-state-space-control-kalman-filter-prediction-error-decomposition.md
---

# Kalman 滤波器

## 定义

对线性高斯 [[state-space-model]]：

$$\mathbf{x}_t = \mathbf{A}\mathbf{x}_{t-1} + \mathbf{v}_t,\quad \mathbf{v}_t\sim\mathcal{N}(\mathbf{0},\mathbf{\Sigma}_v)$$
$$\mathbf{y}_t = \mathbf{B}\mathbf{x}_t + \mathbf{w}_t,\quad \mathbf{w}_t\sim\mathcal{N}(\mathbf{0},\mathbf{\Sigma}_w)$$

**Kalman 滤波器**给出**滤波密度** $p(\mathbf{x}_t|\mathbf{y}_{1:t})$ 的闭式递推。它是这一模型下的贝叶斯最优状态估计器。

## 关键点

### 滤波密度递推（一般形式）

由贝叶斯法则（[[posterior-distribution]]）与 Markov 假设（[[markov-chain]]）：

$$p(\mathbf{x}_t|\mathbf{y}_{1:t}) \propto p(\mathbf{y}_t|\mathbf{x}_t) \int p(\mathbf{x}_t|\mathbf{x}_{t-1})\, p(\mathbf{x}_{t-1}|\mathbf{y}_{1:t-1})\, d\mathbf{x}_{t-1}$$

拆成两步：

1. **预测**：$p(\mathbf{x}_t|\mathbf{y}_{1:t-1}) = \int p(\mathbf{x}_t|\mathbf{x}_{t-1})\,p(\mathbf{x}_{t-1}|\mathbf{y}_{1:t-1})\,d\mathbf{x}_{t-1}$
2. **更新**：$p(\mathbf{x}_t|\mathbf{y}_{1:t}) \propto p(\mathbf{y}_t|\mathbf{x}_t)\,p(\mathbf{x}_t|\mathbf{y}_{1:t-1})$

这与 [[hidden-markov-model]] 的前向递推同构，只是隐状态从离散变为连续高斯。

### 线性高斯闭式解

在高斯先验+线性高斯似然下，所有密度保持高斯，只需追踪均值与协方差。Kalman 滤波器方程：

**预测**：
$$\boldsymbol{\mu}_{t|t-1} = \mathbf{A}\boldsymbol{\mu}_{t-1|t-1}$$
$$\mathbf{P}_{t|t-1} = \mathbf{A}\mathbf{P}_{t-1|t-1}\mathbf{A}^T + \mathbf{\Sigma}_v$$

**Kalman 增益**：
$$\mathbf{K}_t = \mathbf{P}_{t|t-1}\mathbf{B}^T (\mathbf{B}\mathbf{P}_{t|t-1}\mathbf{B}^T + \mathbf{\Sigma}_w)^{-1}$$

**更新**：
$$\boldsymbol{\mu}_{t|t} = \boldsymbol{\mu}_{t|t-1} + \mathbf{K}_t (\mathbf{y}_t - \mathbf{B}\boldsymbol{\mu}_{t|t-1})$$
$$\mathbf{P}_{t|t} = (\mathbf{I}-\mathbf{K}_t\mathbf{B})\mathbf{P}_{t|t-1}$$

### Kalman 增益的解读

$\mathbf{K}_t$ 回答：*"给定观测空间中一个偏差 $\mathbf{y}_t-\mathbf{B}\boldsymbol{\mu}_{t|t-1}$，我应该把状态估计沿状态空间的哪个方向、移动多少？"*

- $\mathbf{\Sigma}_w$ 大（观测噪声大）→ $\mathbf{K}_t$ 小 → 相信模型预测。
- $\mathbf{P}_{t|t-1}$ 大（先验不确定）→ $\mathbf{K}_t$ 大 → 相信观测。

结构上，Kalman 增益就是[[linear-gaussian-model]]中"高斯先验 + 高斯似然 → 高斯后验"的条件化公式在时序上的循环应用。

### 扩展 Kalman 滤波器（EKF）

对非线性状态空间

$$\mathbf{x}_t = A(\mathbf{x}_{t-1}) + \mathbf{v}_t,\quad \mathbf{y}_t = B(\mathbf{x}_t) + \mathbf{w}_t$$

在当前均值处对 $A, B$ 做一阶 Taylor 展开，得到线性化系统后套用标准 Kalman 方程。非线性强或后验高度非高斯时精度不足，此时可转向粒子滤波（属 [[monte-carlo-methods]] 家族）。

### 预测误差分解（用于参数估计）

由观测模型经高斯变换：

$$p(\mathbf{y}_{t+1}|\mathbf{y}_{1:t}) = \mathcal{N}(\mathbf{y}_{t+1};\, \mathbf{B}\boldsymbol{\mu}_{t+1|t},\, \mathbf{B}\mathbf{P}_{t+1|t}\mathbf{B}^T + \mathbf{\Sigma}_w)$$

由概率乘法链式法则得完整似然：

$$p(\mathbf{y}_{1:T}) = p(\mathbf{y}_1)\prod_{t=1}^{T-1} p(\mathbf{y}_{t+1}|\mathbf{y}_{1:t})$$

每步在 Kalman 递推中即可算出增量似然，累加得总似然，随后可对参数 $\theta$（如 $A, B, \Sigma_v, \Sigma_w$）做 ML 或 MAP 估计（见 [[estimation-theory]]）。

## 关联概念

- [[state-space-model]] — 滤波器所作用的动力学模型
- [[hidden-markov-model]] — 离散隐状态版本；Kalman 是 HMM 前向递推在连续高斯下的对应物
- [[linear-gaussian-model]] — 高斯共轭条件化公式是 Kalman 更新步的基石
- [[gaussian-distribution]] — 条件、边缘、线性变换后仍为高斯
- [[posterior-distribution]] — 滤波密度 = 到当前时刻观测为止的后验
- [[markov-chain]] — 状态方程的 Markov 性质使递推成立
- [[monte-carlo-methods]] — 非线性/非高斯情形下的粒子滤波替代方案
- [[estimation-theory]] — 通过预测误差分解做参数 ML/MAP 估计
