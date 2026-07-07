---
source: KaedeSync/_Knowledge/Communications/Digital and Analog Conversion/Response Matching.md
ingested: 2026-07-08
---

[[Continuous-to-Discrete Algebraic Transformations]]

![[Impulse Invariance]]

![[Step Invariance]]

![[Ramp Invariance]]

In fact, any waveform invariance can be considered. In such case, the digital filter will preserve the properties of the continuous filter response to that particular waveform.

How do we choose a proper invariance?
- This depends on how DAC is done.
- If the DAC returns impulse train, then use impulse invariance.
- If the DAC returns step train / "sample and hold", then use step invariance.
- If the DAC returns "first order hold", then use ramp invariance.