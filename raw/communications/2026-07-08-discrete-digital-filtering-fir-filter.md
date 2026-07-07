---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/FIR Filter.md
ingested: 2026-07-08
---

[[Digital Filtering]]

$$
y_{n}=\sum_{k=0}^{N}g_{k}u_{n-k}
$$
- It is feedforward (non-recursive).
- Realised efficiently in hardware (via [[Fast Fourier Transform]]).
- Can have exact linear phase: $G(e^{j\theta})=|G(e^{j\theta})|e^{-j\theta}$ #SUPO this allows the shape of the signal be obtained through the filter.
- Inherently stable: $G(z)=\frac{{\sum_{k=0}^{N}g_{k}z^{N-k}}}{N}$, so all poles are at $0$.
- Design methods are generally linear: easy and efficient.
- Require higher order of filter and larger delay for same level of performance.