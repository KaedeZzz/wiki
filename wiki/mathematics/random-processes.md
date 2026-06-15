---
summary: 随机过程是以时间为索引的随机变量族，描述随机系统的动态演化；核心概念包括平稳性、遍历性、白噪声和功率谱密度。
tags: [mathematics, probability, stochastic-processes]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-random-processes-basics.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-stationarity.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-ergodicity.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-white-noise.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-psd.md
---

# 随机过程

## 定义

随机过程（random process）是一族以索引集 $T$ 为参数的随机变量 $\{X_t : t \in T\}$。当 $T$ 为可数集（如 $\mathbb{Z}$）时称为离散时间随机过程；当 $T$ 为连续集（如 $\mathbb{R}$）时称为连续时间随机过程。对每个固定的 $t$，$X_t$ 是一个随机变量；对每个固定的样本 $\omega$，$X_t(\omega)$ 是一条实现（realization）。

## 关键点

### 平稳性

- **严平稳（strict-sense stationary）**：对任意时移 $\tau$，联合分布不变，即 $(X_{t_1}, \dots, X_{t_n})$ 与 $(X_{t_1+\tau}, \dots, X_{t_n+\tau})$ 同分布。
- **宽平稳（wide-sense stationary, WSS）**：
  1. 均值为常数：$E[X_t] = \mu$
  2. 方差有限：$\text{Var}(X_t) < \infty$
  3. 自相关仅依赖于时滞：$R_{XX}(t_1, t_2) = R_{XX}(t_1 - t_2)$

严平稳蕴含宽平稳（当二阶矩存在时），但反之不成立。

### 遍历性

遍历性（ergodicity）指单条实现的时间平均等于集合（ensemble）平均：

$$\lim_{N\to\infty} \frac{1}{2N+1}\sum_{n=-N}^{N} X_n = E[X_t] \quad \text{a.s.}$$

**均值遍历定理**：WSS 过程均值遍历的充分条件是自协方差序列趋于零：

$$\lim_{N\to\infty} c_{XX}[N] = 0$$

其中 $c_{XX}[N] = \frac{1}{2N+1}\sum_{k=-N}^{N}\left(1 - \frac{|k|}{2N+1}\right) C_{XX}(k)$。

### 白噪声

白噪声 $\{W_t\}$ 是均值为零、自相关为冲激的 WSS 过程：

$$R_W(k) = \sigma^2 \delta_{0,k}$$

其功率谱密度为常数 $\Phi_{WW}(\theta) = \sigma^2$（"白"即频谱平坦）。

**白高斯噪声（WGN）**：白噪声且每个时刻 $W_t \sim \mathcal{N}(0, \sigma^2)$。WGN 是严平稳的（高斯分布由前两阶矩完全确定）。

### 功率谱密度

功率谱密度（PSD）是自相关序列的离散时间傅里叶变换：

$$\Phi_{XX}(\theta) = \sum_{n=-\infty}^{\infty} r_{XX}(n)\, e^{-jn\theta}$$

反变换：$r_{XX}(n) = \frac{1}{2\pi}\int_{-\pi}^{\pi} \Phi_{XX}(\theta)\, e^{jn\theta}\, d\theta$

PSD 是非负实函数，描述信号功率在频率上的分布。

## 关联概念

- [[markov-chain]] — 满足马尔可夫性质的特殊随机过程
- [[time-series-analysis]] — 对随机过程观测值的统计建模与预测
- [[expectation-and-moments]] — 随机过程的均值函数和自相关函数依赖期望与矩
