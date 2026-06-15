---
source: KaedeSync/_Knowledge/Machine Learning/Hidden Markov Model/Viterbi Approximation.md
ingested: 2026-06-08
---

$$
p(x_{1},\dots,x_{T})=\sum_{q \in Q^{T}}p(x_{1},\dots,x_{T},q)\approx p(x_{1},\dots,x_{T},\hat{q})
$$
where
$$
\hat{q}=\arg\max_{q \in Q^{T}}p(x_{1},\dots,x_{T},q)
$$
Instead of summing over all state sequences, Viterbi keeps only the **best path**. This yields:
- an approximate likelihood (a lower bound),
- the best state sequence through the [[Hidden Markov Model]].

Interpretation: at each time and state,
- consider all ways to arrive there,
- keep only the best one, ($\to$ [[Dynamic Programming]] idea)
- extend that forward.