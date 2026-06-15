---
summary: HMM 是含离散隐状态序列的概率时序模型，通过状态转移概率和发射概率建模。前向算法计算似然，Viterbi 算法找最优路径。
tags: [machine-learning, probabilistic-models, sequence-model]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-hidden-markov-model-hidden-markov-model.md
  - raw/machine-learning/2026-06-08-hidden-markov-model-hmm-forward-algorithm.md
  - raw/machine-learning/2026-06-08-hidden-markov-model-viterbi-approximation.md
  - raw/machine-learning/2026-06-08-hidden-markov-model-emitting-state.md
---

# 隐马尔可夫模型（HMM）

## 定义

假设存在隐状态序列 $s$（未知）和观测序列 $x$（已知），系统遵循状态转移概率 $P(s_t|s_{t-1})$ 和发射概率 $P(x_t|s_t)$。数据似然：
$$p(x_1, \dots, x_T) = \sum_{\mathbf{s}} p(s_0) \prod_{t=1}^T P(s_t|s_{t-1}) p(x_t|s_t)$$

参数：状态转移矩阵 $A$、发射概率 $b_j(x_t)$、初始状态概率 $p(s_0)$。

## 关键点

**前向算法**：定义前向变量 $\alpha_t(j) = p(x_1, \dots, x_t, q_t = s_j)$，递推：
$$\alpha_t(j) = \sum_{i=1}^N \alpha_{t-1}(i) A_{ij} b_j(x_t)$$
总似然 $p(\mathbf{x}_T|\theta) = \sum_i \alpha_T(i)$。动态规划思想：任何在时刻 $t$ 到达状态 $s_j$ 的路径必从某个 $s_k$ 转移而来。

**Viterbi 近似**：只保留最优路径而非对所有路径求和：$\hat{q} = \arg\max_q p(x, q)$。给出似然的下界和最优状态序列。

**发射状态 vs 静默状态**：发射状态产生可观测输出，静默状态不产生。

## 关联概念

- [[graphical-model]] — HMM 是具有时序链结构的贝叶斯网络
- [[expectation-maximisation]] — Baum-Welch 算法（HMM 的 EM）用于参数估计
