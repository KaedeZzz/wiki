---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Time Shift Properties of z-Transform.md
ingested: 2026-07-08
---

**Time lag**
$$
\begin{align}
\mathcal Z[\{ u_{k-d} \}]&=\sum_{k=0}^{\infty}u_{k-d}z^{-k} \\
&=u_{-d}+u_{-(d-1)}z^{-1}+\dots+u_{-1}z^{-(d-1)}+\sum_{k=d}^{\infty}u_{k-d}z^{-k} \\ \\
&=u_{-d}+u_{-(d-1)}z^{-1}+\dots+u_{-1}z^{-(d-1)}+\sum_{k'=0}^{\infty}u_{k'}z^{-(k'+d)} \\
&=u_{-d}+u_{-(d-1)}z^{-1}+\dots+u_{-1}z^{-(d-1)}+z^{-d}U(z)
\end{align}
$$
Note that we have to add terms from $k<0$.
If signal is 0 at negative values, $\mathcal Z[\{ u_{k-d} \}]=z^{-d}U(z)$; therefore, $z^{-1}$ is the *time-delay operator*.

**Time advance**
$$
\begin{align}
\mathcal Z[\{ u_{k+d} \}]&=\sum_{k=0}^{\infty}u_{k+d}z^{-k} \\
&= z^{d}\sum_{k=d}^{\infty}u_{k}z^{-k} \\
&= z^{d}U(z)-z^{d}u_{0}-z^{d-1}u_{1}-\dots-zu_{d-1}
\end{align}
$$
Note that we have to discard terms before $k=d$.
$z$ is the *time-advance operator*.

[[z-Transform]]