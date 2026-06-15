---
source: KaedeSync/_Knowledge/Machine Learning/Gaussian Process/Gaussian Process.md
ingested: 2026-06-08
---

*A Gaussian process is a collection of random variables, any finite number of which have joint Gaussian distributions*. In other words, it is a generalisation of a [[Multivariate Gaussian]] to **infinitely many** variables.
- Informally, infinitely long vector $\approx$ function

A Gaussian process is fully specified by a mean function $m(x)$ and a covariance function $k(x,x')$ over the domain of **argument** $x$:
$$
f\sim \mathcal{N}(m(x),k(x, x')),\quad x,x' \in \mathcal{X}
$$
note: $f$ and $m$ are defined on $\mathcal{X}$, and $k$ is defined on $\mathcal{X}\times \mathcal{X}$.
The argument plays the role of index set: for every input $x$, there is an associated random variable $f(x)$ which is the value of the function $f$ at the location.

**if we define a finite set of arguments(indices) to draw samples from the Gaussian process, we will get a random vector distributed in multivariate Gaussian.** That is, if we say a function is distributed as a Gaussian process:
$$
\mathbf{f}\sim \mathcal{N}(m,k)
$$
then, given arguments $\mathbf{x}$, the drawn samples (functions) will be distributed as
$$
f(\mathbf{x})\sim \mathcal{N}(\mu,\mathbf{\Sigma})\text{ where }\mu_{i}=m(x_{i})\text{ and }\mathbf{\Sigma}_{ij}=k(x_{i},x_{j})
$$
in other words, we can say $f(\mathbf{x})$ is a **marginalization** of the full Gaussian process.
*Repeatedly drawing samples from Gaussian process is to drawing samples from multivariate Gaussian, which gives varying realizations of values of $f(\mathbf{x})$ given $\mathbf{x}$; that is how it is a "distribution of functions".* 