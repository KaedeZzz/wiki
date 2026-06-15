---
source: "KaedeSync/_Knowledge/Mathematics/Algebra/Number Theory/Oddity of gcd.md"
ingested: 2026-06-09
---

- if $n_{1}$ and $n_{2}$ are even, 
$$
\gcd(n_{1}, n_{2})=2\gcd\left( \frac{n_{1}}{2}, \frac{n_{2}}{2} \right)
$$
- if $n_{1}$ is even and $n_{2}$ is odd
$$
\gcd(n_{1}, n_{2})=\gcd\left( \frac{n_{1}}{2}, n_{2} \right)
$$
- If both are odd,
$$
\gcd(n_{1}, n_{2})=\gcd\left( n_{1}, \frac{{n_{1}-n_{2}}}{2} \right)
$$

Repetitively use these three rules form a more efficient gcd algorithm than [[Euclid's Algorithm]].

[[Greatest Common Divisor (gcd)]]