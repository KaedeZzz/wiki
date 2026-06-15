---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Time Series Analysis/Basics/Time Series.md"
ingested: 2026-06-09
---

[[Time Series Analysis]]

A time series is a set of observations $y_{n}, n=0,1,\dots$ arranged in increasing time $t_{0}+n\Delta$.
Workflow for time series analysis:
1. Set up probability model. use $$Y_{n}=\text{trend }+\text{ seasonal component }+\text{ residual}$$
   $m_{n}$ trend: evolution of mean over time
   $S_{n}$ seasonal: sinusoid(s) with periodicity related to calendar
   $X_{n}$ residual: zero-mean random vector
2. Estimate parameters, check goodness of fit
3. Deploy

###### Estimating the Trend
$$
\nabla _{\hat{m_{i}}}\sum_{n=0}^N(Y_{n}-\hat{m_{n}})=0
$$
Minimised over [[Minimum Mean Squared Error Estimation]]
de-trended data: $Y_{n}-\hat{m_{n}}$
fitting a wrong trend will result in **bias**: see [[Unbiased Estimator]].
###### Estimating Seasonal Component
$$
S_{n}=\alpha_{1}\cos(2\pi fn)+\alpha_{2}\sin(2\pi fn)\text{ where }\alpha_{1}=A\cos \phi\text{ and }\alpha_{2}=-A\sin \phi
$$
Solving:
$$
\left( \frac{\partial}{\partial \alpha_{1}}, \frac{\partial}{\partial \alpha_{2}} \right)\sum_{n=0}^N(Y_{n}-\hat{m_{n}}-\alpha_{1}\cos(2\pi fn)-\alpha_{2}\sin(2\pi fn))=0
$$
Residual: $Y_{n}-\hat{m_{n}}-\hat{S_{n}}$

