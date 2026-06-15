---
summary: ROC 曲线绘制假阳性率 vs 真阳性率，AUC 衡量分类器整体判别能力。曲线上的点对应不同决策阈值（操作点）。
tags: [machine-learning, evaluation]
updated: 2026-06-08
sources:
  - raw/machine-learning/2026-06-08-basics-metrics-roc-curve.md
  - raw/machine-learning/2026-06-08-deep-learning-receiver-operating-characteristic-curve.md
---

# ROC 曲线

## 定义

False Positive Rate ($FP/N$) vs True Positive Rate ($TP/P$) 的曲线。AUC（曲线下面积）是单一指标衡量分类器判别能力。

## 关键点

- 曲线上的每个点对应一个决策阈值（操作点）。
- 有偏损失函数使"代价比"成为操作阈值，改变阈值在 ROC 曲线上移动操作点。

## 关联概念

- [[loss-function]] — 损失函数的偏向性影响操作点选择
- [[supervised-and-unsupervised-learning]] — ROC 用于评估监督学习分类器
