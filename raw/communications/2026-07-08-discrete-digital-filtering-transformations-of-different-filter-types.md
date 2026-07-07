---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Transformations of Different Filter Types.md
ingested: 2026-07-08
---

Prototypes are typically low pass; standard transformations can be used to convert a lowpass prototype into other types.

Assuming a lowpass prototype with cutoff at $1$:
- Lowpass to lowpass: set $s=\frac{\bar{ s}}{\omega_{c}}$ to change cut off frequency to $\omega_{c}$.
- Lowpass to highpass: set $s=\frac{\omega_{c}}{\bar{s}}$ to get high pass with cut off frequency $\omega_{c}$.
- Lowpass to bandpass: set $s=\frac{{\bar{s}^{2}+\omega_{l}\omega_{u}}}{\bar{ s}(\omega_{u}-\omega_{l})}$ to get bandpass with lower cutoff $\omega_{l}$ and upper cutoff $\omega_{c}$.
- Lowpass to bandstop: set $s=\frac{\bar{ s}(\omega_{u}-\omega_{l})}{{\bar{s}^{2}+\omega_{l}\omega_{u}}}$
