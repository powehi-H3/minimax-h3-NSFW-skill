# 任务名称：协作层建立与同步说明

> 状态：COMPLETED / 已完成
> 性质：项目协作层设计与同步
> 注意：本任务不是 H3 Prompt 编写任务，也不是 Skill 优化任务。
> 不需要 Grok / Gemini 参与修改；它们只需要知道协作层已经建立以及以后如何读取。

---

## 用户原始需求

用户指出：之前建立的协作机制涉及另一个任务，而那个任务已经敲定完成优化，不需要 Grok 和 Gemini 参与新的修改；只需要让它们知道协作层的存在、作用以及自己的角色。

用户要求：

1. 将这一部分单独作为一个任务分类。
2. 任务名称由 GPT 命名。
3. 将我们关于这部分的对话完整保存到 GitHub。
4. 该任务完成后不再要求 Grok / Gemini 参与修改，只需同步知情。

---

## GPT 提出的分类

GPT 将这一部分定义为：

**协作层建立与同步说明**

它属于 PROJECT 协作基础设施，而不是：

- PROMPT_WRITING-提示词编写
- SKILL_OPTIMIZATION-技能优化
- 某一个具体 Prompt 任务

因此单独建立目录：

`PROJECT/AI-COLLABORATION-协作层/`

本任务位于：

`PROJECT/AI-COLLABORATION-协作层/COMPLETED-协作层建立与同步说明/`

---

## 已建立的协作层文件

此前已在项目中建立：

```text
PROJECT/
├── AI-ONBOARDING-新AI入职说明.md
├── PROJECT-README.md
├── COLLABORATION-PROTOCOL-协作协议.md
├── ROLE_MATRIX.md
└── WORKFLOW-工作流.md
```

这些文件属于项目协作层，不属于 V1-5 H3 Prompt Skill。

---

## AI-ONBOARDING 的目的

以后任何新的 AI 加入项目，第一入口是：

`PROJECT/AI-ONBOARDING-新AI入职说明.md`

新 AI 先阅读：

1. AI-ONBOARDING
2. PROJECT-README
3. COLLABORATION-PROTOCOL
4. ROLE_MATRIX
5. WORKFLOW
6. 当前任务的 SOURCE / REVIEW / TEST 文件
7. 只有在执行 H3 Prompt 工作时，再阅读 V1-5 Skill

这样新 AI 可以知道：

- 项目是什么
- 当前 Baseline 是什么
- 自己是谁
- 自己负责什么
- 哪些文件可以读取
- 哪些文件属于 SOURCE
- 哪些内容不能覆盖
- 哪些修改需要用户批准
- Prompt 任务如何从 SOURCE 进入 FINAL

---

## 当前角色划分

### 用户

负责：

- 提出任务
- 给任务命名
- 提供/确认素材
- 批准采用哪些修改
- 批准 Prompt 正式收录
- 批准 Skill 修改
- 批准项目协作规则修改

### Grok

主要负责：

- Prompt 初稿
- Prompt 优化
- 实验
- 测试
- Execution-level 问题分析
- Reference Mapping 候选

### Gemini

主要负责：

- 独立 Review
- 多模态 / Reference 分析
- 反证
- 连续性、空间、动作、镜头执行问题分析
- 外部 Skill 研究
- Research Candidate 提炼

### GPT

主要负责：

- H3 结构审查
- V1-5 Baseline 对照
- Semantic / Reference / PATCH / PRESERVE 纪律审查
- 综合 Grok 与 Gemini 意见
- 项目协作整理
- 版本和研究结论整理

### 用户拥有最终批准权

---

## Prompt 任务生命周期

```text
SOURCE
  ↓
REVIEW
  ↓
RESEARCH CANDIDATE（如有）
  ↓
DRAFT
  ↓
TEST
  ↓
FINAL
```

SOURCE / ORIGINAL 永远不能被 Review 直接覆盖。

需要修改时建立新版本。

---

## Creative Enhancement 的定义

本次讨论中明确修正了一个概念：

**Creative Enhancement 指的是剧情 / 叙事 / 镜头创意提升，不是 Prompt 格式创意。**

因此分为两个层级：

### Prompt Execution / Compilation

用户已经决定发生什么。

AI 的任务是把已经授权的语义稳定、准确地编译成 H3 Prompt，不擅自改变剧情。

### Narrative Creative Enhancement

当用户明确要求：

- 丰富剧情
- 增加张力
- 设计镜头节奏
- 提供剧情方案
- 帮助构思

AI 才进入剧情 / 叙事创意阶段。

然后用户选择方案，再进入 Prompt Compilation。

---

## 与 V1-5 的关系

本次协作层建立没有修改 V1-5。

V1-5 仍然是：

**FROZEN BASELINE**

协作层不属于 H3 Skill。

H3 Skill 不承担 AI 团队角色管理。

---

## 本任务最终状态

**COMPLETED / 已完成。**

本任务的目的只是：

- 建立协作层
- 让未来新 AI 能够快速入职
- 让 Grok / Gemini 知道协作层已经存在
- 明确角色和工作流

不要求 Grok / Gemini 对本任务进行再次优化或参与修改。

以后如需修改协作层本身，应另建独立的协作层优化任务，并遵循用户批准机制。
