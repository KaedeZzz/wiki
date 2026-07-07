---
summary: Potts 模型是像素被视为节点、相邻像素成对连边的马尔可夫网络，成对势 φ_ij 奖励同标签邻居；用于图像分割时诱导空间平滑先验，是统计力学 Ising 模型的直接多状态推广。
tags: [computer-vision, graphical-model, statistical-mechanics]
updated: 2026-07-06
sources:
  - raw/computer-vision/2026-07-06-potts-model.md
---

# Potts 模型（视觉中的应用）

## 定义

将图像的每个像素 $i$ 视为随机变量 $x_i \in \{1,\dots,K\}$（分割标签），构造一个马尔可夫网络（[[graphical-model]] 中的无向图模型），其中相邻像素间有边。联合分布：

$$p(x_1,\dots,x_n) = \frac{1}{Z}\prod_{(i,j)\in E} \phi_{ij}(x_i, x_j)$$

**成对势**：奖励邻居同标签：

$$\log\phi_{ij}(x_i, x_j) = \begin{cases}\beta > 0, & x_i = x_j \\ 0, & \text{otherwise}\end{cases}$$

## 关键点

### 图像分割用途

结合像素级观察概率（e.g. 每像素在给定标签下的颜色/纹理似然）与 Potts 平滑先验，最大化后验（MAP）能得到**边界干净、区域连续**的分割——像素噪声被邻居"投票"抹平。$\beta$ 越大 → 分割越平滑（可能过合并）；$\beta$ 越小 → 越贴合观测。

### 与 Ising 模型的关系

Potts 是 [[statistical-mechanics]] Ising 模型（$K=2$、自旋 $\pm 1$）的**多状态推广**。物理里 $\beta$ 是逆温度，视觉里就是分割**平滑度旋钮**——两者共享 Gibbs 分布形式和相变现象。

### 推断

MAP 求解等价于最小化能量 $-\log p = -\sum_{(i,j)}\beta\,\mathbb{1}[x_i=x_j] + \text{const}$。这是一个**图割**问题：

- $K=2$：多项式时间可解（max-flow / min-cut）
- $K\geq 3$：一般 NP 难，但 $\alpha$-expansion / $\alpha\beta$-swap 等近似算法效果很好

也可用 [[markov-chain]] 的 Gibbs 采样、置信传播（见 [[factor-graph]]）近似。

## 关联概念

- [[graphical-model]] — Potts 是无向马尔可夫网络的经典实例
- [[statistical-mechanics]] — Ising 是 Potts 的 $K=2$ 特例；共享 Gibbs 分布与相变
- [[factor-graph]] — 置信传播可作为近似推断
- [[markov-chain]] — Gibbs 采样是另一近似推断路线
- [[feature-detection]] — 分割与特征检测是视觉中互补的低层信号
