---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Fixed-length Source Code.md
ingested: 2026-07-06
---

A fixed-length data compression scheme is defined by:
1. Encoder $\phi:\mathcal{V}^{n}\to \{ 1,\dots, M \}$
2. Decoder $\psi: \{ 1,\dots,M \}\to \mathcal{V}^{n}\cup \{ e \}$ (error)

The probability of error is the probability that reconstruction is not equal to the original sequence:
$$
p_{e}(M)=\mathbb{P}[\psi(\phi(V^{n}))\neq V^{n}]
$$

[[Source Coding]]