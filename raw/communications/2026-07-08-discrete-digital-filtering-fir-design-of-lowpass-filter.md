---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/FIR Design of Lowpass Filter.md
ingested: 2026-07-08
---

[[FIR Filter]]

The approach we usually adopt to create an FIR filter that mimics the idea lowpass filter is to:
- shift the $\text{sinc}$ into [[Causal]] region (do a delay), and 
- truncate at $N+1$ samples of the ideal response (keep the response symmetric). 

![[Pasted image 20250102152432.png]]

For ideal filter $h_{k}$, the designed filter is then:
$$
g_{k}=h_{k-\frac{N}{2}}
$$
Larger $N$ causes longer delay but less distortion (from truncation).

![[Effect of Truncation of Ideal Lowpass Filter]]

**Multi-band FIR filter design**: composition of lowpass filters