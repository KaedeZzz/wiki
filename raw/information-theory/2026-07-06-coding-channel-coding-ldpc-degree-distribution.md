---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Degree Distribution.md
ingested: 2026-07-06
---

###### Node-perspective Polynomials

$L_{i}$: fraction of left (variable) nodes of degree $i$, i.e. the fraction of columns of $H$ with weight $i$.
$R_{i}$: fraction of right (check) nodes of degree $i$, i.e. the fraction of rows of $H$ with weight $i$.

Can be written as polynomials:
$$
L(x)=\sum_{i=1}^{d_{v,\max}}L_{i}x^{i},\quad R(x)=\sum_{i=1}^{d_{c,\max}}R_{i}x^{i}
$$
Average degrees:
$$
\bar{d}_{v}=L'(1),\quad \bar{d}_{c}=R'(1)
$$
Hence design rate is:
$$
\frac{k}{n}=1- \frac{\bar{d}_{v}}{\bar{d_{c}}}=1-\frac{L'(1)}{R'(1)}
$$
###### Edge-perspective Polynomials

$\lambda_{i}$: fraction of edges connected to variable nodes of degree $i$, i.e. the fraction of ones in $H$ in columns of weight $i$.
$\rho_{i}$: fraction of edges connected to check nodes of degree $i$, i.e. the fraction of ones in $H$ in rows of weight $i$.

The edge perspective polynomials are
$$
\lambda(x)=\sum_{i=1}^{d_{v,\max}}\lambda_{i}x^{i-1}, \quad \rho(x)=\sum_{i=1}^{d_{c,\max}}\rho_{i}x^{i-1}
$$
It can be shown that
$$
\bar{d}_{c}=\left( \int_{0}^{1}\lambda(x)dx \right)^{-1},\quad \bar{d}_{v}=\left( \int_{0}^{1}\rho(x)dx \right)^{-1}
$$

[[Message Passing]]