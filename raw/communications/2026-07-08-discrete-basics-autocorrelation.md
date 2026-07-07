---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Autocorrelation.md
ingested: 2026-07-08
---

[[Random Processes]]

The autocorrelation function for zero-mean process $\{ X_{t} \}$ is:
$$
R_{X}(t,t+k)=\mathbb{E}\{X_{t}X_{t+k}\}
$$
For a [[Wide-Sense Stationary]] process, this does not depend on $t$, so we have
$$
R_{X}(k)=\mathbb{E}\{X_{t}X_{t+k}\}=\mathbb{E}\{X_{0}X_{k}\}
$$
By writing $R_{X}(k)$ we implicitly assume WSS.

Properties:
- $R_{X}$ is an even function
- $R_{X}(0)\geq 0$
- $|R_{X}(k)|\leq R_{X}(0)$

