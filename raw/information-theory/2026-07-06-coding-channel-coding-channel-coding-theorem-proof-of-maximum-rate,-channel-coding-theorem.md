---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Coding Theorem/Proof of Maximum Rate, Channel Coding Theorem.md
ingested: 2026-07-06
---

[[Channel Coding Theorem]]

Consider a length $n$, rate $R$ channel code, i.e. $2^{nR}$ codewords.
Probability of error defined as
$$
P_{e}=Pr(\hat{W}\neq W)=\frac{1}{2^{nR}}\sum_{k=1}^{2^{nR}}Pr(\hat{W}\neq k|W=k)
$$
Fano's inequality applied to this problem gives:
$$
H(W|\hat{W})\leq 1+P_{e}\log 2^{nR}=1+P_{e}nR
$$

![[Channel Information Lemma]]