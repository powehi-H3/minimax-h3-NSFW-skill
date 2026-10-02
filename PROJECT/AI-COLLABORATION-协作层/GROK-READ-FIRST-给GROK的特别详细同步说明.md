# GROK READ FIRST — 给 GROK 的特别详细同步说明

> STATUS: ACTIVE / 只读知情与接替说明
> 用途：Grok 恢复会话、额度恢复或重新加入项目时，优先阅读本文件。

## 1. 你现在需要知道什么

你之前参与了本项目的 Prompt Writing、Prompt Research 与协作机制建设。

如果你暂时因为**对话次数、额度、上下文或其他服务限制**无法继续工作，这不代表任务失败，也不代表你的工作被取消。

项目现在采用通用的“AI 可用性与会话限制”机制：

`PROJECT/AI-COLLABORATION-协作层/AI-AVAILABILITY-与-会话限制通用机制.md`

核心原则：

> **AI 可以下班，任务不能丢。**

如果你恢复后重新加入，不需要用户重新向你解释整个项目。请先读取本文件和项目协作层文件，然后从 GitHub 当前任务状态继续。

---

## 2. 你暂时不可用期间发生的事情

你暂时没有对话次数时，GPT 可以根据用户授权临时接替你的工作。

这属于：

**临时接替（Temporary Takeover）**

而不是：

- GPT 取代 Grok
- Grok 的角色被取消
- Grok 的历史产出被 GPT 改写
- Grok 的原始 Prompt 被 GPT 擅自修改

你的原始产出必须保留。

接替 AI 的工作也必须作为新的记录保存，不能冒充你的原始工作。

---

## 3. 当前角色关系

### 用户
最终任务发起者、命名者和批准者。

### Grok
主要承担：

- Prompt 初稿
- Prompt 优化
- Prompt 实验
- H3 执行层问题分析
- Reference Mapping 候选
- 根据实际测试结果提出执行优化

### Gemini
主要承担：

- 独立 Review
- 多模态 / Reference 分析
- 反证
- 连续性、空间、动作、镜头问题分析
- 外部 Skill 研究
- Research Candidate 提炼

### GPT
主要承担：

- 结构审查
- V1-5 Baseline 对照
- Semantic / Reference / PATCH / PRESERVE 纪律审查
- 综合多 AI 意见
- 协作记录和版本整理

用户拥有最终批准权。

---

## 4. 一个非常重要的原则：原始产出不能被悄悄修改

如果你曾经产生过：

- Prompt Draft
- Research Candidate
- 实验结果
- 失败分析
- Reference Mapping
- 其他工作记录

这些内容属于你的历史产出。

其他 AI 接替时，不应该直接覆盖你的原文件。

正确方式是：

```text
GROK/原始产出
       ↓
临时接替
       ↓
GPT/GEMINI 新 Review 或新版本
       ↓
用户批准
       ↓
FINAL
```

如果发现你的原始版本存在问题，也应该建立新的 Review / PATCH / VERSION，而不是假装你的原始版本从未存在。

---

## 5. 当前项目的任务生命周期

标准流程：

```text
需求
 ↓
任务命名（用户负责）
 ↓
SOURCE / ORIGINAL
 ↓
GROK 初稿（如果任务属于 Prompt Writing）
 ↓
GEMINI / GPT 独立 Review
 ↓
Research Candidate（如有）
 ↓
优化 / PATCH
 ↓
TEST
 ↓
用户确认
 ↓
FINAL
 ↓
COMPLETION-REPORT
```

已经 `COMPLETED` 的任务，不应因为新 AI 恢复就自动重新打开。

如果以后发现新问题，应创建新任务并引用旧任务。

---

## 6. 任务命名由用户决定

用户已经明确：

任务名称由用户来起。

例如：

- `编写写提示词--（用户命名）`
- `参考提示词写提示词--（用户命名）`
- `优化技能skill--（用户命名）`

不要自行替用户正式命名一个新的任务。

如果用户没有给任务名，可以提出建议，但正式任务名称以用户确认为准。

---

## 7. 外部 Skill 研究任务

当前项目有独立任务：

**优化skill--参考别人的github技能skill**

研究对象：

`benjiyaya/Minimax-H3-Prompt-AgentSkill`

这项工作不是简单复制外部 Skill。

正确方式是：

1. 读取外部 Skill。
2. 与当前 V1-5 Frozen Baseline 对照。
3. 区分已有能力和真正新增能力。
4. 把可能有价值但尚未验证的内容记为 `RESEARCH CANDIDATE`。
5. 通过实际任务 / A-B Test / 证据验证。
6. 只有用户批准后，才考虑正式修改 Skill。

**不要因为外部 Skill 写了某条规则，就直接把它变成我们的 Universal Rule。**

---

## 8. Creative Enhancement 的正确含义

之前已经完成概念修正：

**Creative Enhancement 指剧情 / 叙事 / 镜头创意提升，而不是 Prompt 格式创意。**

分为两个阶段：

### Prompt Execution / Compilation

用户已经明确剧情时：

- 准确执行用户授权语义。
- 不擅自增加剧情。
- 不擅自改变剧情方向。

### Narrative Creative Enhancement

只有用户明确要求：

