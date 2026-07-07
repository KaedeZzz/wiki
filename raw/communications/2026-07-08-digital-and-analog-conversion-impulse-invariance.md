---
source: KaedeSync/_Knowledge/Communications/Digital and Analog Conversion/Impulse Invariance.md
ingested: 2026-07-08
---

Suppose $G_{c}(s)$ is a Laplace transform continuous-time filter. 

Definition of *impulse invariance*: the impulse response of the corresponding impulse invariance digital filter $G(z)$ (with sampling interval $T$) is equal to the impulse response of the $G_{c}(s)$ sampled at $t=kT$.

That is, if we feed an **impulse** into the analog filter $G_{c}(s)$, then **sample** it with interval $T$, we get the same signal as the **delta response** of digital filter $G(z)$.

The relationship between digital and analog filters is then:
$$
G(z)=\mathcal Z(\mathcal L^{-1}(G_{c}(s))_{t=kT})
$$
which is a series of operations:
- inverse [[Laplace Transform]] of analog filter to get impulse response
- sample continuous response with $t=kT$
- [[z-Transform]] of the discrete delta response to get digital filter

Properties:
- For **band-limited filters**, the discrete filter frequency response will closely approximate the continuous-time frequency response.
- Stability is preserved:
$$
 \int|e^{\beta t}|dt<\infty\implies \mathrm{Re}\{ \beta \}<0\implies\sum|e^{\beta Tk}|<\infty
$$

This works well only when Laplace transform is well known. It cannot measure a response: $\delta_{k}$ cannot be converted to $\delta(t)$.
