---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/Kalman Filter/Extended Kalman Filter.md
ingested: 2026-07-06
---

Consider the following non-linear state-space model:
$$
\begin{align}
\mathbf{x}_{t} & =A(\mathbf{x}_{t-1})+\mathbf{v}_{t} \\
\mathbf{y}_{t} & =B(\mathbf{x}_{t})+\mathbf{w}_{t}
\end{align}
$$
with
$$
\begin{align}
\text{cov}(\mathbf{v}_{t}) & =\mathbf{\Sigma}_{\mathbf{v}} \\
\text{cov}(\mathbf{w}_{t}) & =\mathbf{\Sigma}_{\mathbf{w}}
\end{align}
$$
A first-order taylor approximation gives:
$$
\begin{align}
A(\mathbf{x}_{t}) & \approx A( \mu_{t|t})+ \frac{{\partial A(\mathbf{x}_{t})}}{\partial \mathbf{x}_{t}}\rvert_{x_{t}=\mu_{t|t}}(\mathbf{x}_{t}-\mu_{t|t}) \\
B(\mathbf{x}_{t}) & \approx B( \mu_{t|t-1})+ \frac{{\partial B(\mathbf{x}_{t})}}{\partial \mathbf{x}_{t}}\rvert_{x_{t}=\mu_{t|t-1}}(\mathbf{x}_{t}-\mu_{t|t-1})
\end{align}
$$
which leads to a linearized set of equations which can be solved using standard Kalman filter.