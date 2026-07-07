---
source: KaedeSync/_Knowledge/Communications/Filter Design/Filtering Windows.md
ingested: 2026-07-08
---

[[Digital Filtering]]

Frequency distortion is reduced by adopting different windows; i.e. we do not use a rectangular window to truncate the $\text{sinc}$, but use other windows.

![[Pasted image 20250103024718.png]]

Note that, all windows satisfy $w_{k}=w_{N-k}$. If the desired impulse response also satisfies such, then applying windows always give *linear phase filters*.

In frequency domain:

![[Pasted image 20250103024817.png]]

Characteristics:

![[Pasted image 20250103024850.png]]

- Smaller side lobes yield better approximations of the ideal response.
- Increasing $N$ decreases transition bandwidth. The transition band is symmetric at cutoff frequency $\omega_{c}$. 
- For passband error and stopband approximation, the peak approximation error $\delta$ is the same.

![[Window Methods]]