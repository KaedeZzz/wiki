---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Using z-Transform to Solve Difference Equation.md
ingested: 2026-07-08
---

[[z-Transform]] and [[Difference Equation]]

General steps: 
1. obtain difference equation 
2. do its z-transform 
3. solve algebraically for z-domain expression of $Y$ 
4. inverse z-transform of $Y$
5. got solved sequence $y$

Example: solve
$$
y_{k+2}=y_{k+1}-0.25y_{k}+u_{k}
$$
with initial conditions $y_{0}=1$, $y_{1}=0$
Transform to $z$ domain:
$$
z^{2}Y(z)-z^{2}=zY(z)-z-0.25Y(z)+ U(z)
$$
Then solve for $Y(z)$, then do inverse z-transform.

