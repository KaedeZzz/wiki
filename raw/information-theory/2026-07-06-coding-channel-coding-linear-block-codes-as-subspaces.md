---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Linear Block Codes as Subspaces.md
ingested: 2026-07-06
---

Let $\mathcal C$ be an [[Linear Block Code]] with codewords $\{ c_{0},\dots,c_{M-1} \}$.

$\mathcal C$ is a [[Subspace]] of $\{ 0,1 \}^{n}$: that is, it is closed under vector addition and scalar multiplication.
- For any codewords $\underline{c}_{i},\underline{c}_{j} \in \mathcal C$, $\underline{c}_{i}+\underline{c}_{j}$ is also in $\mathcal C$.
- If $\underline{c}\in\mathcal C$, then $0\cdot {\underline{c}}=\underline{0}$ and $1\cdot{\underline{c}}=\underline{c}$ are in $\mathcal C$. ($\underline{0}$ is always a codeword)

Note that: the rows of a generation matrix $G$ form a basis for $\mathcal C$.
