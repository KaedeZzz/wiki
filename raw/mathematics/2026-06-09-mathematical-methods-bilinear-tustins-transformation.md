---
source: "KaedeSync/_Knowledge/Mathematics/Mathematical Methods/Bilinear (Tustin's) Transformation.md"
ingested: 2026-06-09
---

[[Continuous-to-Discrete Algebraic Transformations]]

$$
s=\frac{2}{T} \frac{{z-1}}{z+1}
$$
or simply
$$
s= \frac{{z-1}}{z+1}
$$

Motivation: why do we do that specifically?
$$
\begin{align}
s&=\frac{2}{T} \frac{{z-1}}{z+1}\implies z=\frac{{1+\frac{sT}{2}}}{1-\frac{sT}{2}}\\ \\
\overset{\text{quad. approx.}}\implies z&=\left( 1+\frac{sT}{2} \right)\left( 1-\frac{sT}{2} \right)^{-1} \\
 & =\left( 1+\frac{sT}{2} \right)\left( 1+\frac{sT}{2}+\frac{(sT)^{2}}{4}+O(T^{3})  \right) \\
&=1+sT+\frac{(sT)^{2}}{2}+O(T^{3})
\end{align}
$$
The expression "coincides" with the quadratic expansion of $e^{sT}$; it gets a "quadratic" approximation **without** actually inverting a quadratic and an increase in zeros/poles in the expression.



