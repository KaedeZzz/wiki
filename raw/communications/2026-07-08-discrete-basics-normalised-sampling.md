---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Normalised Sampling.md
ingested: 2026-07-08
---

[[Sampling]]

Discrete-time signal could be considered as a sample of a continuous signal:
$$
s_{k}=s(kT)
$$
Consider: 
- The sampling we have learned in continuous communications is a "*train of impulses*" whose interval is a time of **sampling period**. However, discrete-time signal does not incorporate time information; it is purely sequence of numbers.
- *Do we lose information of time by converting continuous signal into discrete-time signal?*  It appears that we do, but we should include the information!
- Intuitively, we can note the sampling frequency together with the sampled discrete-time signal. This is good, but furthermore, how should we import the concept of **frequency** into sequence of **numbers**?
- Answer: assume two values in a (time-less) sequence are separated by $T=1s$!
- Therefore, the discrete-time signal is *not* exactly a sampled version of continuous signal, but a time-domain *stretch* of the sample. 
- Note that the frequency times period is always $2\pi$ in any domain:
$$
(f_{\text{norm. sampling}}T_{\text{norm. sampling}}=2\pi \times1)=f_{\text{sampling}}T_{\text{sampling}}
$$
where $T_{\text{sampling}}$ is the sampling interval of the digital signal, and $T_{\text{norm. sampling}}=1s$.
- Therefore, all frequencies in the *sequence-of-number* domain and the *real world sampling* domain follow the same ratio:
$$
f_{\text{normalised}}=\frac{T_{\text{sampling}}}{2\pi}f
$$
