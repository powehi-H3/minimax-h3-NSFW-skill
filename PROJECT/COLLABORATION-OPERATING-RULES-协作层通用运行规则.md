# COLLABORATION-OPERATING-RULES — 协作层通用运行规则

## 目的

将“任务完成后必须明确标记状态，并保留完成记录”的做法提升为整个项目的通用运行规则。

## 通用规则：任务生命周期必须可追溯

任何进入 GitHub 项目并被定义为一个独立任务的工作，都必须具有明确的生命周期状态。

至少使用以下状态之一：

- `PLANNED` — 计划中
- `IN_PROGRESS` — 进行中
- `REVIEW` — 审查中
- `TESTING` — 测试中
- `AWAITING_APPROVAL` — 等待用户批准
- `COMPLETED` — 已完成
- `ARCHIVED` — 已归档

## 完成时必须做什么

当任务已经达到用户确认的完成条件时，必须完成以下步骤：

1. 在任务目录或任务主记录中明确标记：`STATUS: COMPLETED`。
2. 创建或更新 `COMPLETION-REPORT-完成报告.md`。
3. 在完成报告中记录：
   - 任务名称
   - 任务目标
   - 实际完成步骤
   - 最终产出文件
   - 关键决策 / 修正
   - 哪些文件被修改
   - 哪些文件明确没有修改
   - 测试 / 验证结果（如有）
   - 用户最终确认状态
   - 后续是否还需要其他 AI 参与
4. 如果任务已经结束且不需要继续修改，可标记为 `ARCHIVED`；但不得删除完成记录。
5. 后续 AI 进入项目时，应能够仅通过任务状态和完成报告判断该任务是否已经结束，以及自己是否需要参与。

## 已完成任务不得被重新打开式修改

如果一个任务已经标记 `COMPLETED`，其他 AI 不应因为看到该任务而自动重新 Review、优化或改写。

如发现新的问题，应建立一个**新的任务**，并引用原任务作为来源。

例如：

```text
TASK-A  → COMPLETED
             ↓
发现新问题
             ↓
TASK-B  → 新任务
```

不得直接把 TASK-A 改成一个混合任务。

## 多 AI 协作规则

当一个任务完成后：

- 已参与 AI：保留历史记录。
- 未参与 AI：原则上只需要读取完成报告了解结果。
- 后续需要继续研究时：创建新的任务，而不是修改已完成任务的历史记录。

## 原始记录与完成报告必须并存

`SOURCE / CONVERSATION-FULL / ORIGINAL` 等原始记录用于保留事实来源。

`COMPLETION-REPORT` 用于说明任务最终做到了什么。

二者不能互相替代。

## 对现有任务的适用

本规则同样适用于：

- Prompt Writing / 提示词编写
- Prompt Optimization / 提示词优化
- Skill Optimization / 技能优化
- External Skill Research / 外部 Skill 研究
- AI Collaboration / 协作层任务
- 未来新增的其他任务类型

## 与 V1-5 Skill 的关系

本文件属于**项目协作层通用运行规则**。

它不修改、不扩展 V1-5 H3 Prompt Skill 的生成规则。

如果未来需要修改 V1-5 Skill，必须按照独立 Skill Optimization 任务流程处理，并经过用户批准。
