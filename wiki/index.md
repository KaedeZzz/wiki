# Wiki Index

> 最后更新：2026-07-06 ｜ 概念页 85 篇 ｜ 来源 5 条（510 个原始文件）

## meta

- [[llm-wiki-pattern]] — 用 LLM 增量构建和维护个人知识库的模式
- [[rag-vs-wiki]] — RAG 与 LLM Wiki 模式的核心区别
- [[three-layer-architecture]] — raw sources / wiki / schema 三层结构
- [[wiki-operations]] — Ingest / Query / Lint 三个核心操作
- [[memex]] — Vannevar Bush 1945 年提出的个人知识存储愿景

## control-theory

### 基础

- [[transfer-function]] — 传递函数、极点/零点、闭环 H=KG/(1+KG)
- [[laplace-transform]] — Laplace 变换：s 域连续系统分析
- [[z-transform-discrete-systems]] — z 域极点与单位圆稳定域

### 稳定性

- [[stability]] — BIBO、s 平面/单位圆判据、三条等价条件
- [[nyquist-stability]] — 用开环频率响应判定闭环稳定性
- [[frequency-response]] — Bode 图、增益/相位裕度

### 控制器与状态估计

- [[pid-controller]] — 比例-积分-微分与 Ziegler-Nichols 调参
- [[state-space-model]] — ẋ=Ax+Bu、Φ(t)=e^{At}
- [[kalman-filter]] — 线性高斯状态估计、Kalman 增益、EKF、预测误差分解

## information-theory

### 熵与信息量度

- [[information-entropy]] — 信息熵 H(X)、二元熵、Perplexity、基本性质
- [[joint-conditional-entropy]] — 联合/条件熵、链式法则、独立性刻画
- [[mutual-information]] — 互信息、数据处理不等式、Fano 不等式
- [[kl-divergence]] — KL 散度、Gibbs、交叉熵、Softmax
- [[differential-entropy]] — 连续版本、高斯的微分熵、最大熵定理

### 渐近典型性

- [[typicality-and-aep]] — AEP、典型集、弱/强典型、联合 AEP

### 信道

- [[channel-capacity]] — C=max I(X;Y)、BSC、Shannon-Hartley

### 编码

- [[source-coding]] — Kraft、Shannon-Fano、Huffman、算术编码、冗余=KL
- [[channel-coding]] — 编码定理、可达性/逆定理、线性块码、Hamming
- [[ldpc-codes]] — 稀疏校验矩阵、消息传递、密度演化

### 学习理论

- [[pac-bayes-bound]] — 用 KL 控制泛化误差

## machine-learning

### 基础

- [[supervised-and-unsupervised-learning]] — 监督/无监督/强化学习三大范式
- [[loss-function]] — 损失函数：实际损失、经验损失、交叉熵、最小二乘、MSE
- [[gradient-descent]] — 梯度下降、SGD、动量
- [[optimisers]] — 归一化梯度下降、Nesterov、ADAM
- [[regularisation]] — 正则化与 L2 正则化
- [[roc-curve]] — ROC 曲线与 AUC 评估指标

### 概率模型

- [[graphical-model]] — 图模型：贝叶斯网络与马尔可夫网络
- [[gaussian-mixture-model]] — 高斯混合模型及其 EM 求解
- [[expectation-maximisation]] — EM 算法：E-step / M-step / 辅助函数
- [[evidence-lower-bound]] — ELBO（证据下界 / 自由能）
- [[factor-analysis]] — 因子分析：线性隐变量生成模型
- [[gaussian-process]] — 高斯过程：函数空间上的分布、后验过程、Matérn 协方差
- [[hidden-markov-model]] — HMM：前向算法、Viterbi 近似
- [[clustering]] — 聚类、K-means、Soft K-means

### 深度学习

- [[neural-network]] — 神经网络：ReLU、层归一化、不变变换
- [[cnn]] — 卷积神经网络：池化、步幅、膨胀卷积
- [[residual-network]] — 残差网络（ResNet）
- [[dropout]] — Dropout 正则化
- [[early-stopping]] — 提前停止
- [[ensemble]] — 集成学习

