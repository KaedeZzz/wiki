---
summary: Noether 定理把物理系统的每个连续对称与一个守恒量一一对应；简约原则（Occam 剃刀在物理里的化身）主张对同一现象保留能解释它的最稀最简模型——不是更简单，也不是更复杂。
tags: [physics, principles]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-noether-theorem.md
  - raw/physics/2026-07-06-principle-of-parsimony.md
---

# Noether 定理与简约原则

## 定义

两条统摄性物理原则的合页。

**Noether 定理**（Emmy Noether, 1918）：具有作用量泛函 $S = \int\mathcal{L}\,dt$ 的物理系统，其每一个**连续对称**都对应一个**守恒量**。

**简约原则**（Principle of Parsimony）："*一个合适的物理模型应当尽可能稀疏和简单，但不能更稀疏更简单。*" 现代对 Einstein 名言"Make things as simple as possible, but not simpler."的呼应。

## 关键点

### Noether 定理：对称 ↔ 守恒

在 [[lagrangian-mechanics]] 里，作用量 $S = \int \mathcal{L}(q,\dot q, t)\,dt$ 的极值条件即 Euler-Lagrange 方程。若 $\mathcal{L}$ 在某种坐标变换 $q \to q + \epsilon\delta q$ 下不变，则存在一个沿系统轨迹守恒的量 $J$。

经典对应：

| 对称 | 守恒量 |
|---|---|
| 时间平移不变（$\mathcal{L}$ 不显式含 $t$） | **能量** |
| 空间平移不变 | **动量** |
| 空间旋转不变 | **角动量** |
| 电磁规范不变 | **电荷** |

**为什么震撼**：物理里最基础的守恒律不再是独立公理，而是**对称性的推论**。这条定理是现代场论、粒子物理、广义相对论所有基本相互作用理论的核心方法论。

**在 Koopman 意义下的对偶**（见 [[koopman-and-dmd]]）：动力学的每个连续对称，对应一个 **Koopman 特征值 $\lambda = 0$ 的特征函数**——即"沿轨道不变的量"。Noether 从**变分**视角说的话，用**算子谱**语言重讲一次得到同样的结论。

### 简约原则的实践含义

它有两个方向：

1. **不要 over-fit**："*但不能更稀疏*"——不能为了简洁牺牲能解释的现象；如果观测里有振荡，模型必须含产生振荡的机制
2. **不要 over-model**："*应尽可能稀疏简单*"——不该无缘无故添加参数或机制

数学化的表述：贝叶斯模型选择里的**边缘似然**、信息准则 AIC/BIC、[[pac-bayes-bound]] 的 KL 项——都是这个原则的定量版本。

**与机器学习的对应**：

- [[regularisation]] — 正则化项就是"不必要复杂就惩罚"的数学化
- [[sindy]] — 稀疏回归找**最少项**能解释数据的动力学方程，是这条原则的直接工具化
- [[pac-bayes-bound]] — KL(后验 || 先验) 越小泛化越好——学"少"胜于学"多"
- [[occam]] 不是本 wiki 一个节点，但 Occam 剃刀在概率语言中即"简单模型有更高 posterior evidence"

### 两条原则的合流

Noether 定理告诉我们，**对称是物理的"塑料模具"**；简约原则告诉我们，**建模应识别并只保留必要的对称与自由度**。SINDy、[[koopman-and-dmd]] 等数据驱动方法本质上是**同时搜索合适的坐标（对称视角）和最稀疏的动力学表达（简约视角）**。

## 关联概念

- [[lagrangian-mechanics]] — Noether 的家；作用量 + 对称 = 守恒
- [[koopman-and-dmd]] — Noether 的算子谱化身
- [[sindy]] — 简约原则在动力系统辨识中的工具化
- [[regularisation]] — 机器学习中的简约实现
- [[pac-bayes-bound]] — 简约与泛化的信息论桥梁
