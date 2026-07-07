---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Discrete Memoryless Channel.md
ingested: 2026-07-06
---

[[Channel Coding]]

A discrete memoryless channel (DMC) is a system consisting of an input alphabet $\mathcal X$ , output alphabet $\mathcal Y$, and a set of transition probabilities:
$$
P_{Y|X}(b|a)=\text{Pr}(Y=b|X=a)\text{ for all }a,b
$$
*”Given all the past, the current output depends only on the current input”*

For a general DMC, We’ll construct a set of input sequences which have *non-intersecting, "non-confusable" sets of output sequences* with high probability.
