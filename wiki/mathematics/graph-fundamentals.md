---
summary: 图的基本定义、表示方法与常见类型。
tags: [mathematics, graph-theory]
updated: 2026-06-09
sources:
  - raw/mathematics/2026-06-09-graph-theory-fundamentals.md
---
# 图论基础

## 定义

图 $G = (V, E)$ 由节点集 $V$ 和边集 $E \subseteq V \times V$ 组成，是描述成对关系的数学结构。

## 关键点

### 邻接矩阵

$n$ 个节点的图可用 $n \times n$ 邻接矩阵 $A$ 表示：

$$A_{ij} = \begin{cases} 1 & \text{if } (i,j) \in E \\ 0 & \text{otherwise} \end{cases}$$

无向图的邻接矩阵对称：$A = A^T$。加权图中 $A_{ij}$ 取边权值。

### 度

- **度**（degree）：节点所连边数，$k_i = \sum_j A_{ij}$
- **有向图**：入度 $k_i^{\text{in}} = \sum_j A_{ji}$，出度 $k_i^{\text{out}} = \sum_j A_{ij}$

### 距离与连通分量

- 两节点间**距离**：最短路径的边数
- **连通分量**：极大连通子图；无向图中任意两节点可达则图连通

### 图的类型

| 类型 | 特征 |
|------|------|
| 无向图 | 边无方向，$A$ 对称 |
| 有向图 | 边有方向，$A$ 不一定对称 |
| 加权图 | 边附带权重 |
| 二部图 | 节点分两组，边只跨组连接 |
| 超图 | 一条超边可连接多于两个节点 |
| 多重图 | 两节点间允许多条边 |
| 多层网络 | 同一节点集上叠加多种关系层 |

## 关联概念

- [[centrality-measures]] — 基于图结构量化节点重要性
- [[graph-properties]] — 图的全局统计特征（聚类系数、模块度等）
- [[graphical-model]] — 用图结构表示概率变量间的依赖关系
