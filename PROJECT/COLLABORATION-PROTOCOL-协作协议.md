# COLLABORATION-PROTOCOL — 四方协作协议

## 1. 核心原则

本项目采用多 AI 独立协作模式。

**SOURCE → REVIEW → CANDIDATE → DRAFT → TEST → FINAL** 是 Prompt 任务的基本生命周期。

任何阶段都必须保留来源和版本关系，不允许用新版本覆盖旧 SOURCE。

## 2. SOURCE 原稿纪律

SOURCE / ORIGINAL 是项目原始证据。

SOURCE 不得被：

- 净化
- 改写
- 润色成另一个版本
- 删除关键内容后冒充原稿
- 被 Review 直接覆盖

如果需要修改，必须创建新版本。

例如：

`SOURCE → DRAFT-V2 → DRAFT-V3 → FINAL`

## 3. Review 旁路原则

GPT、Grok、Gemini 的 Review 都是独立意见。

Review 不直接改变 SOURCE。

推荐结构：

```text
SOURCE/
REVIEWS/
  GPT-REVIEW.md
  GEMINI-REVIEW.md
  GROK-REVIEW.md
CANDIDATES/
DRAFTS/
TEST/
FINAL/
```

## 4. 角色分工

### 用户

- 提出任务
- 指定任务名称
- 提供/确认素材职责
- 批准采用哪些修改
- 批准 Prompt 正式收录
- 批准 Skill / 项目规则修改

### Grok — Prompt Executor

重点负责：

- Prompt 初稿
- Prompt 优化
- 实验
- 测试
- Execution-level 问题分析
- Reference Mapping 候选

### Gemini — Independent Reviewer

重点负责：

- 独立审查
- 多模态/Reference 分析
- 反证
- 连续性、空间、动作、镜头执行问题分析
- 外部 Skill 研究
- Research Candidate 提炼

### GPT — Coordinator / H3 Reviewer

重点负责：

- H3 结构审查
- V1-5 Baseline 对照
- Semantic / Reference / PATCH / PRESERVE 纪律审查
- 综合 Grok 与 Gemini 的意见
- 版本与研究结论整理
- 协助用户做最终判断

GPT 不得把自己的审查意见伪装成其他 AI 的原稿。

## 5. Creative Enhancement

Creative Enhancement 指：

**剧情 / 叙事 / 镜头创意提升。**

它不是 Prompt 格式创意，也不是默认强制规则。

### 已明确剧情

严格执行用户授权语义，不擅自改剧情。

### 用户明确要求创意

例如：

- 丰富剧情
- 增加张力
- 设计镜头节奏
- 提供剧情方案

此时可以进入 Narrative Creative Enhancement 阶段。

## 6. Research Candidate

发现新方法时，不立即修改 Skill。

先记录为：

`RESEARCH CANDIDATE`

并记录：

- 来源
- 方法
- 为什么可能有效
- 当前证据
- 是否需要 A/B Test
- 与 V1-5 的潜在冲突

## 7. Skill 修改

V1-5 当前 Frozen。

只有在出现：

- 同类问题反复出现
- 当前 Skill 明确无法覆盖
- 有实际测试或研究证据

时，才提出最小修改候选。

任何正式 Skill 修改都必须经过用户批准。

## 8. GitHub 写入

AI 不得因为“自己认为应该这样”而自行修改项目核心规则。

涉及：

- SKILL.md
- STATUS.md
- DECISIONS.md
- CHECKPOINT.md
- ROLE_MATRIX.md
- 项目协作协议

应先提出修改内容和原因，并等待用户明确批准。

## 9. 版本追溯

任何正式版本都应能够回答：

- 谁提出？
- 基于哪个 SOURCE？
- 谁审查？
- 采用了哪些意见？
- 谁批准？
- 测试结果是什么？
- 为什么进入 FINAL？
