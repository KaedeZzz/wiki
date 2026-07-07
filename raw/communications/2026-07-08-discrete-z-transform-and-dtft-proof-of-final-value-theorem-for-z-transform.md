---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Proof of Final Value Theorem for z-Transform.md
ingested: 2026-07-08
---

Since all poles of $(z-1)Y(z)$ lie strictly in the unit circle, all poles of $Y(z)$ should also be in the unit circle, except possibly a non-repeated pole at $z=1$ (repeated is impossible).

Assuming **distinct poles** and $|p_{i}|<1$, we can write
$$
Y(z)=\frac{\alpha_{0}}{1-z^{-1}}+\sum_{i} \frac{\alpha_{i}}{1-p_{i}z^{-1}}
$$
therefore
$$
y_{k}=\alpha_{0}+\sum_{i}\alpha_{i}p_{i}^{k}
$$
by inverse z-Transform:
$$
\lim_{ k \to \infty } y_{k}=\lim_{ k \to \infty } \left(\alpha_{0}+\sum_{i}\alpha_{i}p_{i}^{k}\right)=\alpha_{0}
$$
also,
$$
\lim_{ z \to 1 } (z-1)Y(z)=\lim_{ z \to 1 } \left(z\alpha_{0}+(z-1)\sum_{i} \frac{\alpha_{i}}{1-p_{i}z^{-1}}\right)=\alpha_{0}
$$
Proof.

The theorem still holds true if the poles are not distinct; only that forms of summations would be different, the limits are still the same.