---
source: KaedeSync/_Knowledge/Control Theory/Stability/Nyquist/Proof of Nyquist Stability Criterion.md
ingested: 2026-07-06
---

#ESSENTIAL
[[Nyquist Stability Criterion]]

Steps:
1. poles/zeros and encirclements of origin
2. counting elements of the origin
3. poles and zeros of $1+KG(z)$ and corresponding encirclements
4. polynomial degrees vs. number of poles and zeros
5. pole arithmetic
6. shifting the graph to $-1 / K$
7. the Nyquist criterion

![[The Encirclement Property]]

![[Closed Loop Stability]]

Let the rational function described in [[The Encirclement Property]] be $1+KG(z)$, we can obtain:
- $N_{cp,i}=N_{z,i}$ is the number of closed loop poles in the unit circle
- $N_{op,i}=N_{p,i}$ is the number of open loop poles in the unit circle

$$
\mathcal C=N_{cp,i}-N_{op,i}
$$

![[Polynomial Degrees]]

Now, consider
$$
1+KG(z)=\frac{{a(z)+Kb(z)}}{a(z)}
$$
for denominator we are adding two polynomials of same degree; their summation may have equal or less degrees (*for that they might cancel out each other*). So:
$$
\text{deg}(a(z)+Kb(z))\leq \text{deg}(a(z))=\max(m,n)
$$
with equality when $1+Kb(z)=0$. **Let us assume it is not**; hence, $1+KG(z)$ is a fraction of two polynomials with equal degree $\max(m,n)$.

![[Pole Arithmetics]]

**For a closed loop system to be stable, no closed loop pole lies outside the unit circle**. Hence [[Nyquist Stability Criterion]] states that $\mathcal C=N_{op,o}$.

Shifting to encirclement of $-1 / K$:
$$
1+KG(e^{j\theta})\text{ encloses origin} \Leftrightarrow G(e^{j\theta}) \text{ encloses }- \frac{1}{K}
$$
