---
summary: 图像特征检测通过卷积算子提取边缘（Canny 用 ∇G_σ*I 找梯度峰）、角点（Harris 用局部梯度二阶矩阵的特征值）、斑点（LoG 找 ∇²G_σ*I 峰）；尺度用 Gaussian 金字塔控制。
tags: [computer-vision, image-processing]
updated: 2026-07-06
sources:
  - raw/computer-vision/2026-07-06-features-canny-edge-detection-algorithm.md
  - raw/computer-vision/2026-07-06-features-harrris-corner-detection-algorithm.md
  - raw/computer-vision/2026-07-06-features-marr-hildreth-operator.md
  - raw/computer-vision/2026-07-06-features-blob.md
  - raw/computer-vision/2026-07-06-features-image-pyramid.md
  - raw/computer-vision/2026-07-06-features-cross-correlation-of-image.md
---

# 图像特征检测

## 定义

从像素图 $I(x,y)$ 中定位具有几何/统计意义的**局部结构**——边缘、角点、斑点、模板匹配位置——为后续几何视觉（[[camera-model]]、SfM、SLAM）和识别提供**稀疏、稳定、可复现**的锚点。

## 关键点

### 卷积作为通用工具

所有经典特征检测器都建立在**图像与滤波核的卷积**上：

$$S(x,y) = (G_\sigma * I)(x,y),\qquad G_\sigma(x,y) = \frac{1}{2\pi\sigma^2}\exp\!\left(-\frac{x^2+y^2}{2\sigma^2}\right)$$

Gaussian 平滑抑制噪声；后续微分算子作用于 $S$ 而不是 $I$。**关键恒等式** $\nabla(G_\sigma * I) = \nabla G_\sigma * I$ 使"平滑 + 求导" = "与预求导核卷积"，一次卷积搞定。

### Canny 边缘检测

三步：

1. **平滑**：$S = G_\sigma * I$
2. **梯度**：$\nabla S = \nabla G_\sigma * I$
3. **非极大抑制** + **双阈值**：只保留 $|\nabla S|$ 在 $\pm\nabla S$ 方向上是局部极大的像素，再按上下阈值筛出连续边。

输出：一列边像素，每个附**强度** $|\nabla S|$ 和**方向** $\nabla S / |\nabla S|$。

### Harris 角点检测

角点定义：局部强度**在所有方向都变化剧烈**的位置。定量做法：

1. 方向 $\mathbf{n}$ 上的强度变化平方 $S_n^2 = \tfrac{\mathbf{n}^T \nabla S \nabla S^T \mathbf{n}}{\mathbf{n}^T\mathbf{n}}$
2. 局部 Gaussian 加权平均得 $C_n = \tfrac{\mathbf{n}^T \mathbf{A}\mathbf{n}}{\mathbf{n}^T\mathbf{n}}$，其中

$$\mathbf{A} = \begin{bmatrix}\langle S_x^2\rangle & \langle S_x S_y\rangle \\ \langle S_x S_y\rangle & \langle S_y^2\rangle\end{bmatrix}$$

即梯度二阶矩阵。

3. 由瑞利商（见 [[eigendecomposition]]）：$\lambda_1 \leq C_n \leq \lambda_2$，两个特征值即"最小/最大方向变化"。

**分类**：

- $\lambda_1 \approx \lambda_2 \approx 0$：**平坦区**
- $\lambda_1 \approx 0$, $\lambda_2$ 大：**边缘**（沿 $\lambda_1$ 方向无变化）
- $\lambda_1, \lambda_2$ 都大且相当：**角点**

**Harris 响应函数**（避免直接求特征值）：$R = \det\mathbf{A} - \kappa\,\text{tr}(\mathbf{A})^2 = \lambda_1\lambda_2 - \kappa(\lambda_1+\lambda_2)^2$，阈值筛角点。

### Marr-Hildreth / LoG 与斑点

**Marr-Hildreth 算子**：找 $\nabla^2 G_\sigma * I$（**高斯拉普拉斯 LoG**）的零穿越 → 边缘检测器。

**斑点检测**：LoG 的**极值**（不是零穿越）对应中心强度与外圈明显不同的圆形区域。检测到的斑点尺寸由 $\sigma$ 决定——**多尺度检测**即用不同 $\sigma$ 扫（[[image-pyramid]] 结构下更高效）。

### 模板匹配：归一化互相关

$$c(x,y) = \frac{\sum_{u,v} P(u,v)\, I(x+u, y+v)}{\sqrt{\sum P^2 \cdot \sum I^2(x+u, y+v)}}$$

滑动模板 $P$ 与图像局部块的**归一化点积**——对亮度尺度不敏感。相关面存在**尖锐峰**表示良好匹配（角点、独特纹理）；弱峰或多峰意味着位置不确定。

### 图像金字塔

对图像做**逐层降采样 + 平滑**得到多分辨率栈。特征检测器在各层运行 → 尺度不变：不知目标大小时逐层扫，同一物理特征在不同层的响应对齐后即为**多尺度关键点**（SIFT、SURF 的基础）。

## 关联概念

- [[eigendecomposition]] — Harris 二阶矩阵的特征值即角点判据
- [[camera-model]] — 特征点是标定与三维重建的输入
- [[gaussian-distribution]] — Gaussian 核在 $L^2$ 上是唯一"最平滑"平滑器
- [[cnn]] — 现代卷积网络学到的低层滤波器与手工 Canny/Harris 惊人相似
