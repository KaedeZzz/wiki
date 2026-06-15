---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Estimation Basics.md"
ingested: 2026-06-09
---

[[Estimation and Inference]]
Suppose that the PDF of a random variable $X$ is a function $f_X(x;\theta)$ that depends on a parameter $\theta$.
If $\theta$ adopt a **continuous** set of values, we “estimate” its value;
If $\theta$ adopt a **discrete** set of values, we “decide” its value.

Define:
Observation: $x=[x_1,\dots,x_n]^T$
Sample: $X=[X_1,\dots,X_n]^T$
Usually, these are independent and identically distributed.

The estimate (or decision) for $\theta$ is a function of the observations, $\hat\theta(x)$.
The estimator (or decision rule) is the corresponding random variable, $\hat\Theta=\hat\theta(X)$.
In Bayesian statistics ([[Bayes Theorem]]), the unknown parameter $\theta$ is viewed as the value of random variable $\Theta$.

We define:
The prior function $f_\Theta(\theta)$
The likelihood function $f_{X|\Theta}(x|\theta)$
The posterior function $f_{\Theta|X}(\theta|x)$

