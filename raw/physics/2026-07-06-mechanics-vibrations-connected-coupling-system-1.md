---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Connected Coupling System 1.md
ingested: 2026-07-06
---

A particular case of coupling that is simple to treat occurs when *two systems are connected together at a point*.

We could measure or calculate the driving point transfer functions for each subsystem when they are uncoupled:
$$
G_{1}\equiv \frac{Y_{1}(\omega)}{F_{1}(\omega)},\quad G_{2}\equiv \frac{Y_{2}(\omega)}{F_{2}(\omega)}
$$
We can imagine applying an external force at the same point as where they are coupled. In this case, applying *continuity* and *equilibrium*:
$$
Y_{1}=Y_{2}=Y,F_{1}+F_{2}=F_{ext}
$$
combining:
$$
\begin{align}
Y\left( \frac{1}{G_{1}}+\frac{1}{G_{2}} \right) & =F_{ext} \\
G=\frac{Y}{F_{ext}}=\frac{G_{1}G_{2}}{G_{1}+G_{2}}
\end{align}
$$
- The peak occurs when $G_{1}=-G_{2}$.
- The antiresonance occurs when $G_{1}=0$ or $G_{2}=0$.

Special cases:
- if $\lvert G_{1} \rvert\gg \lvert G_{2} \rvert$, then $G_{c}\approx G_{1}$.
- if $G_{1}=G_{2}$, then $G_{c}=\frac{G_{1}}{2}$. Notice that in this case half of the peaks disappear: antisymmetric modes that have a node at the coupling position will not have their resonance frequency shown in frequency response plot.

[[Transfer Function of Vibration]]