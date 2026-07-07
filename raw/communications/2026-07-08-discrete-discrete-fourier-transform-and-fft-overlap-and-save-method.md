---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Overlap and Save Method.md
ingested: 2026-07-08
---

The method is a systematic way to do linear convolution of a [[Semi-Infinite Sequence]] with an [[FIR Filter]], taking the core idea from the one introduced in [[Linear Convolution from Circular Convolution]]. 

Specifically, the method uses [[Fast Fourier Transform]] of length $N$ to do linear convolutions with an FIR of length $L+1\ll N$.


![[Pasted image 20250106193717.png]]

###### Steps
- From the source semi-infinite sequence $\vec{x}$, each time we take a sequence of length $N$, with $L$ elements overlapping with the former sequence (or $0$s for the first sequence)
- We make a filter of length $N$ with first $L+1$ bits being content of the FIR filter $\vec{h}$ and the rest being $0$.
- Do FFT of them, point-wise multiply, and do inverse FFT to obtain the convolution result.
- Discard the first $L$ terms (from [[Circular Convolution]]), and the rest be parts of the final convolved semi-infinite sequence.
