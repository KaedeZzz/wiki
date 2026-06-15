---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Generation of Training Data.md
ingested: 2026-06-08
---

- From an initial deployment or available data, obtain $\mathbf{x}_{i}\sim p(\mathbf{x})$
- From outcomes *(or manually,)* obtain label $y_{i}\sim P(\omega|\mathbf{x}_{i})$
- Note that $(y_{i},\mathbf{x}_{i})$ are samples from joint distribution $p(\omega,\mathbf{x})$

This yields supervised training data
$$
\mathcal D=\{\{\mathbf{x_{1},y_{1}}\},\dots,\{\mathbf{x_{N},y_{N}}\}\}
$$

[[Generative Models]]