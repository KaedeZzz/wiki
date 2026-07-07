---
summary: 状态空间模型 x_{t+1}~f(x_{t+1}|x_t), y_t~g(y_t|x_t) 是 HMM 的连续状态版本；Kalman 滤波是线性高斯下的闭式解，粒子滤波（SMC）用蒙特卡洛样本近似非线性/非高斯情形的滤波密度，并通过重要性重采样避免粒子退化。
tags: [communications, state-space, sequential-monte-carlo]
updated: 2026-07-08
sources:
  - raw/communications/2026-07-08-state-space-models-state-space-model.md
  - raw/communications/2026-07-08-state-space-models-particle-filtering.md
---

# 离散状态空间与粒子滤波

## 定义

**状态空间模型**（概率版本）：状态 $x_t \in \mathbb{R}^N$ 按 Markov 转移密度 $f(x_{t+1}|x_t)$ 演化（[[markov-chain]]），观测 $y_t$ 通过似然 $g(y_t|x_t)$ 与当前状态相关：

$$x_{t+1} \sim f(x_{t+1}|x_t),\qquad y_{t+1} \sim g(y_{t+1}|x_{t+1})$$

**滤波密度** $p(x_t|y_{1:t})$：给定到时刻 $t$ 为止所有观测下的状态后验分布。

**粒子滤波**：用**蒙特卡洛样本**（"粒子"）近似 $p(x_t|y_{1:t})$，通过重要性采样 + 重采样递推更新——适用于**非线性、非高斯**情形（这是 [[kalman-filter]] 覆盖不了的情形）。

## 关键点

### 与经典模型的关系

| 模型 | 状态空间 | 观测空间 | 关键推断算法 |
|---|---|---|---|
| **HMM** | 有限离散 | 离散/连续 | 前向-后向 |
| **Linear Gaussian SSM** | 连续 $\mathbb{R}^N$ | 连续，线性高斯 | [[kalman-filter]] |
| **Nonlinear/Non-Gaussian SSM** | 任意 | 任意 | 粒子滤波 |

粒子滤波是**最通用**但**最贵**的方案。

### 滤波密度递推

由贝叶斯定理与 Markov 性（参考 [[kalman-filter]] 的推导）：

**预测**：

$$p(x_t|y_{1:t-1}) = \int p(x_t|x_{t-1})\,p(x_{t-1}|y_{1:t-1})\,dx_{t-1}$$

**更新**：

$$p(x_t|y_{1:t}) \propto p(y_t|x_t)\,p(x_t|y_{1:t-1})$$

一般**积分无解析形式** → 粒子滤波用样本近似这些积分。

### 顺序重要性采样（SIS）

选一个**提议密度** $q_n(x_n|x_{1:n-1})$ 采样粒子，用重要性权重修正：

$$w_t^{(i)} \propto w_{t-1}^{(i)}\,\frac{p(y_t|x_t^{(i)})\,p(x_t^{(i)}|x_{t-1}^{(i)})}{q(x_t^{(i)}|x_{t-1}^{(i)}, y_t)}$$

**最优提议**（最小化权重方差）：

$$q^{\text{opt}}(x_n|x_{1:n-1}) = \frac{g(y_n|x_n)\,f(x_n|x_{n-1})}{p(y_n|x_{n-1})}$$

——通常不可采样。工程实际中用近似。

### Bootstrap 粒子滤波（最简单）

选择 $q = f(x_n|x_{n-1})$（就用状态转移作为提议）。则权重简化为：

$$\tilde w_t^{(i)} = w_{t-1}^{(i)}\,p(y_t|x_t^{(i)})$$

即"用状态先验采粒子、用观测似然更新权重"。**极其简单，是所有粒子滤波的基线**。

### 算法三步

**Step 1 - 预测**：对每个粒子 $x_{t-1}^{(i)}$，采样 $x_t^{(i)} \sim p(x_t|x_{t-1}^{(i)})$——获得表示 $p(x_t|y_{1:t-1})$ 的先验点云。

**Step 2 - 更新**：计算权重 $\tilde w_t^{(i)} = w_{t-1}^{(i)}\,p(y_t|x_t^{(i)})$；归一化 $w_t^{(i)} = \tilde w_t^{(i)} / \sum_j \tilde w_t^{(j)}$。加权点云表示 $p(x_t|y_{1:t})$。

**Step 3 - 重采样**（避免粒子退化）：随时间推移，大多数粒子权重变小、极少数占尽——**粒子退化**。用**有效样本数**（ESS）检测：

$$\text{ESS} = \frac{1}{\sum_i (w_t^{(i)})^2}$$

若 ESS $< N/2$（常用阈值），做**重采样**：按权重从当前粒子集有放回抽 $N$ 个作为新粒子集，权重复位为 $1/N$——粒子重新集中到可能性高的状态区域。

### 应用

- **目标跟踪**：雷达/视觉多目标追踪
- **机器人 SLAM**：非线性运动模型 + 非高斯传感器
- **金融量化**：随机波动率、跳跃扩散模型的滤波
- **生物信号**：呼吸/心跳的非平稳建模
- **信道估计**：无线通信中的时变信道跟踪

### 性能与陷阱

- **粒子数 $N$**：$N$ 越大越准，代价 $O(N)$/步
- **提议选择**：好的提议能大幅降低所需 $N$
- **重采样时机**：过频损失多样性，过疏加剧退化
- **粒子塌缩**：所有粒子挤到一个点 → 完全失去后验的多样性表达 → 用 MCMC 步骤或迁移动力学重生成粒子多样性
- **维度灾难**：状态维度高时朴素粒子滤波指数级低效——高维问题需要如 **Rao-Blackwellized PF**、**Auxiliary PF**、**变分粒子滤波**等改进

## 关联概念

- [[markov-chain]] — 状态转移的 Markov 结构
- [[hidden-markov-model]] — 离散状态的 SSM
- [[kalman-filter]] — 线性高斯下的闭式解；EKF 是本地线性化的粒子滤波替代
- [[monte-carlo-methods]] — SMC/SIS 建立在重要性采样之上
- [[posterior-distribution]] — 滤波密度是后验的时序版本
- [[state-space-model]] — 控制视角下的等价概念
- [[optimal-filtering]] — Wiener 是特殊线性高斯下的对应
