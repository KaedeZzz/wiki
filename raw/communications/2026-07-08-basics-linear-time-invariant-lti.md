---
source: KaedeSync/_Knowledge/Communications/Basics/Linear Time-Invariant (LTI).md
ingested: 2026-07-08
---

Abbreviated as LTI System (LTIS).
- Linear:
$$L(\alpha_{1}u_{k}+\alpha_{2}u_{k}')=\alpha_{1}L(u_{k})+\alpha_{2}L(u_{k}')$$ (*linear decomposition*)
- Time-invariant:  $$L(u_{k+m})=y_{k+m}\text{ for any }m$$(*shift of input results in same shift of output*)

For a discrete LTIS, we can write:
$$
Y_{t}=\sum_{k=-\infty}^{\infty}h_{k}X_{t-k}
$$
which is a [[Discrete Convolution]] of input signal and LTI filter.

If the input to a LTIS is [[Wide-Sense Stationary]], the output is also wide-sense stationary.

[[Control]], [[Signal Processing]]