---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Polar Plots.md
ingested: 2026-07-06
---

The transfer functions can usefully be plotted in polar coordinates. Consider [[Mobility Function]]:

Let $p=\omega / \omega_{n}$. Then:
$$
H_{v}(\omega)= \frac{ip}{1-p^{2}+i 2\zeta p}=\frac{{ip[(1-p^{2})-i 2\zeta p]}}{(1-p^{2})^{2}+(2\zeta p)^{2}}
$$

Let $U= \frac{2\zeta p^{2}}{(1-p^{2})^{2}+(2\zeta p)^{2}}-\frac{1}{4\zeta}$ and $V=\frac{{p(1-p^{2})}}{(1-p^{2})^{2}+(2\zeta p)^{2}}$, we can find that:
$$
\begin{align}
U+iV & =H_{v}- \frac{1}{4\zeta} \\
U^{2}+V^{2} & =\left( \frac{1}{4\zeta} \right)^{2}
\end{align}
$$
Therefore, $H_{v}$ is a circle of radius $\frac{1}{4\zeta}$ centred around $\left( \frac{1}{4\zeta},0 \right)$.

- The polar plot of mobility function for viscous damping is a circle for any value of $\zeta$.
- Polar plots of [[Receptance Function]] and [[Inertance Function]] are circles for $\zeta\ll 1$.
- All plots rise to the value of $\frac{1}{2\zeta}$ at $\frac{\omega}{\omega_{n}}=1$.
