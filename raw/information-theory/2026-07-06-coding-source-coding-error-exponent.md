---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Error Exponent.md
ingested: 2026-07-06
---

Consider a [[Discrete Memoryless Source]] $\{ V^{n} \}_{n=1}^{\infty}$. There exists a source code with $M=e^{nR}$ codewords such that
$$
p_{e}\leq e^{-ne(R)}
$$
where
$$
e(R)=\max_{\rho> 0}\rho R-E_{s}(\rho)
$$
is the reliability function, a.k.a. optimal error exponent function, with
$$
E_{s}(\rho)=\log\left( \sum_{i=1}^{\lvert \mathcal{V} \rvert }P_{V}(v_{i})^{\frac{1}{1+\rho}} \right)^{1+\rho}
$$

An error exponent is the rate at which the (best achievable) probability of error decays exponentially with blocklength $n$.

Consider optimal probability of error as a function of rate:
$$
P_{e}^{*(n)}(R)=\min_{\text{codes of rate }R}\ \min_{\text{decoders}}P_{e}^{(n)}
$$
then the reliability function is defined as:
$$
e(R)=\limsup_{n\to \infty} -\frac{1}{n}\ln P_{e}^{*(n)}(R)
$$