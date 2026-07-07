---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Minimax Redundancy.md
ingested: 2026-07-06
---

Suppose that we know that the true distribution $P$ is one from a set of distributions $\mathcal P$, then we would like to design a code that *minimises* the **worst-case redundancy** over the class of distributions $\mathcal P$, that is,
- Choose $\hat{ P}$ to minimise $\max_{P \in \mathcal P}D(P||\hat{P})$ 

with this choice, the value of $D(P||\hat{P})$ after $\hat{ P}$ chosen, that is,
$$
R^{*}=\min_{\hat{P}}\max_{P \in \mathcal P}D(P||\hat{P})
$$
is called *minimax redundancy*.