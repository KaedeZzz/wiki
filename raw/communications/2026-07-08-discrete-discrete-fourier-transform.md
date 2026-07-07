---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform.md
ingested: 2026-07-08
---

The discrete [[Fourier Transform]] of a sequence $x_{n}, n=0,1,\dots,N-1$ is defined by
$$
X_{k}=\sum_{n=0}^{N-1}x_{n}e^{-j 2\pi kn/N}
$$
with inverse DFT
$$
x_{n}=\frac{1}{N}\sum_{k=0}^{N-1}X_{k}e^{j 2\pi kn/N}
$$
The transform maps finite-length sequence $\{ x_{k} \}_{0\leq k\leq N-1}$ to a finite-length sequence $\{ X_{n} \}_{0\leq k\leq N-1}$, which are all vectors.

If we extend the range $0\leq n\leq N-1$ to all integers $n$, the formula gives an $N$-period spectrum as $e^{-j 2\pi k(n+aN)/N}=e^{-j 2\pi kn/N}$.
