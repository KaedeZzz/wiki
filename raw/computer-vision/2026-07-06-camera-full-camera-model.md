---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Full Camera Model.md
ingested: 2026-07-06
---

A full camera model describes the mapping from world to pixel coordinates. It accounts for the following transformations:
- rigid body motion between the camera and the scene,
- [[Perspective Projection]] onto the image plane, and
- CCD imaging - the geometry of the CCD array and its position with respect to the optical axis.

**Rigid Body Motion**
We attach a coordinate system $\mathbf{X}=(X,Y,Z)$ to the world, and another coordinate system $\mathbf{X}_{c}=(X_{c},Y_{c},Z_{c})$ to the camera. The rigid body motion of camera can be described as:
$$
\mathbf{X}_{c}=\mathbf{RX}+\mathbf{T}
$$
where
$$
\mathbf{R}=\begin{bmatrix}
r_{11} & r_{12} & r_{13} \\
r_{21} & r_{22} & r_{23} \\
r_{31} & r_{32} & r_{33} 
\end{bmatrix}
$$
is the rotation matrix and $\mathbf{T}$ is the translation matrix.

**Perspective Projection**
$$
\mathbf{x}=\left( f \frac{X_{c}}{Z_{c}}, f \frac{Y_{c}}{Z_{c}} \right)
$$
**CCD Imaging**
The pixel coordinates $\mathbf{w}=(u,v)$ and image plane coordinates $\mathbf{x}=(x,y)$ are associated as:
$$
\begin{align}
u=u_{0}+k_{u}x \\
v=v_{0}+k_{v}y
\end{align}
$$

The overall mapping from $\mathbf{X}$ to $\mathbf{w}$ is then
$$
\begin{align}
u & =u_{0}+\frac{{k_{u}fX_{c}}}{Z_{c}}=u_{0}+\frac{{k_{u}f(r_{11}X+r_{12}Y+r_{13}Z+T_{x})}}{r_{31}X+r_{32}Y+r_{33}Z+T_{z}} \\
v & =v_{0}+\frac{{k_{v}fY_{c}}}{Z_{c}}=u_{0}+\frac{{k_{v}f(r_{21}X+r_{22}Y+r_{23}Z+T_{y})}}{r_{31}X+r_{32}Y+r_{33}Z+T_{z}}
\end{align}
$$