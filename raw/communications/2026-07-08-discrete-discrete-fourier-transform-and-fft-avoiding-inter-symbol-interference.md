---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Avoiding Inter-Symbol Interference.md
ingested: 2026-07-08
---

![[Inter-Symbol Inference (ISI)]]

We can use the [[Fast Fourier Transform]] to communicate in the frequency domain as follows:
- Preparing the signal in the frequency domain, by mapping the signal into $N$ constellations
- Take an inverse FFT, and transmit the resulting time-domain vector
- At the receiver, take an FFT and process the frequency domain vector

In doing this, the time domain convolution has become frequency domain multiplication; **note that multiplying constellation symbols does not cause interference between symbols, so ISI is eliminated.**

However, to practically achieve this, the channel must do [[Circular Convolution]] where it instead does linear convolution, so we have to "trick" the channel to do so.

![[Orthogonal Frequency-Domain Modulation (OFDM)]]