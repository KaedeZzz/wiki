---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Cyclic Properties of DFT Matrix 1.md
ingested: 2026-07-08
---

![[Remainder Function]]

Any integer can be written as $k=qN+r$. Then:
$$
W_{N}^{k}=W_{N}^{qN+r}=W_{N}^{r}=W_{N}^{R_{N}(k)}
$$
Hence, the DFT Vandermonde matrix can be re-written so that powers of $W_{N}$ higher than $N-1$ are expressed as powers between $0$ and $N − 1$.

[[DFT Matrix]]