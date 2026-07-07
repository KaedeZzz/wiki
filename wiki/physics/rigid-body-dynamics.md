---
summary: 刚体动力学核心：Newton 第二定律 M𝐫̈_G = F 描述质心平移，角动量方程 Q_P = ḣ_P + ṙ_P × p 描述转动；角动量 h = Iω，惯量张量 I 是对称矩阵，其特征分解给出主惯量轴与主转动惯量。
tags: [physics, mechanics, rigid-body]
updated: 2026-07-06
sources:
  - raw/physics/2026-07-06-mechanics-newtons-second-law-for-rigid-body.md
  - raw/physics/2026-07-06-mechanics-newtons-second-law-of-angular-momentum.md
  - raw/physics/2026-07-06-mechanics-centre-of-the-mass.md
  - raw/physics/2026-07-06-mechanics-centre-of-the-mass-1.md
  - raw/physics/2026-07-06-mechanics-angular-momentum.md
  - raw/physics/2026-07-06-mechanics-angular-momentum-1.md
  - raw/physics/2026-07-06-mechanics-inertia-matrix.md
  - raw/physics/2026-07-06-mechanics-principal-axes-of-inertia.md
  - raw/physics/2026-07-06-mechanics-principal-moments-of-inertia.md
  - raw/physics/2026-07-06-mechanics-proof-of-virtual-work-with-linear-algebra.md
---

# 刚体动力学

## 定义

**刚体**：所有内部距离不随时间变化的物体。其运动完全由质心 $\mathbf{r}_G$（3 个平移自由度）+ 姿态（3 个转动自由度）确定，共 6 个自由度。

## 关键点

### Newton 第二定律（平移）

$$M\ddot{\mathbf{r}}_G = \dot{\mathbf{p}} = \mathbf{F}^{(e)}$$

- $M$：刚体总质量
- $\mathbf{r}_G = \tfrac{1}{M}\sum_i m_i \mathbf{r}_i$：质心位置
- $\mathbf{p} = M\dot{\mathbf{r}}_G$：总线动量
- $\mathbf{F}^{(e)}$：总外力

**质心的作用**：整体平动方程写在质心上时形式最简——内力对总动量无贡献（Newton 第三定律成对抵消），只需考虑外力合。

### 角动量与转动方程

**角动量**（关于任意参考点 $P$）：

$$\mathbf{h}_P = \sum_i (\mathbf{r}_i - \mathbf{r}_P) \times m_i \dot{\mathbf{r}}_i$$

**转动 Newton 第二定律**：外力矩等于角动量变化率**加**参考点运动的修正项：

$$\mathbf{Q}^{(e)}_P = \dot{\mathbf{h}}_P + \dot{\mathbf{r}}_P \times \mathbf{p}$$

推导：直接对 $\mathbf{h}_P$ 关于时间求导即得。

**两个特殊 $P$ 令修正项消失**：

- $P = G$（质心）：$\dot{\mathbf{r}}_G \parallel \mathbf{p}$，叉积为零 → $\mathbf{Q}^{(e)}_G = \dot{\mathbf{h}}_G$
- $P$ 为**固定点**：$\dot{\mathbf{r}}_P = \mathbf{0}$ → $\mathbf{Q}^{(e)}_P = \dot{\mathbf{h}}_P$

工程实践中总是把 $P$ 选为质心或固定支点，方程最干净。

### 惯量张量

绕固定点以角速度 $\boldsymbol{\omega}$ 旋转的刚体，角动量与角速度的关系：

$$\mathbf{h}_P = \sum_i \mathbf{r}_i \times m_i(\boldsymbol{\omega} \times \mathbf{r}_i) = \mathbf{I}_P\,\boldsymbol{\omega}$$

其中**惯量矩阵**：

$$\mathbf{I}_P = \begin{bmatrix}\sum m_i(y_i^2 + z_i^2) & -\sum m_i x_i y_i & -\sum m_i x_i z_i \\ -\sum m_i y_i x_i & \sum m_i(x_i^2 + z_i^2) & -\sum m_i y_i z_i \\ -\sum m_i z_i x_i & -\sum m_i z_i y_i & \sum m_i(x_i^2 + y_i^2)\end{bmatrix}$$

- **总是对称**（矩阵结构决定）→ 由谱定理有实特征值和正交特征向量
- 依赖参考点 $P$ 和坐标系选择
- **对角元** = 转动惯量（关于该轴）；**非对角元** = 惯量积

### 主惯量轴与主转动惯量

对称矩阵 $\mathbf{I}_P$ 的特征值问题 $\mathbf{I}_P \boldsymbol{\omega} = \lambda \boldsymbol{\omega}$ 给出：

- **主惯量轴**：$\mathbf{I}_P$ 的特征向量方向（相互正交）
- **主转动惯量** $A, B, C$：三个特征值

沿主轴建立坐标系后，惯量矩阵**对角化**：

$$\mathbf{I}_P = \text{diag}(A, B, C)$$

此时 $\mathbf{h}_P = (A\omega_1, B\omega_2, C\omega_3)^T$——运动学简单可解。这就是 [[eigendecomposition]] 在力学中的直接应用。

### 虚功原理（线性代数版）

结构静力学中，刚度矩阵 $\mathbf{R}$ 同时联系"力—内张力"与"位移—伸长"：

$$\mathbf{F} = \mathbf{R}\boldsymbol{\tau},\quad \mathbf{e} = \mathbf{R}^T \boldsymbol{\delta}$$

由此 $\begin{bmatrix}\boldsymbol{\delta} \\ -\mathbf{e}\end{bmatrix}$ 在 $\begin{bmatrix}\mathbf{R}^T & \mathbf{I}\end{bmatrix}$ 的**零空间**里，$\begin{bmatrix}\mathbf{F} \\ \mathbf{T}\end{bmatrix}$ 在其**列空间**里——两者按 [[fundamental-subspaces]] 的正交关系 $\mathbf{F}\cdot\boldsymbol{\delta} - \mathbf{T}\cdot\mathbf{e} = 0$，即**虚功原理**。

## 关联概念

- [[eigendecomposition]] — 惯量矩阵谱分解给出主轴
- [[fundamental-subspaces]] — 虚功原理是列空间与零空间正交的物理化身
- [[lagrangian-mechanics]] — 用广义坐标推广 Newton 方程
- [[small-vibrations]] — 小振动方程用惯量矩阵 M 与刚度矩阵 K
- [[state-space-model]] — 刚体动力学也可以写成状态空间形式
