---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Generation Function.md"
ingested: 2026-06-09
---

[[Probability and Statistics]]
Probability Generation Function for a discrete random variable:

$$ G_X(z)=\sum_{k\in\mathbb X}z^kP_X(k)=\mathbb E[z^X] $$
For a continuous random variable:
$$
G_{X}(z)=\int_{-\infty}^{\infty}f(x)z^{x}dx=\mathbb{E}\{z^{X}\}
$$
For multivariate:
$$
G_{\mathbf{X}}(\mathbf{z})=\mathbb{E}\left\{ \prod_{i}z_{i}^{X_{i}} \right\}
$$

[[Moments]]:
$\mathbb E[X]=G'_X(1)$
$\text{Var}[X]=G_X''(1)+G'_X(1)-G'_X(1)^2$

Multivariable:
$G_{\sum_{i=1}^nx_i}(z)=\Pi_{i=1}^nG_{X_i}(z)$

Addition of variables:
$G_{X+Y}(z)=G_{X}(z)G_{Y}(z)$

Constant scaling of random variables:
$G_{aX}(z)=\mathbb{E}\{z^{aX}\}=G_{X}(z^{a})$

for discrete $X$:
$$
G_{X}^{(k)}(0)=k!p(k)
$$

Using this expression, we find:
$X\sim B(n_X,p),Y\sim B(n_Y,p)\Rightarrow X+Y=B(n_X+n_Y,p)$
$X\sim\text{Pois}(\lambda_X),Y\sim\text{Pois}(\lambda_Y)\Rightarrow X+Y\sim\text{Pois}(\lambda_X+\lambda_Y)$


Moment Generating Function
For a **continuous** random variable:

$$ g_X(s)=\int_{-\infty}^{+\infty}f_X(x)e^{sx}dx=\mathbb E[e^{sX}] $$

Moments:
$\mathbb E[X]=g'_X(0)$
$\text{Var}[X]=g_X''(0)-g'_X(0)^2$

Sum of independent variables:
$g_{\sum_{i=1}^nx_i}(s)=\Pi_{i=1}^ng_{X_i}(s)$

Using this expression, we find:
$X\sim\mathcal N(\mu_X,\sigma_X^2),Y\sim\mathcal N(\mu_Y,\sigma_Y^2)\Rightarrow X+Y\sim\mathcal N(\mu_X+\mu_Y,\sigma_X^2+\sigma_Y^2)$

