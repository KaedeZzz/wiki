---
summary: 群体决策的理想（多信息、多视角、更被接受）常被现实机制（Groupthink、Social Loafing、conformity）侵蚀。个体决策的理性过程六步在 Bounded Rationality 下多退化到 satisficing——凭经验生成有限方案、选择"够用"的方案。
tags: [human-and-society, decision-making, groups]
updated: 2026-07-08
sources:
  - raw/human-and-society/2026-07-08-business-organisational-behaviour-group-people.md
  - raw/human-and-society/2026-07-08-business-organisational-behaviour-groupthink.md
  - raw/human-and-society/2026-07-08-business-organisational-behaviour-decisions-decisions.md
  - raw/human-and-society/2026-07-08-business-organisational-behaviour-decisions-decision-making.md
  - raw/human-and-society/2026-07-08-social-sciences-concepts-rational-process.md
  - raw/human-and-society/2026-07-08-social-sciences-concepts-bounded-rationality.md
---

# 群体与决策

## 定义

**群体（Group）**：两个或以上人员**相互依赖**地互动以达成共同目标。分两类：

- **正式群体（Formal）**：组织为达成目标而建立
- **非正式群体（Informal）**：因共同兴趣自发形成

**决策（Decision）**：从两个或以上备选中做选择。

## 关键点

### 关于群体的三条乐观假设（及其现实修正）

| 假设 | 内容 | 现实 |
|---|---|---|
| Synergy | 群体表现 > 个体之和 | 常被 Social Loafing 侵蚀 |
| Effectiveness | 群体更能达成组织目标 | 视任务复杂度而定 |
| Efficiency | 群体更高效 | 决策速度慢，协调成本高 |

### 群体决策：优 vs 劣

**优势**：

- 信息与知识更完整
- 视角多样性提高
- 更好方案被更好接受
- 责任扩散（也可以是缺点，见 Social Loafing）

**劣势**：

- 慢
- **conformity pressure**：从众压力
- **Social Loafing**：群体任务中的懈怠
- **Groupthink**：极端形式

### Groupthink（群体思维）

*群体从众压力使成员不去批判性评估少数派/异见/不合群意见*。

**为什么会顺从**：

- 不想当"刺头"（心理成本）
- 个人主义文化里从众少

**解药**：

- **异见必须被制度化珍视**（e.g. 设"魔鬼律师"角色）
- 成员必须**心理安全**地讲话（Amy Edmondson 的经典发现）

**Groupthink 的历史案例**：猪湾入侵、挑战者号发射决策——一群聪明人共同做出灾难性错误决策的经典情境。

### 理性决策六步（理论上）

1. **定义问题**
2. **识别决策标准**
3. **给标准分配权重**
4. **发展备选方案**
5. **评估备选方案**
6. **选择最优方案**

**为什么现实中难以做到**：

- **认知能力有限**
- **信息可获得性有限**

### Bounded Rationality（有限理性）— Herbert Simon

Simon 因此获得诺贝尔经济学奖。核心洞察：

1. **认知能力有限** → 决策时只考虑**有限**信息
2. 备选方案**从经验生成**，而非通过收集分析外部信息
3. 选择**满意且足够（satisficing）**的方案——不是最优，而是"够好"

**Satisficing = satisfy + suffice**：找到跨过阈值就停，而不是穷尽搜索。

**含义**：

- 组织决策通常远非"最优"
- 好的**默认选项设计**和**决策流程**（checklist、pre-mortem）比"更聪明的决策者"更能改善结果
- 在机器学习里的对应：贪婪算法与 anytime algorithms

### 与 [[perception-and-bias]] 的联系

Bounded Rationality 是**结构性**（能力和信息约束）；**认知偏差**是**系统性偏离理性的模式**（锚定、可得性、确认等）。两者叠加：**"能力有限 + 有偏"** 决定了真实决策的形状。

### 群体决策的双刃

群体决策既可以是**Bounded Rationality 的缓解**（更多信息、更多视角）又可能**放大偏差**（groupthink 让多个人的偏差同步而不是抵消）。**正确设计的群体决策流程** ≠ 简单让一群人在一个房间开会。

## 关联概念

- [[motivation-theories]] — Social Loafing 是激励失败的群体形式
- [[perception-and-bias]] — 决策偏差与感知偏差重叠
- [[organisational-behaviour-overview]] — 三大流派对"个人 vs 群体"角色看法迥异
- [[organisational-culture]] — 文化决定 conformity 与异见容忍度
- [[hypothesis-testing]] — 决策理论的定量对应（假设检验 = 二元决策）
- [[posterior-distribution]] — 理性决策的贝叶斯化身
- [[monte-carlo-methods]] — 群体也是一种"多智能体"采样
