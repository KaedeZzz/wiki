---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Perspective Projection in Homogenous Coordinates.md
ingested: 2026-07-06
---

For an object, Cartesian to homogenous coordinates transformation:
$$
\mathbf{X}=(X,Y,Z)\longrightarrow (\lambda X,\lambda Y,\lambda Z,\lambda)=\tilde{\mathbf{X}}
$$
For an image on a plane:
$$
\mathbf{x}=(x,y)\longrightarrow (sx,sy,s)=\tilde{\mathbf{x}}
$$

Therefore, in homogenous coordinates, perspective projection can be expressed as
$$
\begin{bmatrix}
sx \\
sy \\
s
\end{bmatrix}
=
\begin{bmatrix}
f & 0 & 0 & 0 \\
0 & f & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
\lambda X_{c} \\
\lambda Y_{c} \\
\lambda Z_{c} \\
\lambda
\end{bmatrix}
$$
equivalently,
$$
\tilde{\mathbf{x}}=\mathbf{P}_{p}\tilde{\mathbf{X}}_{c},\quad \mathbf{P}_{p}=\begin{bmatrix}
f & 0 & 0 & 0 \\
0 & f & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
$$
Notice how value of $\lambda$ has no effect on the projection. Conventionally we set $\lambda$ to $1$.
Same projection is achieved by multiplying by $\mu \mathbf{P}_{p}$ where $\mu\neq 0$.