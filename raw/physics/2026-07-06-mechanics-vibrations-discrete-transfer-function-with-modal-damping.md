---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Discrete Transfer Function with Modal Damping.md
ingested: 2026-07-06
---

$$
H_{jk}(\omega)=\frac{q_{k}}{F_{j}}=\sum_{n=1}^{N} \frac{{u_{k}^{(n)}u_{j}^{(n)}}}{\omega_{n}^{2}+i{2}\zeta_{n}\omega_{n}\omega-\omega ^{2}}
$$
where the $\zeta_{n}$ are damping ratios.

Impulse response:
$$
h_{jk}(t)=\sum_{n=1}^{N} \frac{u_{j}^{(n)}u_{k}^{(n)}}{\omega_{n}}e^{-\zeta_{n}\omega_{n}t}\sin\omega_{n}t
$$

[[Transfer Function of Vibration]]