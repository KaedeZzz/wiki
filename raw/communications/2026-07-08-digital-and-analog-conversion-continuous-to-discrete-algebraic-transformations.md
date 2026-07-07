---
source: KaedeSync/_Knowledge/Communications/Digital and Analog Conversion/Continuous-to-Discrete Algebraic Transformations.md
ingested: 2026-07-08
---

[[Computation Science]]

Algebraic transformations are used to map systems that are *not necessarily band-limited* (avoiding aliasing) at the cost of *some distortion between the frequency response* of the continuous-time system and the frequency response of the digital system.

$$
H(z)=H_{c}(s)|_{s=\psi(z)}
$$

*How to obtain a correct mapping $s=\psi(z)$?* 
Recall that the mapping from z domain to Laplace domain is 
$$
z\to e^{sT}
$$
For small $z$, the expression can be approximated as
$$
z=1+sT+\frac{(sT)^{2}}{2}+o(T^{3})
$$

![[Euler's Method (Forward Difference)]]

![[Backward Difference]]

Why do we not add an order and use quadratic expression?
- How to invert $z=1+sT+\frac{(sT)^{2}}{2}$?
- Replacing every $z$ with a quadratic expression of $s$ would lead to an explosion number of poles and zeros. Simple designs in the $s$ domain would lead to higher order designs in $z$ domain!

![[Bilinear (Tustin's) Transformation]]