---
summary: Karpathy 提出的自动化 ML 研究框架：LLM 智能体在固定 5 分钟预算内反复修改 train.py、跑实验、按 val_bpb 择优保留，模拟"过夜"自主研究循环。
tags: [machine-learning, ai-agents, autonomous-research, karpathy]
updated: 2026-07-06
sources:
  - raw/machine-learning/2026-07-06-karpathy-autoresearch.md
---

# autoresearch

## 定义

**autoresearch** 是 Andrej Karpathy 在 2026 年公开的一个开源框架（`github.com/karpathy/autoresearch`），用来演示 **AI 智能体自主进行机器学习研究** 的最小可行形式。人类只写一份 `program.md` 说明目标，LLM 智能体（如 Claude）就在单张 GPU 上反复：修改训练脚本 → 跑一次固定时长的训练 → 读评估指标 → 保留改进 / 回滚失败 → 循环。目标是让研究者一觉醒来就能收到一份"过夜实验日志"和一个可能更好的模型。

它不是一个新算法，而是一种 **研究协议**（research protocol）：把"做 ML 研究"这件事拆成一个 LLM 可执行的、有明确指标和时间约束的外循环。

## 关键点

### 三份文件的分工
- `prepare.py`：**只读**。负责数据准备、分词器、评估逻辑。冻结这一部分保证不同实验结果可比。
- `train.py`：**智能体唯一可改的文件**。含 GPT 模型定义、优化器、训练循环。
- `program.md`：人类写给智能体的"研究纲领"——目标、约束、评分规则。

### 固定时间预算 = 硬件无关比较
每次实验强制 **5 分钟训练时间**，而不是固定 step/epoch。这使不同 GPU 上跑出来的 `val_bpb` 数字可以直接横比：更强的硬件在 5 分钟内跑更多 step，本身就体现在最终分数里。

### 评估指标：val_bpb
**Validation bits per byte**，即在留出集上语言模型对每个字节需要多少比特描述——本质是交叉熵除以 log 2，再按字节归一化（关联 [[loss-function]]）。越低越好。用 bpb 而不是 perplexity 或 loss，是为了跨 tokenizer / 词表大小可比。

### 外循环协议
智能体在 `autoresearch/<tag>` 分支上：
1. 编辑 `train.py`（结构、超参、优化器、batch size 等）
2. `git commit`
3. `uv run train.py > run.log 2>&1`
4. `grep "^val_bpb:\|^peak_vram_mb:" run.log` 抽取结果
5. 追加到 `results.tsv`（commit hash、val_bpb、峰值显存、keep/discard/crash、简述）
6. 改进则保留，否则 `git reset` 回滚

约束：不引入新依赖；VRAM 是软约束；**不停下来等确认**，直到人类打断。

### 简洁性优先
`program.md` 明确要求："复杂度必须靠增益证明"——鼓励智能体先试简单改法。这与经典 ML 中的正则化 / [[early-stopping]] 精神一脉相承：奥卡姆剃刀被写进了研究协议本身。

## 为什么重要

autoresearch 是把 "AI 做研究" 从模糊愿景变成 **可复现工件** 的一次典型尝试：
- 它假设 **好的研究循环 = 明确指标 + 明确编辑面 + 明确时间约束 + 可回滚的 git 历史**。
- 它把"研究"降维成一个可评分的优化问题，让 LLM 的编辑能力和实验直觉可以直接被 `val_bpb` 度量。
- 它顺带示范了 [[llm-wiki-pattern]] 的另一个维度——不仅让 LLM 维护知识，还让 LLM 生产新知识（新架构、新超参组合）。

局限也明显：5 分钟单卡训练规模的"研究"离真正的 frontier 差距巨大；智能体优化的是 `val_bpb` 这一个标量，容易被局部技巧钻空子；`prepare.py` 被冻结意味着数据侧的创新被排除在外。

## 关联概念
- [[neural-network]] — 被优化的对象是一个小 GPT 语言模型
- [[optimisers]] — 智能体常见的改动之一是换优化器 / 调节学习率
- [[loss-function]] — `val_bpb` 本质是交叉熵在字节尺度上的归一化
- [[gradient-descent]] — 每次 5 分钟训练即一次 SGD 内循环
- [[early-stopping]] — 时间预算相当于强制的 early stopping
- [[regularisation]] — "简洁性优先"是把奥卡姆剃刀写进研究协议
- [[llm-wiki-pattern]] — 同属"让 LLM 承担智力劳动"的模式家族
