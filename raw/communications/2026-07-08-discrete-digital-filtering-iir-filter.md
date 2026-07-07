---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/IIR Filter.md
ingested: 2026-07-08
---

[[Digital Filtering]]

$$
y_{k}=-a_{n-1}y_{k-1}-\dots-a_{0}y_{k-n}+b_{m}u_{(k-n)+(m-1)}+\dots+b_{0}u_{k-n}
$$
- They have finite polynomial representation (at denominator), but infinite impulse response.
- Can be unstable.
- Design methods: direct optimisation of the transfer function, or generation of digital filter from analogue prototype.
- Require shorter delay and lower order to achieve same performance.

![[IIR Design]]