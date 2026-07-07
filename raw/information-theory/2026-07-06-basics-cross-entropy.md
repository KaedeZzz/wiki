---
source: KaedeSync/_Knowledge/Information Theory/Basics/Cross Entropy.md
ingested: 2026-07-06
---

[[Information Theory]]
For probability vector $p$ and one-hot encoding vector $\omega$:
$$
\mathcal L(p,\omega)=-\sum_{i}\omega_{i}\log p_{i}
$$
More generally,
$$
H(P,Q)=\sum_{s}p_{s}\log \frac{1}{q_{s}}
$$
describes the average surprise (information content) by observing a random variable governed by distribution $P$, **but believing in its model** $Q$.
 $$
\text{how often you observe state s }\times\text{ how surprised you will be to see it}
$$

For any model, $H(P,Q)\geq H(P)$ with equality at $P=Q$. 
$\to$ *Any error in the models increases surprise*

Relation with [[KL Divergence]]:
$$
D_{KL}(P||Q)=H(P,Q)-H(P)
$$