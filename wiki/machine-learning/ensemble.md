---
summary: 集成方法将多个模型（不同初始化、不同数据采样、甚至不同架构）的预测平均，利用方差减小提升泛化性能。
tags: [machine-learning, technique]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-techniques-ensemble.md
---

# 集成学习（Ensemble）

## 定义

将多个模型的预测取平均，来源可包括不同随机初始化、不同重采样数据集、不同架构。

## 关键点

- 核心直觉：平均可以降低方差。
- 与 [[dropout]] 存在理论联系——dropout 可视为隐式集成。

## 关联概念

- [[regularisation]] — 集成是减小泛化差距的方法
- [[dropout]] — 隐式的集成方法
