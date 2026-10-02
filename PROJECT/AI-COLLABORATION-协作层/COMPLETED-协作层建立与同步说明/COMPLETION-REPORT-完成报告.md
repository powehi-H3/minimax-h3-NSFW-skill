# 协作层建立与同步说明 — 完成报告

**STATUS: COMPLETED / 已完成**

## 1. 任务目标

建立一个独立于 V1-5 H3 Prompt Skill 的项目协作层，使现有 AI 与未来加入的新 AI 都能够明确理解：

- 项目是什么
- 当前 Baseline 是什么
- 自己的角色是什么
- 自己应该读取哪些文件
- Prompt 任务如何流转
- SOURCE / REVIEW / CANDIDATE / DRAFT / TEST / FINAL 如何区分
- 哪些内容不能覆盖
- 哪些修改必须经过用户批准

## 2. 已完成步骤

### Step 1 — 区分两个层级

明确将项目分成：

**项目协作层**

负责 AI 角色、权限、工作流、版本纪律、入职说明与协作机制。

**H3 Prompt Skill 层**

负责 V1-5 Frozen Skill 本身的 H3 Prompt 编写与执行方法。

因此，AI 角色和协作规则不塞入 V1-5 Skill。

### Step 2 — 建立新 AI 入职入口

创建：

`PROJECT/AI-ONBOARDING-新AI入职说明.md`

规定新 AI 加入后先阅读协作层文件，再进入具体任务。

### Step 3 — 建立项目总览

创建：

`PROJECT/PROJECT-README.md`

明确项目目标、V1-5 Frozen Baseline、最终决策权属于用户，以及协作层与 Skill 层的区别。

### Step 4 — 建立协作协议

创建：

`PROJECT/COLLABORATION-PROTOCOL-协作协议.md`

明确：

`SOURCE → REVIEW → RESEARCH CANDIDATE → DRAFT → TEST → FINAL`

并规定 SOURCE 不得被覆盖，Review 不得伪装成 Original，Candidate 不得自动升级为 Skill 规则。

### Step 5 — 建立角色矩阵

创建：

`PROJECT/ROLE_MATRIX.md`

明确：

- 用户：需求、命名、授权、最终批准
- Grok：Prompt 初稿、优化、实验、测试、Execution 分析
- Gemini：独立 Review、多模态分析、反证、外部研究
- GPT：H3 结构审查、Baseline 对照、综合分析、协作整理

### Step 6 — 建立标准工作流

创建：

`PROJECT/WORKFLOW-工作流.md`

明确从用户命名、Brief、SOURCE、初稿、Review、Candidate、用户批准、Test 到 Final 的流程。

### Step 7 — 单独定义 Creative Enhancement

本次协作层建设过程中修正了概念：

**Creative Enhancement = 剧情 / 叙事 / 镜头创意提升。**

它不是 Prompt 格式创意。

当用户已经明确剧情时，不擅自改剧情；只有用户明确要求丰富剧情、增加张力、设计镜头节奏或提供创意方案时，才进入 Narrative Creative Enhancement。

### Step 8 — 单独归档本次完整对话

创建：

`PROJECT/AI-COLLABORATION-协作层/COMPLETED-协作层建立与同步说明/CONVERSATION-FULL-完整对话.md`

用于保留本次协作层设计过程与最终结论。

## 3. 当前完成状态

本任务已经完成。

**不需要 Grok / Gemini 再参与修改本任务。**

它们只需要读取并知晓协作层已经建立。

如果未来需要修改协作层本身，应建立新的独立任务，不回写本任务的完成状态。

## 4. 未修改内容

本次任务没有修改：

- V1-5 Frozen Skill
- 任何已有 Prompt SOURCE
- PW-0001 原始 Prompt
- Skill Optimization 任务的研究结论

## 5. 后续工作入口

完成本协作层任务后，项目继续回到独立任务：

**优化skill--参考别人的github技能skill**

该任务负责研究外部 GitHub Skill，不与本协作层任务混合。