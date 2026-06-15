---
summary: 时间序列分析：将观测分解为趋势、季节性和残差，并用 AR/MA/ARMA 模型描述残差的随机结构。
tags: [mathematics, probability, time-series]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inference-time-series-analysisbasicstime-series.md
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inference-time-series-analysisbasicsauto-regressive-ar-process.md
  - raw/mathematics/2026-06-09-probability-theory-estimation-and-inference-time-series-analysisbasicsarma-process.md
  - raw/mathematics/2026-06-09-probability-theory-random-processeslinear-systemsmoving-average-ma-process.md
---

# 时间序列分析

## 定义

时间序列是按时间递增排列的观测序列 $y_n, n=0,1,\dots$，分析框架将其分解为：

$$Y_n = m_n + S_n + X_n$$

其中 $m_n$ 为趋势项，$S_n$ 为季节分量（周期正弦），$X_n$ 为零均值随机残差。

## 关键点

### AR 过程

自回归过程 $AR(p)$：

$$X_t = \sum_{i=1}^{p} a_i X_{t-i} + W_t$$

其中 $\{W_t\}$ 为白噪声。AR(1) 展开为离散卷积 $X_n = \sum_{k=0}^{\infty} W_{n-k} a^k$，当 $|a|<1$ 时为因果且宽平稳，方差 $\sigma^2/(1-a^2)$。

### MA 过程

滑动平均过程 $MA(q)$：

$$X_t = \sum_{i=1}^{q} b_i W_{t-i} + W_t$$

$MA(q)$ 天然为宽平稳。

### ARMA 过程

$ARMA(p,q)$ 结合两者：

$$X_t = \sum_{i=1}^{p} a_i X_{t-i} + \sum_{i=0}^{q} b_i W_{t-i}$$

可视为 LTI 系统受白噪声激励的输出。

### AR 过程作为 GLM

AR(p) 可写为广义线性模型 $\mathbf{x} = \mathbf{Ga} + \mathbf{e}$，其中 $\mathbf{G}$ 由历史观测值构成。

### 线性系统与频谱

对 LTI 系统，输出功率谱与输入的关系为：

$$\Phi_{YY}(\theta) = |H(\theta)|^2 \Phi_{XX}(\theta)$$

互谱密度：$\Phi_{XY}(\theta) = H(\theta)\Phi_{XX}(\theta)$

### 估计流程

1. 用最小二乘估计趋势 $\hat{m}_n$
2. 用正弦拟合估计季节分量 $\hat{S}_n$（$S_n = \alpha_1\cos(2\pi fn) + \alpha_2\sin(2\pi fn)$）
3. 对残差 $X_n = Y_n - \hat{m}_n - \hat{S}_n$ 建立 AR/MA/ARMA 模型

## 关联概念

- [[random-processes]] — 时间序列的概率论基础
- [[linear-gaussian-model]] — AR 过程可表示为 GLM
- [[estimation-theory]] — 参数估计方法
