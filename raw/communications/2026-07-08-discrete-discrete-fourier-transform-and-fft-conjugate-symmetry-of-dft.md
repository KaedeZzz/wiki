---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Conjugate Symmetry of DFT.md
ingested: 2026-07-08
---

[[Discrete Fourier Transform]]

In a [[DFT Matrix]] $\mathbf{F}$,
$$
\vec{f}_{n}=\vec{f}_{N-n}^{*}
$$
i.e. columns $1$ to $\left\lceil  \frac{N}{2}-1  \right\rceil$ comes in conjugate pairs with columns $N$ to $\left\lfloor  \frac{N}{2}+1  \right\rfloor$, and column $0$ (and $\frac{N}{2}$ for even $N$) are real.

Hence, if the input vector is real, the frequency domain output vector exhibits conjugate symmetry
$$
X_{n}=X^{*}_{N-n}
$$

Conversely, if input time-domain vector obeys the conjugate symmetry property, its DFT is real.