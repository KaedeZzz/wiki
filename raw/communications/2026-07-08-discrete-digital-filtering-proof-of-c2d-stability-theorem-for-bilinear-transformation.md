---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Proof of C2D Stability Theorem for Bilinear Transformation.md
ingested: 2026-07-08
---

Proof of [[C2D Stability Theorem]] for [[Bilinear (Tustin's) Transformation]]:
Let the transformation be
$$
s= \psi(z)=\frac{{z-1}}{z+1}\implies z= \frac{{1+s}}{1-s}
$$
For some pole of the continuous system, $s=\lambda+j\omega$:
$$
|z|^{2}=zz^{*}=\frac{{(1+\lambda)^{2}+\omega ^{2}}}{(1-\lambda)^{2}+\omega ^{2}}
$$

If the continuous system is to be stable, all possible poles $s$ must satisfy [[Open Loop Stability Criterion]] such that all possible $\lambda$ has to satisfy $\lambda\leq 0$; this results in $|z|^{2}\leq 1$ such that all discrete-time system poles are inside the unit circle and thus the discrete-time system is also stable.