---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Theories/Cross Entropy Loss.md
ingested: 2026-06-08
---

For classification tasks, the loss function is defined as the negative likelihood of correct classification.
 
![[Softmax Function]]

The [[Cross Entropy]] loss is thus the negative log likelihood:
$$
L(\mathbf{y},\hat{y}=k)=-\log(p(y_{n}=k|\mathbf{w}_{1},\dots,\mathbf{w}_{k},\tilde{\mathbf{x}}))=\log\left( \sum_{k'=1}^{K}\exp(\mathbf{w}_{k'}^{T}\tilde{\mathbf{x}})\right)-\mathbf{w}_{k}^{T}\tilde{\mathbf{x}}
$$
[[Machine Learning]]