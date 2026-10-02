# COLLABORATION-OPERATING-RULES — 协作层通用运行规则

## 目的

将任务状态、对话检查点、AI 下班 / 接替、进度记录和完成报告串成一条可追溯的任务防丢失链。

## 一、任务生命周期必须可追溯

任何进入 GitHub 项目并被定义为独立任务的工作，都必须具有明确生命周期状态。

至少使用以下状态之一：

- `PLANNED` — 计划中
- `IN_PROGRESS` — 进行中
- `REVIEW` — 审查中
- `TESTING` — 测试中
- `AWAITING_APPROVAL` — 等待用户批准
- `COMPLETED` — 已完成
- `ARCHIVED` — 已归档

任务状态、`PROGRESS`、对话归档和完成报告必须能够互相对应。

---

## 二、任务防丢失链（Task Continuity Chain）

所有持续性任务统一采用：

```text
CURRENT CONVERSATION
        ↓
Task Conversation Checkpoint
        ↓
TASK-CONVERSATION / CONVERSATION-FULL
        ↓
PROGRESS
        ↓
AI HANDOFF（如 AI 下班 / 不可用）
        ↓
恢复 AI 读取当前任务状态
        ↓
继续任务
        ↓
TEST / REVIEW / APPROVAL
        ↓
COMPLETION-REPORT
        ↓
COMPLETED / ARCHIVED
```

核心原则：

> **AI 可以下班，任务不能丢。**

任何一个 AI 是否在线，不应决定任务上下文是否存在。

---

## 三、Task Conversation Checkpoint｜任务对话检查点

### 默认触发条件

同一任务累计约 **3–5 次有实质内容的任务对话 / 讨论轮次** 后，当前负责记录的 AI 应主动检查一次 GitHub 任务对话归档。

“实质内容”包括：

- 新决策
- 新研究结论
- 用户确认 / 否决
- AI 间重要分歧及解决
- Prompt / Skill / Experiment 版本变化
- 新实验假设
- 新测试结果
- 任务范围、约束、角色或职责变化

纯寒暄、重复确认、简单“好 / OK / 继续”等不计入。

### 检查点必须同步什么

默认同步**结构化重要信息**：

1. 当前任务状态
2. 自上次检查点以来的新决策
3. 用户批准 / 否决事项
4. 各 AI 独立意见
5. 尚未确认的候选方案
6. 新增 / 修改 / 冻结的版本
7. 新实验假设和结果
8. 当前阻塞项
9. 下一步行动
10. 当前 AI 是否即将下班或无法继续

### 立即同步例外

以下情况不等 3–5 轮：

- 用户明确说“这个很重要，不能丢”。
- 用户正式批准 / 否决。
- 任务范围发生变化。
- 版本状态发生变化。
- AI 角色或接替关系发生变化。
- 产生影响整个项目的新结论 / 通用规则。
- AI 即将下班、额度耗尽或预计无法继续。

### 原始记录规则

默认不逐字复制全部聊天。

如果用户明确要求“完整对话原样保存”，才建立 / 更新 `CONVERSATION-FULL`。

历史检查点不得覆盖；原则上采用追加方式，并注明：

```text
CHECKPOINT-N
DATE
TASK STATUS
KEY DECISIONS
AI OPINIONS
OPEN ITEMS
NEXT ACTION
```

---

## 四、PROGRESS 与 Checkpoint 联动

每次检查点同步后，如果任务存在 `PROGRESS` 文件，应同步更新：

- 当前完成百分比 / 阶段
- 已完成步骤
- 当前阶段
- 当前实验版本
- 已确认结论
- 待验证事项
- 下一步
- 最后同步检查点

`PROGRESS` 是**当前状态摘要**；
`TASK-CONVERSATION / CONVERSATION-FULL` 是**历史证据记录**。

两者不能互相替代。

---

## 五、AI 下班 / 接替机制与 Checkpoint 联动

如果 AI 因为：

