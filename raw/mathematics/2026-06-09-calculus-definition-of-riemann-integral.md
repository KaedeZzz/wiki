---
source: "KaedeSync/_Knowledge/Mathematics/Calculus/Definition of Riemann Integral.md"
ingested: 2026-06-09
---

Divide the interval $[a,b]\subset \mathbb{R}$ into intervals: $a=x_{1}<x_{2}<\dots<x_{n+1}=b$ defines the partition $P$ pf the domain of integration with $\Delta x_{k}=[x_{k},x_{k+1}]$.
Define two summations:
$$
\begin{align}
S_{P}(x)=\sum_{k=1}^{n}M_{k}(x_{k+1}-x_{k}),\quad M_{k}=\sup_{x \in \Delta x_{k}}f(x) \\
s_{P}(x)=\sum_{k=1}^{n}m_{k}(x_{k+1}-x_{k}),\quad m_{k}=\inf_{x \in \Delta x_{k}}f(x)
\end{align}
$$
Then if the function is continuous, then
$$
\lim_{ n \to \infty } S_{P}=\lim_{ n \to \infty } s_{P}=A
$$
where $A$ is the value of the [[Riemann Integral]].