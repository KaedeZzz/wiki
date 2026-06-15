---
summary: 马尔可夫链是满足马尔可夫性质（未来仅依赖当前状态）的随机过程，其长期行为由转移矩阵的谱性质决定。
tags: [mathematics, probability, stochastic-processes]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-random-processes-markov-chain-basics.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-markov-chain-convergence.md
  - raw/mathematics/2026-06-09-probability-theory-random-processes-markov-chain-stationary.md
---

# 马尔可夫链

## 定义

马尔可夫链是满足**马尔可夫性质**的随机过程：给定当前状态，未来与过去条件独立：

$$P(X_t \mid X_{t-1}, X_{t-2}, \dots, X_0) = P(X_t \mid X_{t-1})$$

若转移概率不随时间变化，则称为**齐次（homogeneous）**马尔可夫链。

## 关键点

### 转移矩阵

齐次链的一步转移概率构成转移矩阵 $Q$：

$$Q_{ij} = P(X_{t+1} = j \mid X_t = i)$$

$Q$ 是行随机矩阵（每行之和为 1）。$n$ 步转移概率由 $Q^n$ 给出。

### 状态分类

- **可达（accessible）**：状态 $j$ 从 $i$ 可达，若存在 $n$ 使 $Q^n_{ij} > 0$。
- **互通（communicate）**：$i$ 与 $j$ 互相可达。互通是等价关系，将状态空间划分为互通类。
- **不可约（irreducible）**：所有状态属于同一互通类（任意两状态互通）。
- **周期（period）**：$d(i) = \gcd\{n \geq 1 : Q^n_{ii} > 0\}$。**非周期**：$d(i) = 1$。
- **常返（recurrent）**：从 $i$ 出发以概率 1 返回 $i$。**正常返**：期望回归时间有限。

### 平稳分布

平稳分布 $\pi$ 满足：

$$\pi Q = \pi, \quad \sum_i \pi_i = 1, \quad \pi_i \geq 0$$

即 $\pi$ 是 $Q$ 的属于特征值 1 的**左特征向量**。

**细致平衡（detailed balance）**：若 $\pi_i Q_{ij} = \pi_j Q_{ji}$ 对所有 $i, j$ 成立，则 $\pi$ 是平稳分布。满足细致平衡的链称为可逆链。

### 收敛定理

**有限状态空间上的不可约非周期链**具有唯一平稳分布 $\pi$，且对任意初始分布：

$$\lim_{n\to\infty} Q^n_{ij} = \pi_j$$

收敛速率由 $Q$ 的**第二大特征值模** $|\lambda_2|$ 决定——$|\lambda_2|$ 越小，混合（mixing）越快。

### 遍历定理

对正常返不可约链，时间平均几乎必然收敛到集合平均：

$$\frac{1}{n}\sum_{k=1}^{n} r(X_k) \xrightarrow{\text{a.s.}} \sum_{i} \pi_i\, r(i)$$

### 转移核

当状态空间连续时，转移矩阵推广为**转移核** $K(x, A) = P(X_{t+1} \in A \mid X_t = x)$。

## 关联概念

- [[random-processes]] — 马尔可夫链是随机过程的特殊情形
- [[monte-carlo-methods]] — MCMC 利用马尔可夫链的遍历性进行采样
- [[hidden-markov-model]] — 隐状态服从马尔可夫链的生成模型
- [[eigendecomposition]] — 平稳分布和收敛速率由转移矩阵的特征分解决定