- 对话次数耗尽
- Token / 上下文限制
- 服务限制
- 暂时不可用
- 其他会话限制

无法继续任务：

### 下班前

如果可以操作：

1. 立即写入最近的重要 Checkpoint。
2. 更新 `PROGRESS`。
3. 标明当前状态。
4. 标明未完成事项。
5. 标明下一步建议。
6. 如果有接替 AI，写入 Handoff 信息。

### 无法提前同步时

接替 AI 在获得当前会话内容后，应优先：

1. 读取任务目录。
2. 读取最近的 `TASK-CONVERSATION / CONVERSATION-FULL`。
3. 读取 `PROGRESS`。
4. 读取 AI Handoff 文件。
5. 判断 GitHub 是否存在未同步的最近重要内容。
6. 尽快补写缺失 Checkpoint。

### 接替纪律

接替 AI：

- 不覆盖原 AI 历史产出。
- 不把自己的判断冒充原 AI 判断。
- 不改变已批准结论。
- 不因为接替而自动重新优化已完成任务。
- 所有新增意见明确标注为自己的意见。

---

## 六、任务完成与 Completion Report

当任务达到用户确认的完成条件：

1. 标记 `STATUS: COMPLETED`。
2. 创建 / 更新 `COMPLETION-REPORT-完成报告.md`。
3. 记录：
   - 任务名称
   - 目标
   - 实际完成步骤
   - 最终产出
   - 关键决策 / 修正
   - 修改文件
   - 明确未修改文件
   - 测试 / 验证结果
   - 用户确认状态
   - 后续是否需要其他 AI
4. 不再继续自动修改已完成任务。
5. 如发现新问题，建立新任务并引用旧任务。

```text
TASK-A → COMPLETED
             ↓
        新问题出现
             ↓
TASK-B → 新任务
```

---

## 七、四类记录的职责分工

### `TASK-CONVERSATION / CONVERSATION-FULL`
保存任务过程中的重要事实和历史证据。

### `PROGRESS`
保存任务当前状态。

### `AI-HANDOFF`
保存 AI 下班 / 接替所需的最小连续性信息。

### `COMPLETION-REPORT`
保存任务最终完成结果。

标准关系：

```text
CONVERSATION
    ↓
CHECKPOINT
    ↓
PROGRESS
    ↓
HANDOFF（如需要）
    ↓
COMPLETION REPORT
```

---

## 八、历史上下文隔离

历史任务可以作为项目背景，但不得未经当前任务明确授权而自动成为当前任务的需求、证据、设计依据、优化目标或实验样本。

只有以下内容默认属于当前任务证据：

- 当前任务说明
- 当前任务目录中的指定文件
- 当前任务明确指定的外部资料
- 当前任务明确指定的历史任务 / Prompt
- 当前任务产生的新实验数据

历史任务只有在用户明确指定后，才能升级为当前任务证据。

> **相关不等于授权。**

该原则适用于 GPT、Gemini、Grok 以及未来加入项目的所有 AI。

---

## 九、多 AI 协作纪律

一个任务可以由多个 AI 分工完成，但必须区分：

```text
User Decision
GPT Opinion
Gemini Opinion
Grok Opinion
Research Candidate
Experimental Result
Approved Rule
```

任何 AI 建议不能自动变成用户批准结论。

任何 Research Candidate 不能自动升级为正式 Skill Rule。

任何实验版本不能自动覆盖 V1-5 Frozen Baseline。

---

## 十、对现有任务的适用

本规则适用于：

- Prompt Writing / 提示词编写
- Prompt Optimization / 提示词优化
- Skill Optimization / 技能优化
- External Skill Research / 外部 Skill 研究
- A/B Experiment / A-B 实验
- AI Collaboration / 协作层任务
- 未来新增任务类型

本文件属于**项目协作层通用运行规则**，不修改 V1-5 H3 Prompt Skill 的生成规则。

如果未来需要修改 V1-5 Skill，必须建立独立 Skill Optimization 任务并经过验证和用户批准。
