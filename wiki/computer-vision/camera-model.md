---
summary: 相机模型把世界坐标 X 映射到像素坐标 w，串联刚体运动 → 透视投影 → CCD 采样；齐次坐标把非线性除法变为线性矩阵乘法；投影相机 P（3×4，11 自由度）可由 ≥6 对已知点标定。
tags: [computer-vision, geometry]
updated: 2026-07-06
sources:
  - raw/computer-vision/2026-07-06-camera-full-camera-model.md
  - raw/computer-vision/2026-07-06-camera-perspective-projection.md
  - raw/computer-vision/2026-07-06-camera-orthographic-projection.md
  - raw/computer-vision/2026-07-06-camera-homogenous-coordinates.md
  - raw/computer-vision/2026-07-06-camera-perspective-projection-in-homogenous-coordinates.md
  - raw/computer-vision/2026-07-06-camera-projective-camera.md
  - raw/computer-vision/2026-07-06-camera-camera-calibration.md
---

# 相机模型

## 定义

相机模型：把 3D 世界坐标 $\mathbf{X}=(X,Y,Z)$ 映射到 2D 像素坐标 $\mathbf{w}=(u,v)$。全模型由三段组成：

1. **刚体运动**：世界坐标 → 相机坐标 $\mathbf{X}_c = \mathbf{R}\mathbf{X} + \mathbf{T}$
2. **透视投影**：相机坐标 → 图像平面坐标 $\mathbf{x}=(x,y)$
3. **CCD 采样**：图像平面 → 像素 $u=u_0+k_u x,\ v=v_0+k_v y$

## 关键点

### 透视投影 vs 正投影

**透视投影**（相机光心为原点，$Z_c$ 为光轴）：

$$x = \frac{f X_c}{Z_c},\quad y = \frac{f Y_c}{Z_c}$$

由相似三角形导出。含**深度归一**，是所有实际针孔相机的近似。

**正投影**（平行光线，无深度效应）：

$$\mathbf{x} = \mathbf{X} - (\mathbf{X}\cdot\hat{\mathbf{k}})\hat{\mathbf{k}}$$

远距离对象或长焦近似；不含 $1/Z_c$ 项，线性。

### 齐次坐标

用 $(x_1,x_2,x_3)$ 表示平面点 $(x,y) = (x_1/x_3, x_2/x_3)$——只有比例重要。核心作用：

- **透视除法变矩阵乘法**：$\tilde{\mathbf{x}} = P_p\tilde{\mathbf{X}}_c$，$P_p = \text{diag}(f,f,1) \oplus 0$
- **无穷远点**表示为 $(x_1,x_2,0)$——有明确方向，无 finite 位置
- **多变换合成**：刚体 + 透视 + 采样都是 $4\times 4$ 或 $3\times 4$ 矩阵，可乘起来一次性算

### 投影相机

一般 $3\times 4$ 矩阵 $\mathbf{P}$：

$$\tilde{\mathbf{w}} = \mathbf{P}\tilde{\mathbf{X}},\quad \mathbf{P}\in\mathbb{R}^{3\times 4}$$

$12$ 个元素但整体缩放不改变投影 → **11 自由度**。透视相机（含焦距、旋转、平移、主点、像素尺度）是投影相机的特例。

### 相机标定

用 $N\geq 6$ 对**已知**世界点 $\mathbf{X}_i$ + 观测像素 $\mathbf{w}_i$ 反求 $\mathbf{P}$。每对点给 2 个线性方程（$u_i, v_i$ 分别一条），11 个未知量 → 至少 12 方程（6 点）。

**做法**：

1. **线性解**：把 $u_i, v_i$ 重排为 $\mathbf{A}\mathbf{p} = \mathbf{0}$ 的齐次线性系统，用 SVD 求最小特征向量（见 [[matrix-decomposition]]）。
2. **非线性精化**：以线性解为初值最小化重投影误差 $\sum_i (u_i-\hat u_i)^2 + (v_i-\hat v_i)^2$。
3. **分解**：$\mathbf{P} = \mathbf{K}[\mathbf{R}|\mathbf{T}]$。用 QR 把前 $3\times 3$ 拆为**上三角内参** $\mathbf{K}$ 和**正交旋转** $\mathbf{R}$，然后 $\mathbf{T} = \mathbf{K}^{-1}(p_{14},p_{24},p_{34})^T$。

**标定物设计**：特征清晰、位置精确、点**不共线也不共面**（共面 → 单应性歧义）。

## 关联概念

- [[matrix-decomposition]] — SVD 用于最小二乘解，QR 用于内外参分解
- [[eigendecomposition]] — 齐次线性系统的最小特征方向
- [[fundamental-subspaces]] — 齐次坐标下的投影空间视角
- [[feature-detection]] — 图像上定位特征点是标定和 SfM 的输入
