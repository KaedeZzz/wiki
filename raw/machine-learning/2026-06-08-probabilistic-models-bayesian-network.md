---
source: KaedeSync/_Knowledge/Machine Learning/Probabilistic Models/Bayesian Network.md
ingested: 2026-06-08
---

A Bayesian network $\mathcal G$ is a directed acyclic graph whose nodes are random variables $X_{1},\dots,X_{d}$.

Let $PA_{X_{i}}^{\mathcal G}$ be the parents of $X_{i}$ in $\mathcal G$, the network is annotated with (*edges are*) conditional distributions $p(X_{i}|PA_{X_{i}}^{\mathcal G})$.

**Factorisation Rule**
$$
p(X_{1},\dots,X_{d})=\prod_{i=1}^{d}p(X_{i}|PA_{X_{i}}^{\mathcal G})
$$
Instead of one huge joint model, you only specify one local conditional for each node.

**Conditional Independence**
$X_{i}$ is independent to non-descendants of $X_{i}$ in $\mathcal G$, denoted $\text{ND}_{X_{i}}^{\mathcal G}$, given condition of $PA_{X_{i}}^{\mathcal G}$. That is:
$$
(X_{i}\perp\text{ND}_{X_{i}}^{\mathcal G}|PA_{X_{i}}^{\mathcal G}),i=1,\dots,d
$$
Once you know a node's parents, it is independent of everything upstream that is not its descendant.

[[Conditional Independence]]