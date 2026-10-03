# 2026-10-02｜GPT 日常协作对话同步

> 本文件属于 AI-COLLABORATION-协作层的日常对话同步区。
> **默认规则：所有有助于 GPT / Gemini / Grok 三方协作的日常对话信息，优先进入本区域。**
> 只有当用户明确要求任务记录、任务进度、实验记录或指定任务归档时，才进一步同步到对应任务目录。

## 一、三方协作归档总规则（最新）

### Daily-First / Task-Second

1. **先存日常协作对话。**
   - 目的：让 GPT、Gemini、Grok 能共享最新协作上下文、讨论结论、纠错、决策背景、工作状态和交接信息。
   - 普通协作对话不需要等待用户指定任务目录。
   - 只要内容对三方理解“我们最近讨论了什么、为什么这么决定、接下来怎么协作”有价值，就优先进入 DAILY-CONVERSATIONS。

2. **再按需求同步任务目录。**
   - 如果某段日常对话后来被确认属于某个任务的重要信息，再把相关内容摘要/结论同步到对应任务目录。
   - 任务目录用于任务自身的正式状态、设计、实验、证据、交付物和进度，不取代日常协作区。
   - 同一信息可以同时存在于 Daily 与 Task：Daily 保存协作上下文，Task 保存任务相关的结构化记录。

3. **用户没有明确要求时，不要擅自把普通聊天当成正式任务决策。**
   - 日常对话可以讨论、提出、质疑、建议和草拟。
   - 只有经过任务流程确认的内容，才进入任务正式状态/规则。

4. **三方 AI 的协作读取顺序：**
   - 先看 DAILY-CONVERSATIONS，恢复最近协作上下文；
   - 再看当前任务目录，获取任务正式状态和已确认资料；
   - 最后按需读取实验/参考/证据文件。

## 二、当前协作重点

### PW-OPT-001｜优化 Skill｜参考别人的 GitHub Skill

正式 V1-5 Baseline：**FROZEN**。

实验分组：

- A = 外部 Skill 全量参考版。
- B = GPT + Gemini 独立重构优化版。
- A/B 完全独立。
- B 不复制 A 的最终实现。
- A/B 均不直接修改正式 V1-5。
- 最终由 Grok 使用相同原始任务生成 Prompt A / Prompt B，再进行 H3 实测对比。

### Version B 当前状态

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

## 三、重要协作纪律

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

> **历史任务需求可以帮助理解项目背景，但不能未经授权成为新 Skill 规则的来源。**

## 四、当前行动

- B Version 架构记录已落盘。
- 下一阶段：在 B 实验目录实际落地 B Skill。
- 之后由 Grok 基于相同原始测试任务生成 Prompt A / Prompt B。
- H3 实测后再记录 Comparison / Evidence。

## 五、归档规则声明

本文件是“日常协作同步”，不是 PW-OPT-001 的正式任务进度文件。

### 以后默认执行

**普通/有价值的三方协作对话 → 先进入 DAILY-CONVERSATIONS。**

**明确属于某任务的重要内容 → 在 Daily 已归档的基础上，再同步到当前任务目录。**

**用户明确要求更新任务进度/任务记录/实验记录 → 必须写入对应任务文件。**

**不要求用户重复指定“存哪里”：默认 Daily-first。**
