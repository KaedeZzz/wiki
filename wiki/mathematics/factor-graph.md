---
summary: 因子图是一种概率图模型，通过因子节点和变量节点表示联合分布的乘积分解结构，支持置信传播等消息传递算法。
tags: [mathematics, probability, graphical-models]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-probability-theory-factor-graphfactor-graph.md
  - raw/mathematics/2026-06-09-probability-theory-factor-graphbelief-propagation.md
  - raw/mathematics/2026-06-09-probability-theory-factor-graphsum-product-message-computation-rule.md
---

# 因子图

## 定义

因子图将联合分布表示为因子的乘积：

$$p(x_1, \dots, x_n) = \prod_a f_a(x_{N(a)})$$

图中包含两类节点：变量节点（圆）和因子节点（方），当变量 $x_i$ 参与因子 $f_a$ 时二者相连。

## 关键点

### 置信传播（消息传递）

- **变量→因子**消息：来自其他邻居因子的消息之积
$$m_{i \to a}(x_i) = \prod_{b \in N(i) \setminus a} m_{b \to i}(x_i)$$

- **因子→变量**消息：对因子势函数乘以其他变量消息后边缘化
$$m_{a \to i}(x_i) = \sum_{x_{N(a) \setminus i}} f_a(x_{N(a)}) \prod_{j \in N(a) \setminus i} m_{j \to a}(x_j)$$

- **置信（边缘）**：
$$b_i(x_i) \propto \prod_{a \in N(i)} m_{a \to i}(x_i)$$

### Sum-Product 规则

若因子图无环，则 sum-product 算法给出精确边缘分布：$\bar{f}_X(x) = \vec{\mu}_X(x) \overleftarrow{\mu}_X(x)$

## 关联概念

- [[graphical-model]] — 因子图是概率图模型的一种表示
- [[estimation-theory]] — 消息传递可用于推断
- [[hidden-markov-model]] — HMM 的前向-后向算法是 sum-product 的特例