### 生成模型与降维

- [[autoencoder]] — 自编码器与潜空间
- [[variational-autoencoder]] — VAE：ELBO 损失、重参数化技巧
- [[pca]] — 主成分分析
- [[t-sne]] — t-SNE 非线性降维
- [[umap]] — UMAP 基于图的非线性降维

### 物理信息 ML

- [[pinn]] — 物理信息神经网络
- [[sindy]] — SINDy：从数据发现稀疏动力学方程

### 其他

- [[logsumexp]] — LogSumExp 数值稳定技巧
- [[zipfs-law]] — Zipf 定律：词频与排名的反比关系

## mathematics

### 代数

- [[algebraic-structures]] — 半群→幺半群→群→阿贝尔群→环→域的代数结构层次
- [[number-theory]] — GCD、欧几里得算法、欧拉定理、素数、模运算

### 分析

- [[convexity]] — 凸/凹函数、Jensen 不等式、对数凹分布、强凸性
- [[functional-spaces]] — 度量空间→赋范空间→Banach→内积空间→Hilbert 的层次
- [[convergence]] — 逐点收敛、一致收敛、limsup/liminf
- [[concentration-inequalities]] — Markov、Chebyshev、Chernoff 不等式

### 微积分

- [[calculus]] — Riemann 积分、Jacobian 矩阵、梯度/散度/旋度

### 微分方程

- [[partial-differential-equations]] — 波动方程、热传导方程、Burger 方程

### 图论

- [[graph-fundamentals]] — 图定义、邻接矩阵、度、连通分量、图类型
- [[centrality-measures]] — 度/特征向量/介数/接近中心性、PageRank、Katz
- [[graph-properties]] — 聚类系数、模块度、同配性、社区检测
- [[random-graphs]] — Erdős-Rényi 模型、配置模型、无标度网络

### 线性代数

- [[vector-norms]] — $L^p$ 范数、算子范数、Frobenius 范数
- [[eigendecomposition]] — 特征分解、谱定理、PSD、Perron-Frobenius
- [[matrix-decomposition]] — SVD、Woodbury 恒等式、条件数
- [[fundamental-subspaces]] — 四个基本子空间、秩-零度定理

### 测度论

- [[measure-and-integration]] — 测度、Lebesgue 积分、概率测度、Gaussian 测度、Wasserstein 距离

### 特殊函数

- [[special-functions]] — Stirling 近似、Gamma 函数、Beta 函数

### 概率论基础

- [[probability-foundations]] — 概率空间、Kolmogorov 公理、随机变量、PDF/PMF
- [[random-vectors]] — 联合分布、边缘分布、变量变换、随机变量之和
- [[expectation-and-moments]] — 期望、方差、协方差、Tower rule
- [[discrete-distributions]] — Bernoulli、二项、几何、Poisson、多项分布
- [[continuous-distributions]] — 指数、Beta、Dirichlet、Rayleigh 分布
- [[gaussian-distribution]] — 高斯分布：一维/多维、条件化、采样、最大熵
- [[generating-functions]] — PGF、MGF、特征函数及其应用
- [[limit-theorems]] — 中心极限定理、弱大数定律

### 贝叶斯推断与估计

- [[posterior-distribution]] — 后验分布：先验 × 似然 → 后验
- [[estimation-theory]] — MLE、MAP、MMSE、无偏/一致估计量
- [[linear-gaussian-model]] — 广义线性模型、OLS、贝叶斯线性回归
- [[monte-carlo-methods]] — MC 积分、重要性采样、MCMC、Metropolis-Hastings、Gibbs

### 随机过程

- [[random-processes]] — 随机过程定义、平稳性、遍历性、白噪声、功率谱
- [[markov-chain]] — Markov 性质、转移矩阵、不可约、非周期、平稳分布
- [[time-series-analysis]] — 时间序列分解、AR/MA/ARMA 模型、频谱分析

### 概率图模型

- [[factor-graph]] — 因子图与置信传播（消息传递）算法

### 统计力学

- [[statistical-mechanics]] — Ising 模型、Boltzmann 分布、能量函数与贝叶斯对应
