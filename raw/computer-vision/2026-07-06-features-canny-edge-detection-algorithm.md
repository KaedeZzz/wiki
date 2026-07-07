---
source: KaedeSync/_Knowledge/Computer Vision/Features/Canny Edge Detection Algorithm.md
ingested: 2026-07-06
---

- Convolution with 2D Gaussian kernel:
$$
G_{\sigma}(x,y)=\frac{1}{2\pi\sigma ^{2}}\exp\left(- \frac{{x^{2}+y^{2}}}{2\sigma ^{2}}\right)
$$
$$
S(x,y)=G_{\sigma}(x,y)*I(x,y)=\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}G_{\sigma}(u,v)I(x-u,y-v)dudv
$$
- Then find the gradient of the smoothed image:
$$
\nabla S=\nabla(G_{\sigma}*I)=\nabla G_{\sigma}*I
$$
- Next step is non-maximal suppression: place edge elements where $\lvert \nabla S \rvert$ is greater than local values of $\lvert \nabla S \rvert$ in the direction of $\pm \nabla S$. This ensures all edge elements are located at *ridge points*. Afterwards, the edge elements are thresholded, so that only those with $\lvert \nabla S \rvert$ above a certain value are retained.

This process outputs a list of edge positions, each with a strength $\lvert \nabla S \rvert$ and an orientation $\nabla S / \lvert \nabla S \rvert$.

[[Image Features]]