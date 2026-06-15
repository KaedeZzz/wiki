---
source: "KaedeSync/_Knowledge/Mathematics/Graph Theory/Linear Interpolation of Graphs.md"
ingested: 2026-06-09
---

We can interpolate the whole graph using
$$
y_{i}=\begin{cases}
y_{i} & \text{if node }i\text{ is observed} \\
\frac{1}{k_{i}}\sum_{j}A_{ij}y_{j} & \text{otherwise.}
\end{cases}
$$
To solve, let $W_{ij}=A_{ij}/ k_{i}$, then the equation to solve is
$$
\begin{align}
y_{i} & =\sum_{j}W_{ij}y_{j} \\
 & =\sum_{j:\text{obs.}}W_{ij}y_{j}+\sum_{j:\text{unobs.}}W_{ij}y_{j} \\
\text{notation} & =b_{i}+\sum_{j:\text{unobs.}}W_{ij}y_{j}
\end{align}
$$
vectorise:
$$
\mathbf{y}=\mathbf{b}+\mathbf{W}^{(u)}\mathbf{y}
$$
and the solution:
$$
\mathbf{y}=(\mathbf{I}-\mathbf{W}^{(u)})^{-1}\mathbf{b}
$$
[[Graph]]