---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Butterworth Filter.md
ingested: 2026-07-08
---

[[Digital Filtering]]

$N$-th order low pass filter.
$$
G_{c}(s)=\frac{1}{1+\left( \frac{s}{\omega_{c}} \right)^{N}}
$$
such that $G_{c}(s)$ satisfies
$$
G_{c}(s)G_{c}(-s)=\frac{1}{1+\left( \frac{s}{j\omega_c} \right)^{2N}}
$$
Unit DC gain, $-3dB$ cutoff frequency at $s=j\omega_c$.
The higher the order, the sharper the transition is.

![[Pasted image 20250102150723.png]]

Pole of $G_{c}(s)G_{c}(-s)$ satisfies:
$$
\left( \frac{s}{j\omega_{c}} \right)^{2N}=-1,\quad i.e.\quad s=j\omega_{c}e^{\frac{j(2k+1)\pi}{2N}}
$$
and those poles are on the unit circle.
- Note that, if $p_{i}$ is a pole of $G_{c}(s)$, then $-p_{i}$ is a pole of $G_{c}(-s)$. Therefore, the poles of $G_{c}(s)$ are the poles that lie on the left hand side of the plane.
- The transfer function may then be written as
$$
G_{c}(s)=\prod _{i=1}^{P} \frac{1}{s+p_{i}}
$$
