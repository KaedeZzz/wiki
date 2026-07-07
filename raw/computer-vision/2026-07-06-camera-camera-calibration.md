---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Camera Calibration.md
ingested: 2026-07-06
---

For a [[Projective Camera]] mapping from spatial coordinates $\tilde{\mathbf{X}}$ to CCD array location $\tilde{\mathbf{w}}$ we have:
$$
\begin{bmatrix}
su \\
sv \\
s
\end{bmatrix}
=
\begin{bmatrix}
p_{11} & p_{12} & p_{13} & p_{14} \\
p_{21} & p_{22} & p_{23} & p_{24} \\
p_{31} & p_{32} & p_{33} & p_{34}
\end{bmatrix}
\begin{bmatrix}
X \\
Y \\
Z \\
1
\end{bmatrix}
$$
there are $11$ parameters to estimate.

Each point we observe gives us a pair of equations:
$$
\begin{align}
u_{i} & =\frac{su_{i}}{s}=\frac{{p_{11}X_{i}+p_{12}Y_{i}+p_{13}Z_{i}+p_{14}}}{p_{31}X_{i}+p_{32}Y_{i}+p_{33}Z_{i}+p_{34}} \\
v_{i} & =\frac{sv_{i}}{s}=\frac{{p_{21}X_{i}+p_{22}Y_{i}+p_{23}Z_{i}+p_{24}}}{p_{31}X_{i}+p_{32}Y_{i}+p_{33}Z_{i}+p_{34}}
\end{align}
$$
which can be rearranged into two linear equations in the unknown projection matrix parameters:

![[Pasted image 20251105225035.png]]

Since there are $11$ unknowns, we need at least $11$ equations, so we need to observe at least $6$ points ($12$ equations) to estimate the parameters and calibrate the camera.

However, when we do a linear solution, it is only approximate and should ideally be used as the starting point for non-linear minimisation task described by:
$$
\min_{\mathbf{P}}\sum_{i}((u_{i}-\hat{u}_{i})^{2}+(v_{i}-\hat{v}_{i})^{2})
$$
Having obtained $\mathbf{P}=\mathbf{P}_{ps}$ then we do the decomposition
$$
\mathbf{P}_{ps}=\mathbf{K}[\mathbf{R}|\mathbf{T}]
$$
to obtain the camera calibration matrix and the **orientation** and **position** of the camera.

Standard matrix techniques exist for decomposing the $3\times 3$ sub-matrix into the product of an upper triangular matrix $\mathbf{K}$ and an orthogonal matrix (essentially rotation matrix) $\mathbf{R}$. 
This means, although we cannot decompose $\mathbf{P}_{ps}$ directly into $\mathbf{K}$ and $[\mathbf{R}|\mathbf{T}]$, but we can decompose the first $3$ columns of $\mathbf{P}_{ps}$, $\mathbf{KR}$, into $\mathbf{K}$ and $\mathbf{R}$, then obtain $\mathbf{T}$ as:
$$
\mathbf{T}=\mathbf{K}^{-1}(p_{14},p_{24},p_{34})^{T}
$$
What is desirable for an object to calibrate camera on?
- The object should have accurate, clearly distinguishable features.
- The calibration points cannot be co-line or co-planar.