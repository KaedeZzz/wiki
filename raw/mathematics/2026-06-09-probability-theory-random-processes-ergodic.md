---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Ergodic.md"
ingested: 2026-06-09
---

The time average for a particular **realisation** out of a random process is:
$$
\langle f(x)\rangle=\lim_{ T \to \infty } \sum_{t=1}^{T}f(x_{t})
$$
A process is **ergodic** if $\langle f(x) \rangle$ converges to the same value ($\mathbb{E}X$) for any realisation.

In particular, a process is "mean ergodic" if
$$
\mathbb{E}X=\lim_{ N \to \infty } \frac{1}{N}\sum_{k=0}^{N-1}X_{k}
$$
and "autocorrelation ergodic" if
$$
r_{XX}(k)=\mathbb{E}\{X_{0}X_{k}\}=\lim_{ N \to \infty }  \frac{1}{N}\sum_{k=0}^{N-1}X_{0}X_{k}
$$
*[[Positive Recurrent]] [[Irreducible Aperiodic Chain]] is ergodic.*

![[Mean Ergodicity Theorem]]

[[Random Processes]]