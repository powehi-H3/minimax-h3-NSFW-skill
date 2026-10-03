# 2026-10-02｜GPT 日常协作对话同步

> 本文件属于 AI-COLLABORATION-协作层的日常对话同步区。
> 除非用户明确指定“任务记录/任务对话/实验记录”，普通跨 AI 协作信息统一进入本区域；任务专属信息仍进入对应任务目录。

## 本次同步重点

### 1. 日常对话归档规则

用户明确确定：

- 普通日常协作对话默认归档到 AI-COLLABORATION-协作层的 DAILY-CONVERSATIONS-日常对话区域。
- GPT、Gemini、Grok 三方均可读取该区域，用于恢复协作上下文。
- 只有用户明确要求“需要任务记录”“更新任务进度”“归档到某任务”“实验结果”等情况，才将信息写入对应任务目录。
- 不应把普通闲聊、AI 可用次数、上下班状态、临时讨论等混入具体任务记录。
- 日常对话与任务记录必须保持分层，避免任务目录被无关聊天污染。

### 2. PW-OPT-001 当前协作状态

任务：PW-OPT-001｜优化 Skill｜参考别人的 GitHub Skill。

正式 V1-5 Baseline：FROZEN。

实验分组：

- A = 外部 Skill 全量参考版。
- B = GPT + Gemini 独立重构优化版。
- A/B 完全独立。
- B 不复制 A 的最终实现。
- A/B 均不直接修改正式 V1-5。
- 最终由 Grok 使用相同原始任务生成 Prompt A / Prompt B，再进行 H3 实测对比。

### 3. Version B 已完成设计审核

GPT 提出了 B-01 至 B-26 的独立工程强化清单；Gemini 已完成二次逻辑审核并形成 B Version Recommended Final Checklist。

审核后的 B 架构已经单独写入：

`PROJECT/SKILL_OPTIMIZATION-技能优化/EXPERIMENTS-技能优化对比实验/B-AI-RECOMMENDED-OPTIMIZATION-AI推荐优化版/B-VERSION-ARCHITECTURE-2026-10-02.md`

核心方向包括：

- Mode Detection
- Reference Role Mapping
- Reference Conflict Resolver
- Retention Analysis 2.0
- Temporal State Ledger
- One Dominant Action per Shot
- Action Vector + Minimum Sufficient Physical Description
- Camera Kinematics Decoupling
- Adaptive Spatial Geography
- Adaptive Prompt Density
- Creative Enhancement Gating
- Narrative Ideation / Compilation 解耦
- Environmental Reactivity 默认关闭
- Visual Texture Budget
- Camera / Subject / Environment 三层解耦
- PATCH Architecture + Minimal Semantic Change
- Shot-Level / Global Verification
- Debug Trace
- Evidence / Candidate Lifecycle
- A/B Experimental Isolation
- Mode-Specific Optimization
- Reference Asset Wiring Awareness
- Output Compiler Layer

### 4. 重要协作纪律

三方 AI 在任何 Skill 优化任务中，都必须区分：

- User Requirement
- Reference Material
- Existing Formal Skill Rule
- Research Candidate
- Experimental Rule
- AI Proposal
- User-Approved Rule

AI 不得因为历史对话中出现过某个偏好，就自动把它当成通用 Skill 规则。

特别是 Skill 研究任务：

> 历史任务需求可以帮助理解项目背景，但不能未经授权成为新 Skill 规则的来源。

### 5. 当前行动

- B Version 架构记录已落盘。
- 下一阶段：在 B 实验目录实际落地 B Skill。
- 之后由 Grok 基于相同原始测试任务生成 Prompt A / Prompt B。
- H3 实测后再记录 Comparison / Evidence。

## 归档规则声明

本文件是“日常协作同步”，不是 PW-OPT-001 的正式任务进度文件。

如果用户后续明确要求“更新 PW-OPT-001 任务进度”，应同步到该任务的 PROGRESS 文件；如果用户只说“同步给三方 AI / 让它们知道 / 把这段对话放进去”，默认写入本 DAILY-CONVERSATIONS 区域。
