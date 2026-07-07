---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Ideal Lowpass Delta Response.md
ingested: 2026-07-08
---

[[Digital Filtering]]

What is the time domain sequence (delta response) of ideal lowpass filter?

[[Inverse Discrete-time Fourier Transform]] gives:
$$
g_{k}=\frac{1}{2\pi}\int_{-\pi}^{\pi}G(e^{j\theta})e^{j\theta k}d\theta=\frac{\theta_{c}}{\pi}\text{sinc}(\theta_{c} k)
$$
note that the filter is non-[[Causal]] and infinite in two sides; it is not realisable, therefore we need to approximate it.
