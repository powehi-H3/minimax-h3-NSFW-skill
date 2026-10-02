# EXPERIMENTS-技能优化对比实验

> STATUS: ACTIVE / 独立实验区

## 目的

本目录专门用于比较两条独立的 Skill 优化路线，并最终让 Grok 分别基于两套实验版本生成 Prompt，用真实任务进行对比。

**本目录不直接修改或覆盖正式 V1-5 Skill。**

正式 Skill 与本实验区完全隔离。

## 实验路线

### A — 外部 Skill 全量参考版

目标：尽可能完整地按照外部参考 Skill `benjiyaya/Minimax-H3-Prompt-AgentSkill` 的设计思路，对我们的 Skill 做一次独立优化实验。

原则：
- 不以 V1-5 正式 Skill 的优化结果反向约束本实验版本。
- 不把实验结果自动写回正式 Skill。
- 保留外部 Skill 的原始设计逻辑，便于观察其整体效果。

### B — AI 推荐优化版

目标：由 GPT + Gemini 根据外部 Skill 分析、V1-5 现况和工程判断，独立设计另一套优化版本。

原则：
- 不复制 A 版的最终优化结果。
- 可以参考同一外部 Skill，但由 AI 自己筛选、重构和组织。
- 同样不写回正式 Skill。

## 对比方法

完成 A / B 两个实验 Skill 后：

1. 由 Grok 分别读取 A 版和 B 版。
2. 使用相同任务需求。
3. 分别生成 Prompt A 与 Prompt B。
4. 尽可能保持相同参考素材、参数和测试条件。
5. 对比输出质量与 H3 实际表现。
6. 记录差异和失败原因。
7. 最终由用户决定是否将任何结果升级到正式 Skill。

## 重要纪律

`EXPERIMENTS-技能优化对比实验` 的任何文件都不是正式 Skill。

实验结果不能自动成为 Universal Rule。

实验版本不能覆盖：
- V1-5 Baseline
- 正式 SKILL.md
- 正式 references
- 已完成任务历史

## Grok 的职责

Grok 不参与这两个 Skill 实验版本的设计决策，只负责在两套版本准备完成后：

- 分别读取 A / B 实验 Skill；
- 使用同一真实任务；
- 各自生成一份 Prompt；
- 明确标注使用的是 Experiment A 还是 Experiment B；
- 不混用两套实验规则。

## 当前状态

- A 外部 Skill 全量参考版：待建立
- B AI 推荐优化版：待建立
- Grok 对比 Prompt：待执行
- H3 实测：待执行
- 最终结论：待用户确认
