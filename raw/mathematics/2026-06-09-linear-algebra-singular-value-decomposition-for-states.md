---
source: "KaedeSync/_Knowledge/Mathematics/Linear Algebra/Singular Value Decomposition for States.md"
ingested: 2026-06-09
---

![[Singular Value Decomposition]]

Decompose the state of [[Mechanics and Dynamics]] into multiple "eigenstates":
$$
\mathbf{u}(x,t)\approx \bar{\mathbf{u}}+\sum_{k=1}^{r}\phi_{k}(\mathbf{x})a_{k}(t)
$$
Essentially a *data-driven generalisation* of the [[Fourier Transform]].

Can be viewed as a shallow (1 hidden layer), **linear** [[Autoencoder]]. 