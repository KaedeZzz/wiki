---
summary: Vault 中 _Resources/Research Papers 下的 8 篇论文（原笔记多为占位）——机器学习与数据驱动动力学的经典/近期工作，按主题分为动力学谱分析、深度 Koopman、PINN、变分自编码、UMAP 五族。
tags: [research-papers, reading-list]
updated: 2026-07-06
sources:
  - raw/research-papers/2026-07-06-auto-encoding-variational-bayes-kingma-et-al.-2022.md
  - raw/research-papers/2026-07-06-umap-uniform-manifold-approximation-and-projection-for-dimension-reduction-mcinnes-et-al.-2020.md
  - raw/research-papers/2026-07-06-dynamic-mode-decomposition-of-numerical-and-experimental-data-p.schmid-2010.md
  - raw/research-papers/2026-07-06-spectral-analysis-of-nonlinear-flows-c.-rowley-et-al.-2009.md
  - raw/research-papers/2026-07-06-deep-learning-for-universal-linear-embeddings-of-nonlinear-dynamics-b.-lusch-et-al.-2018.md
  - raw/research-papers/2026-07-06-deep-learning-models-for-global-coordinate-transformations-that-linearise-pdes-gin-et-al.-2020.md
  - raw/research-papers/2026-07-06-solving-the-wave-equation-with-physics-informed-model-moseley-et-al.-2020.md
  - raw/research-papers/2026-07-06-deep-learning-for-fast-simulation-of-seismic-waves-in-complex-media-moseley-et-al.-2020.md
---

# 论文阅读单

## 定义

Vault `_Resources/Research Papers/` 下用户标记的 8 篇论文。**原笔记均为占位**（多为引用、arxiv 链接或 "TBC"），因此本页由我从通识知识整理每篇的一句话摘要 + 到 wiki 中相应概念页的链接。用户后续补充笔记时可以拆分成独立概念页。

## 关键点

### 变分自编码

- **Kingma & Welling (2013/2022 arXiv v)**, *"Auto-Encoding Variational Bayes"*, [arXiv:1312.6114](https://arxiv.org/abs/1312.6114)
  - 提出 VAE：用**变分下界**（ELBO）+ **重参数化技巧**训练神经网络作为随机编码器/解码器；后验 $q_\phi(z|x)$ 与生成 $p_\theta(x|z)$ 联合优化，KL 项作正则。
  - 见 [[variational-autoencoder]]、[[evidence-lower-bound]]、[[kl-divergence]]。

### 非线性降维

- **McInnes, Healy, Melville (2018/2020)**, *"UMAP: Uniform Manifold Approximation and Projection for Dimension Reduction"*, [arXiv:1802.03426](https://arxiv.org/abs/1802.03426)
  - 基于图/黎曼几何构造保持**局部拓扑**的低维嵌入；比 t-SNE 快且更好保留全局结构，事实标准的可视化工具。
  - 见 [[umap]]、[[t-sne]]。

### 数据驱动动力学：DMD 与 Koopman

- **Schmid (2010)**, *"Dynamic Mode Decomposition of Numerical and Experimental Data"*, J. Fluid Mech.
  - 提出 DMD：从时序快照矩阵 $\{x_k\}$ 拟合线性算子 $A$ 使 $x_{k+1}\approx A x_k$，其特征分解给出**时空相干模态** + 各自的复频率。流体/降阶建模的核心工具。
  - Physics topic 中的 [[dynamical-systems-and-koopman]] 覆盖此概念。

- **Rowley, Mezić, Bagheri, Schlatter, Henningson (2009)**, *"Spectral Analysis of Nonlinear Flows"*, J. Fluid Mech.
  - 从 **Koopman 算子**视角把 DMD 严格化：Koopman 是无限维**线性**算子作用于可观测函数空间，其谱把非线性动力系统"线性化"。DMD 是 Koopman 谱的有限维数据驱动近似。
  - 见 [[dynamical-systems-and-koopman]]。

### 深度 Koopman 嵌入

- **Lusch, Kutz, Brunton (2018)**, *"Deep Learning for Universal Linear Embeddings of Nonlinear Dynamics"*, Nat. Comm.
  - 用 autoencoder 学习一组坐标 $\varphi(x)$ 使得动力学在该坐标下**线性演化**；辅助网络处理连续谱。把 Koopman 谱学习端到端化。
  - 见 [[dynamical-systems-and-koopman]]、[[autoencoder]]、[[sindy]]。

- **Gin, Lusch, Brunton, Kutz (2020)**, *"Deep Learning Models for Global Coordinate Transformations that Linearise PDEs"*, Eur. J. Appl. Math.
  - 把 Lusch 2018 的思想推广到 **PDE**：学习空间坐标变换使得 PDE 演化变线性。含 Burgers、KdV 等实例。
  - 见 [[partial-differential-equations]]、[[dynamical-systems-and-koopman]]。

### 物理信息深度学习

- **Moseley, Nissen-Meyer, Markham (2020)**, *"Solving the wave equation with physics-informed model"*
  - PINN 应用于波动方程：网络 $u_\theta(x,t)$ 直接最小化 $\|\square u_\theta\|^2 +$ BC/IC 残差。
  - 见 [[pinn]]、[[partial-differential-equations]]。

- **Moseley, Markham, Nissen-Meyer (2020)**, *"Deep Learning for Fast Simulation of Seismic Waves in Complex Media"*
  - 训练 CNN 快速逼近全波场仿真结果——不是 PINN，是**监督式代理模型**，训练数据来自数值求解器。工程动机：地震反演里的正问题昂贵，用 DL 加速。
  - 见 [[cnn]]、[[pinn]]（对比路径）。

## 关联概念

- [[variational-autoencoder]] — Kingma 2013 直接落地为该页
- [[umap]] — McInnes 2018 直接落地
- [[pinn]] — Moseley 波动方程论文的基础
- [[sindy]] — Koopman 系另一实用工具（数据驱动稀疏动力学）
- [[autoencoder]] — Lusch 深度 Koopman 的架构基础
- [[partial-differential-equations]] — Gin 与 Moseley 的应用对象
