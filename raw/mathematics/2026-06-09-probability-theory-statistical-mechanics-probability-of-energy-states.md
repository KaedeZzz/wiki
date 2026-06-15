---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Statistical Mechanics/Probability of Energy States.md"
ingested: 2026-06-09
---

Consider 1st and 2nd law of thermodynamics:
- Energy is conserved.
- Entropy is maximised.
In this case the entropy is:
$$
S[P]=-\sum_{\sigma}P(\sigma)\log P(\sigma)
$$
we need to find the distribution $P$ that maximises the entropy $S$ subject to the energy conservation law:
$$
\max_{P} S\quad s.t. \quad \sum_{\sigma}P(\sigma)=1,\quad \sum_{\sigma}E(\sigma)P(\sigma)=const.
$$
solution: use the [[Lagrangian Multiplier]] to construct a lagrangian:
$$
\mathcal{L}=-\sum_{\sigma}P(\sigma)\log P(\sigma)-\lambda \left( \sum_{\sigma} P(\sigma)-1\right)-\beta\left( \sum_{\sigma}E(\sigma)P(\sigma)-U \right)
$$
where $U$ is considered a constant here.
Then, the Lagrangian will be optimised with respect to all parameters.
$$
\begin{align}
\frac{{\partial L}}{\partial P(\sigma)} & =
-1-\log P(\sigma)-\lambda-\beta E(\sigma)=0 \text{ (at a particular }\sigma\text{)}\\
\log P(\sigma) & =-\beta E(\sigma)-\lambda-1 \\
P(\sigma) & =\frac{e^{-\beta E(\sigma)}}{e^{\lambda-1}}=\frac{e^{-\beta E(\sigma)}}{Z}
\end{align}
$$
Physically, $\beta=\frac{1}{T}$.
According to constraint $\sum_{\sigma}P(\sigma)=1$, $Z=\sum_{\sigma}e^{-\beta E(\sigma)}$, and we have derived [[Boltzmann Distribution]].
In language of [[Statistical Mechanics]], the probability of a state is the exponential of the negative beta times energy.

