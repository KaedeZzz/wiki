---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/The Kolmogorov Axioms.md"
ingested: 2026-06-09
---

Monotonicity:
$$
\text{if }A\subseteq B,\text{ then }P(A)\leq P(B)
$$
Probability of the empty set:
$$
P(\emptyset)=0
$$
Complement rule:
$$
P(A^C)=1-P(A)
$$
Numeric bound:
$$
0\leq P(A)\leq 1 \quad\forall A\subset \Omega
$$
Addition Law:
$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$
Sum rule:
$$
P(A\cap B) + P(A\cap B^C)=P(A)
$$

Additionally:
Product rule(essentially marginal):
$$
P(r)=\sum_{s}P(s,r)
$$