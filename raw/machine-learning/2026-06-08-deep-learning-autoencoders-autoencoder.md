---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Autoencoders/Autoencoder.md
ingested: 2026-06-08
---

[[Deep Learning]]
_Baseline for models like_ [[U-Net]]
Components:
1. Encoder
2. Bottleneck
3. Decoder

Data -> Encoder -> [[Latent Space]] -> Bottleneck -> Decoder -> Reconstructed data
![[Pasted image 20240912181309.png]]

How to train:
Goal: minimise difference between reconstructed data and original input 
1. maximise reconstruction ability from latent space
2. optimise encoder to keep the most useful features
Use a proper [[Loss Function]].

Why use such models?
Dimension reduction. -> encoding  in [[Latent Space]] (by how activated each neuron is)
![[Pasted image 20240912181541.png]]
Note that: LATENT SPACE QUALITY = RECONSTRUCTION QUALITY

Limitations: again, LATENT SPACE
1. Only using reconstruction quality as loss function does not necessarily generate nice latent space
2. Midpoint is pointless
3. Learned irrelevant features such that noisy input gets no good reconstruction
Solution: regulate latent space -> [[Variational Autoencoder]]

