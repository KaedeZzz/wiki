---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Irreducible Aperiodic Chain.md"
ingested: 2026-06-09
---

An [[Irreducible]] [[Aperiodic]] [[Markov Chain]] is a chain in which all states are reachable from one another and all states are aperiodic.

If $(Q^{n})_{ij}>0$ for all $i,j$ for some $n$, then the chain is irreducible and aperiodic.

For an irreducible aperiodic chain, either
$$
\lim_{ t \to \infty }P(X_{t}=j|X_{0}=i)=\pi_{j} 
$$
for all $i,j$, else
$$
\lim_{ t \to \infty }P(X_{t}=j|X_{0}=i)=0
$$
in either case, the chain "forgets" it was initially at $i$.

- We approach $\pi$ if the chain is positive recurrent
- If the state space is finite, we always approach $\pi$.
- Rate of approach determined by $|\lambda_{2}|$, the second eigenvalue of $Q$.

[[Eigenvalue and Eigenvector]]