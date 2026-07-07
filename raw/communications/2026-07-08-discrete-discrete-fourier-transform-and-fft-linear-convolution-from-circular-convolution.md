---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Linear Convolution from Circular Convolution.md
ingested: 2026-07-08
---

The linear [[Discrete Convolution]] of arbitrary sequences cannot in general be computed via an FFT.

However, if we consider an [[FIR Filter]] with length $L+1$ such that
$$
\{ y_{k} \}_{k\geq 0}=\{ h_{k} \}_{0\leq k\leq L}*\{ x_{k} \}_{k\geq 0}
$$
i.e.
$$
y_{k}=\sum_{l=0}^{L}h_{l}x_{k-l}
$$
if we take a block $\vec{x}=x_{0},\dots,x_{N-1}$ and evaluate the [[Circular Convolution]] $\vec{y}_{c}=\vec{h}\circledast \vec{x}$:
- The first $L$ entries will be different because they depends on the last $L$ terms of $\vec{x}$ which is supposed to have no dependence for linear convolution; yet, the other entries stay the same as linear convolution.
- If $N\gg L$, then circular convolution ( and thus FFT) can be used to evaluate linear convolution.