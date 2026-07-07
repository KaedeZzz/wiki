---
source: KaedeSync/_Knowledge/Communications/Filter Design/FIR Wiener Filter.md
ingested: 2026-07-08
---

[[FIR Filter]] and [[Wiener Filter]]

Here we have [[Wiener-Hopf Equations]] as follows:
$$
\sum_{p=0}^{P}h_{p}r_{XX}[q-p]=r_{xd}[q]\quad \text{for }q=0,1,\dots,P
$$
The equation may be written in matrix form as:
$$
\mathbf{R}_{x}\mathbf{h}=\mathbf{r}_{xd}
$$
where $\mathbf{R}$ is the correlation matrix that is symmetric and has constant diagonals:
$$
\mathbf{R}_{x}=
\begin{bmatrix}
r_{x x}[0] & r_{x x}[1] & \dots & r_{x x}[P] \\
r_{x x}[1] & r_{x x}[0] & \dots & r_{x x}[P-1] \\
\vdots & \vdots &  & \vdots \\
r_{x x}[P] & r_{x x}[P-1] & \dots & r_{x x}[0]
\end{bmatrix}
$$
Therefore:
$$
\begin{align}
\mathbf{h} & =\mathbf{R}_{x}^{-1}\mathbf{r}_{xd} \\
J_{\min} & =r_{dd}[0]-\mathbf{r}_{xd}^{T}\mathbf{R}_{x}^{-1}\mathbf{r}_{xd}
\end{align}
$$