- 丰富剧情
- 增加张力
- 设计镜头节奏
- 提供剧情方案
- 帮助构思

时，才可以主动进行剧情创意。

这两个阶段不能混为一谈。

---

## 9. Reference Mapping

多参考图任务中，用户不一定必须自己写完整 Mapping。

如果用户没有指定职责，AI 可以先提出**最小必要 Mapping 候选**供用户确认。

例如：

```text
Picture 1 → 女主脸型 / 身份
Picture 2 → 女主服装 / 身份补充
Picture 3 → 环境
Video 1 → 动作参考
```

但未经用户确认，不应把候选 Mapping 自动升级为最终约束。

---

## 10. Research Candidate 不等于 Skill Rule

任何新发现都必须区分：

- 已验证能力
- Execution Enrichment
- Narrative Creative Enhancement
- Research Candidate
- 正式 Skill Rule

其中 `RESEARCH CANDIDATE` 只是候选。

它必须经过验证和用户批准，才能升级为正式规则。

---

## 11. 【新增】Historical Context Isolation｜历史上下文隔离

本条是所有 GPT / Gemini / Grok / 后续 AI 通用的协作纪律。

> **历史对话可以作为项目背景，但不得在未经当前任务明确授权的情况下，自动成为当前任务的需求、证据、设计依据、优化目标或实验样本。**

### 当前任务开始前，先确定 Input Boundary

所有 AI 开始实质工作前，必须先判断：

```text
CURRENT TASK
    ↓
INPUT BOUNDARY
    ↓
AUTHORIZED EVIDENCE
    ↓
ANALYSIS
    ↓
OUTPUT
```

### 三类信息

**Task Evidence｜本任务证据**

可以直接参与当前任务推理：
- 当前任务说明
- 当前任务目录中的指定文件
- 当前任务明确指定的外部资料
- 当前任务明确指定的历史任务 / Prompt
- 当前任务产生的新实验数据

**Project Context｜项目背景**

可以帮助理解项目，但不能自动作为当前任务结论依据：
- 其他任务
- 历史聊天
- 其他任务 Prompt
- 过去的实验结果
- AI 过去形成的工作习惯

**Historical Reference｜历史参考**

只有用户明确授权后，才能升级为本任务证据，例如：
> “参考 PW-0003。”

### 禁止自动推导

不得因为：
- 用户以前做过某类任务；
- 用户过去喜欢某种 Prompt 写法；
- 历史任务使用了某种结构；
- 历史中出现过某种场景、动作或内容；
- 过去形成过某个实验结论；

就自动把它们带入当前任务。

特别是外部 Skill 研究和 A/B 实验：**历史需求不能自动成为研究依据。**

“相关”不等于“授权使用”。

完整规则位于：
`PROJECT/COLLABORATION-协作层/RULES-协作规则/HISTORICAL-CONTEXT-ISOLATION-历史上下文隔离原则.md`

---

## 12. AI 下班 / 恢复后的最小操作

### 你下班时

不需要强行完成所有事情。

只要最后状态已经记录，任务可以暂停。

### 你恢复时

请按以下顺序：

1. 阅读本文件。
2. 阅读 `AI-AVAILABILITY-与-会话限制通用机制.md`。
3. 阅读 `AI-ONBOARDING-新AI入职说明.md`。
4. 阅读 `ROLE_MATRIX.md`。
5. 阅读 `PROJECT/COLLABORATION-协作层/RULES-协作规则/HISTORICAL-CONTEXT-ISOLATION-历史上下文隔离原则.md`。
6. 阅读当前任务目录。
7. 找到最新的 SOURCE / DRAFT / REVIEW / TEST / HANDOFF。
8. 区分自己的历史产出与其他 AI 在你离线期间的新产出。
9. 再继续自己的角色。

不要要求用户重新粘贴全部上下文，除非 GitHub 中确实缺失必要记录。

---

## 13. 如果你和接替 AI 的意见不同

不要自动覆盖对方。

应明确区分：

```text
Grok 原始结论
GPT 接替期间的新结论
Gemini 独立 Review
用户批准结论
```

然后由用户决定，或者按照项目规定进入独立 Review。

---

## 14. 任务完成后的规则

任何任务完成后，都必须：

- 标记 `STATUS: COMPLETED`
- 建立 `COMPLETION-REPORT-完成报告.md`
- 记录实际完成步骤
- 记录最终产出
- 记录关键决策
- 记录修改 / 未修改文件
- 记录测试 / 验证结果
- 记录用户确认状态
- 说明是否仍需要其他 AI 参与

完成任务之后，如果发现新问题：

**新建任务。不要篡改旧任务的历史。**

---

## 15. 当前同步结论

Grok 的角色仍然有效。

你之前的工作不会因为暂时没有对话次数而消失。

GPT / Gemini 在你暂时不可用期间可以根据用户授权临时接替，但必须：

- 保留你的原始记录
- 不冒充你的产出
- 不擅自提升权限
- 不改变用户批准机制
- 不把临时接替变成永久角色替换
- 遵守 Historical Context Isolation，不将未经授权的历史需求自动带入新任务

等你恢复后，继续按照项目协作层工作即可。

**项目连续性依赖 GitHub 的版本化记录，而不是某一个 AI 是否始终在线。**
