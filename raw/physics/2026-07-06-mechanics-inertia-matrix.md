---
source: KaedeSync/_Knowledge/Physics/Mechanics/Inertia Matrix.md
ingested: 2026-07-06
---

![[Angular Momentum 1]]

Suppose the object is rotating about a fixed point (set it be origin of the coordinate system) at angular velocity $\omega$, then:
$$
\mathbf{h}_{P}=\sum_{i}\mathbf{r}_{i}\times m_{i}(\mathbf{\omega}\times \mathbf{r}_{i})=\sum_{i}m_{i}[(\mathbf{r}_{i}\cdot \mathbf{r}_{i})\mathbf{\omega}-(\mathbf{r_{i}}\cdot \mathbf{\omega})\mathbf{r_{i}}]
$$
expansion in matrix form gives
$$
\mathbf{h}_{P}=
\begin{bmatrix}
\sum_{i}m_{i}(y_{i}^{2}+z_{i}^{2}) & -\sum_{i}m_{i}x_{i}y_{i} &  -\sum_{i}m_{i}x_{i}z_{i} \\
-\sum_{i}m_{i}y_{i}x_{i} & \sum_{i}m_{i}(x_{i}^{2}+z_{i}^{2}) & -\sum_{i}m_{i}y_{i}z_{i} \\
-\sum_{i}m_{i}z_{i}x_{i} & -\sum_{i}m_{i}z_{i}y_{i} & \sum_{i}m_{i}(x_{i}^{2}+y_{i}^{2})
\end{bmatrix}
\begin{bmatrix}
\omega_{1} \\
\omega_{2} \\
\omega_{3}
\end{bmatrix}
$$
summarizing into
$$
\mathbf{h}_{P}=\mathbf{I}_{P}\mathbf{\omega}
$$
$\mathbf{I}_{P}$ is known as inertia matrix or inertia tensor.
- It is always symmetric
- It depends on choice of $P$ and axes of coordinates
- The diagonal elements are known as *moment of inertia,* and the off-diagonal elements are known as *product of inertia*.

[[Torque]], [[Angular Momentum 1]]