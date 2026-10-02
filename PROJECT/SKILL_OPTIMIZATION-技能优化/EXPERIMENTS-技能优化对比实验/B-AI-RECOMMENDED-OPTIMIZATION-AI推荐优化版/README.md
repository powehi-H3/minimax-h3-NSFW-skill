# B — AI RECOMMENDED OPTIMIZATION / AI 推荐优化版

## 定位

独立实验版本。

目标是：由 GPT + Gemini 基于外部 Skill 研究、V1-5 现况和工程分析，**独立设计一套推荐优化方案**。

## 与正式 Skill 的关系

完全隔离。

不得：
- 覆盖正式 V1-5；
- 修改正式 SKILL.md；
- 将实验结论自动升级为正式规则；
- 把 Experiment A 的最终版本直接复制为 B。

## 方法

允许参考：
- 外部 Skill 的研究结果；
- Gemini 的独立分析；
- GPT 的工程分析；
- 已有 Research Candidates。

但最终形成的是一套独立的 AI 推荐方案，而不是外部 Skill 的全量移植。

需要明确记录：
- 为什么保留某机制；
- 为什么删除某机制；
- 为什么重构某机制；
- 哪些内容仍属于实验假设。

## 后续

完成后交给 Grok。

Grok 使用该实验版本独立生成 Prompt，标记为：

`PROMPT-EXPERIMENT-B`

再与 Experiment A 的 Prompt 对比。
