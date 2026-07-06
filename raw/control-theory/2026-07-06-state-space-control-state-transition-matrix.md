---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/State Transition Matrix.md
ingested: 2026-07-06
---

For $\mathbf{u}(t)=\mathbf{0}$ we have $\dot{\mathbf{x}}(t)=\mathbf{A}\mathbf{x}(t)$ and hence,
$$
\mathbf{X}(s)=(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{x}_{0}
$$
To get linear solution in time domain:
$$
\mathbf{x}(t)=\mathcal L^{-1}\left((s\mathbf{I}-\mathbf{A})^{-1}\right)\mathbf{x}_{0}=\mathbf{\Phi}(t)\mathbf{x}_{0}
$$
where
$$
\begin{align}
\mathbf{\Phi}(t) & =\mathcal L^{-1}\{ (s\mathbf{I}-\mathbf{A})^{-1} \} \\
 & =\mathcal L^{-1}\left\{  \sum_{k\geq 0} \mathbf{A}^{k}s^{-(k+1)} \right\} \\
 & =\mathbf{I}+\mathbf{A}t+\frac{\mathbf{A}^{2}t^{2}}{2!}+\frac{\mathbf{A}^{3}t^{3}}{3!}+\dots \\
 & \equiv e^{\mathbf{A}t}
\end{align}
$$


[[Laplace Solution of Linear State Equations]]