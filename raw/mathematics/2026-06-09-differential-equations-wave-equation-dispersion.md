---
source: "KaedeSync/_Knowledge/Mathematics/Differential Equations/Wave Equation/Dispersion.md"
ingested: 2026-06-09
---

How do waves move as a group? Consider two travelling sinusoidal waves that have a slight difference in their frequencies:
$$
y(x,t)=A_{0}\cos(k_{1}x-\omega_{1}t)+A_{0}\cos(k_{2}x-\omega_{2}t)
$$
Now, choose $\omega_{1},\omega_{2}=\omega\pm \frac{\delta\omega}{2}$ and $k_{1},k_{2}=k\pm \frac{\delta k}{2}$:
$$
\begin{align}
y(x,t)&=A_{0}\cos \left( \left[ k- \frac{\delta k}{2} \right]x-\left[ \omega- \frac{\delta\omega}{2} \right]t \right)+A_{0}\cos \left( \left[ k+ \frac{\delta k}{2} \right]x+\left[ \omega- \frac{\delta\omega}{2} \right]t \right) \\
&=2A_{0}\underbrace{{\cos(kx-\omega t)}}_{wave}\underbrace{\cos(\delta kx-\delta\omega t)}_{envelope}
\end{align}
$$

Speed of wave is called **phase velocity**.
$$
c_{p}=\omega / k
$$
It describes how fast a particular crest of wave moves.

Speed of envelope is called **group velocity**.
$$
c_{g}=d\omega / \delta k
$$
It describes how fast the overall packet of wave travels.


- When $c_{p}=c_{g}$, there is no dispersion: waves of different frequency travels at same velocity, and waves propagate **without changing shape**.
- When $c_{p}<c_{g}$, higher frequencies travel faster than slow.

[[Wave Equation]]