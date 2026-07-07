---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Continuous Transfer Function with Damping.md
ingested: 2026-07-06
---

Transfer function with light damping:
$$
G(x,y,\omega)\approx \sum_{n} \frac{{u_{n}(x)u_{n}(y)}}{\omega_{n}^{2}+2i\zeta_{n}\omega_{n}\omega-\omega ^{2}}
$$
where $\zeta_{n}$ is the modal [[Damping Factor]] which is dimensionless.

The corresponding impulse response is given by:
$$
g(x,y,t)\approx \sum_{n} \frac{{u_{n}(x)u_{n}(y)}}{\omega_{n}}e^{-\zeta_{n}\omega_{n}t}\sin(\omega_{n}t)
$$
each term of the sum is simply the response of a damped mass-on-spring oscillator.

[[Continuous Vibration Transfer Function]]