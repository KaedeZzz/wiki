---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Radix-2 FFT.md
ingested: 2026-07-08
---

[[Fast Fourier Transform]] of $N=2^{n}$.

Complexity:
- $N$ can be divided into $L=2$ and $M=2^{n-1}$, resulting in $2^{n-1}$ two-point FFTs, $2^{n}$ twiddle factor multiplications, and two $2^{n-1}$-point FFTs. 
- The number of multiplication needed is hence $2^{n}+2\times(\text{\#multiplication of }2^{n-1}\text{-point FFT})$
- As we further divide the FFT, only $2^{n}$ twiddle factor multiplications add up
- We can divide the FFT at most $n$ times, so the number of multiplications is $nN=N\log_{2}N$.


