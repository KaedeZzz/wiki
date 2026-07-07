---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Poles and Zeros of Discrete LTI System.md
ingested: 2026-07-08
---

Switch the z-transfer function from negative $z$ powers to positive powers:
$$
G(z)=\frac{Y(z)}{X(z)}= \frac{b_{0}+b_{1}z^{-1}+\dots+b_{m}z^{-m}}{1+a_{1}z^{-1}+\dots+a_{n}z^{-n}}
$$
Assuming $m<n$:
$$
G(z)=\frac{{b_{0}z^{n}+b_{1}z^{n-1}+\dots+b_{m}z^{n-m}}}{z^{n}+a_{1}z^{n-1}+\dots+a_{n-1}z+a_{n}}=\frac{({b_{0}z^{m}+b_{1}z^{m-1}+\dots+b_{m})z^{n-m}}}{z^{n}+a_{1}z^{n-1}+\dots+a_{n-1}z+a_{n}}
$$
or $m>n$:
$$
G(z)=\frac{{b_{0}z^{m}+b_{1}z^{m-1}+\dots+b_{m-1}z+b_{m}}}{z^{m}+a_{1}z^{m-1}+\dots+a_{n}z^{m-n}}=\frac{{b_{0}z^{m}+b_{1}z^{m-1}+\dots+b_{m-1}z+b_{m}}}{(z^{n}+a_{1}z^{n-1}+\dots+a_{n})z^{m-n}}
$$

In both cases, numerator and denominator are polynomials of degree $\max\{ m,n \}$.

![[Fundamental Theorem of Algebra]]

Therefore, both numerator and denominator in both cases have $\max\{ m,n \}$ roots, that is, this discrete [[Linear Time-Invariant (LTI)]] system has $\max\{ m,n \}$ zeros and $\max\{ m,n \}$ poles. Dependent on relationship between $m$ and $n$, there will be $|m-n|$ zeros **or** $|m-n|$ poles.

For an FIR filter:
$$
G(z)=\frac{{b_{0}z^{m}+b_{1}z^{m-1}+\dots+b_{m-1}z+b_{m}}}{z^{m}}
$$

so all poles of an FIR filter are at $z=0$.