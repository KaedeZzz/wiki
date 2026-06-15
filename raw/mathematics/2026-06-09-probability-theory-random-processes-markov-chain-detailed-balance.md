---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Markov Chain/Detailed Balance.md"
ingested: 2026-06-09
---

A [[Markov Chain]] with [[Markov Transition Kernel]] $\mathcal{P}$ is *reversible* with respect to the measure $\pi$ if for all $A,B \in \mathcal{X}$:
$$
\int_{A}\mathcal{P}(x,B)\pi(dx)=\int_{B}\mathcal{P}(y,A)\pi(dy)
$$
i.e. the probability of observing the transition $A\to B$ is the same as observing the transition $B\to A$.