---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Optimal Decoding of BSC.md
ingested: 2026-07-06
---

For a [[Binary Symmetric Channel]], the number of errors is $d(\underline{y},\underline{c})$ and hence:
$$
Pr(\underline{y}|\underline{c})=p^{d(\underline{y},\underline{c})}(1-p)^{n-d(\underline{y},\underline{c})}=(1-p)^{n}\left( \frac{p}{1-p} \right)^{d(\underline{y},\underline{c})}
$$

Thus, for $\frac{p<1}{2}$, the optimal decoding rule is to decode
$$
\hat{\underline{c}}=\text{arg min}_{\underline{c}\in\{\underline{c}_{1},\dots,\underline{c}_{M}\}}d(\underline{y},\underline{c})
$$
i.e. the optimal decoder for BSC picks the codeword closest in Hamming distance to $\underline{y}$.

![[Optimal BSC Decoding Power]]
