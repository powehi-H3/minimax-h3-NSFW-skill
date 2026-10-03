# GitHub / Skill Update Declaration｜更新声明

> STATUS: ACTIVE
> 用途：任何 AI 在协作过程中声称“GitHub 已更新”“Skill 已更新”“已读取最新版本”时，必须先遵守本声明。

## 1. 更新不是“只看改动文件”

当任一 AI 发现 GitHub / Skill 有更新时，不能因为已经知道“更新了什么”就跳过完整检查。

在继续执行任何依赖最新 Skill / GitHub 状态的任务前，必须：

1. 检查仓库当前状态与最新提交；
2. 检查当前任务相关目录；
3. **完整读取当前正式 Skill 的全部相关文件**，不能只读取本次修改文件；
4. 完整读取实验 Skill 的全部相关文件（如果当前任务涉及实验 Skill）；
5. 读取当前任务要求指定的协作 / READ-FIRST / STATUS / CHECKPOINT / CHANGE 文件；
6. 对照更新声明确认本次更新究竟改变了什么；
7. 再开始实际分析、生成 Prompt 或修改文件。

“AI 已经知道更新内容”不等于“完成了读取检查”。

## 2. 每次 GitHub / Skill 更新必须留下 Update Declaration

更新完成后，必须有明确声明记录：

- 更新时间
- 执行 AI
- Commit SHA（如果可获得）
- 修改文件
- 新增文件
- 删除文件
- Skill 是否修改
- 正式 V1-5 是否仍 FROZEN
- 实验版本是否受到影响
- 对其他 AI 的读取要求
- 下一步动作

推荐格式：

```text
## YYYY-MM-DD HH:MM｜AI

Update Type:
GITHUB / SKILL / EXPERIMENT / COLLABORATION

Commit:
<sha>

Changed:
- <path>
- <path>

Skill Impact:
- Official V1-5: FROZEN / CHANGED
- Experiment B: unchanged / changed
- Experiment A: unchanged / changed

Required Re-read:
- Formal Skill: ALL relevant files
- Experiment Skill: ALL files when applicable
- Task / Collaboration files: ALL specified files

Next Action:
<description>
```

## 3. 正式 Skill 与实验 Skill 必须分开声明

任何更新都必须明确属于：

- Official Skill / V1-5
- Experiment A
- Experiment B
- Collaboration Layer
- Daily Archive
- Task Archive

不能只写“Skill updated”而不说明是哪一层。

## 4. AI 恢复会话后的读取纪律

即使另一个 AI 已经告诉你：

> “GPT 已经更新了 B Skill。”

你仍然必须自己重新检查 GitHub 当前状态，并重新读取本任务要求的全部相关 Skill 文件。

不能把其他 AI 的摘要当作文件读取的替代品。

## 5. 与 Daily / Task 归档规则的关系

普通协作内容：

`→ DAILY-CONVERSATIONS`

用户明确指定任务归档：

`→ TASK DIRECTORY`

GitHub / Skill Update Declaration 属于协作层的版本同步记录，不替代 Daily 或 Task 正式记录。

## 6. 最高原则

> **知道发生了什么 ≠ 读过最新文件。**
>
> **摘要 ≠ Source of Truth。**
>
> **任何依赖最新 Skill 的执行，都必须重新读取最新 Skill 文件。**

GitHub 当前文件内容与用户明确授权，是最终 Source of Truth。

## 7. Daily Conversation Read Intent｜日常对话读取语义（新增）

当用户明确说：

> **“查看日常对话” / “看一下日常记录” / “读取日常对话”**

默认含义不是让 AI 做归档说明，也不是让 AI 只挑选某个主题，而是：

> **用户正在通知当前 AI：另一个 AI 已经把它截至当前时点的最新聊天内容同步进 Daily Conversations，当前 AI 需要读取这些最新日常记录，以恢复跨 AI 协作上下文。**

因此，收到这种指令后，当前 AI 应：

1. 进入当前日期对应的 `DAILY-CONVERSATIONS-日常对话` 文件；
2. 优先读取当天最新日常文件；
3. 必要时衔接读取紧邻的上一份日常记录，以恢复上下文连续性；
4. 将 Daily Conversation 视为当前 AI 的**协作上下文输入**；
5. 读取后再继续用户当前任务。

除非用户明确说明其他目的，否则**不要把“查看日常对话”理解成要求整理、重写、审核、迁移或归档日常文件。**

如果用户说的是“把这段对话存到日常”，才执行 Daily Archive 写入流程；如果用户说“把某某内容存到当前任务”，才执行 Task Archive 写入流程。

### 7.1 Daily 是跨 AI 上下文桥接，不是任务真相源

Daily Conversation 的主要用途是：

`GPT ↔ Grok ↔ 其他 AI`

之间传递近期协作上下文。

它不是对正式 Skill、Task Archive 或 Update Declaration 的替代品。

当 Daily 与正式 Task / Skill 文件发生冲突时，应继续遵循既有的 Source of Truth 层级，而不能因为 Daily 中出现某个说法就自动升级为正式规则。

## 8. Daily / Task 写入规则仍保持不变

- 用户说“存到日常” → 写入 Daily Conversation；
- 用户说“存到当前任务 / 某某任务” → 写入对应 Task Directory；
- 用户没有明确指定任务归档 → 不自行把普通对话升级成 Task Archive；
- Daily 文件按日拆分，避免单文件无限增长；
- Daily 条目必须保留来源前缀：`用户:` / `GPT:` / `GROK:` 等；
- AI 自己写入的条目应标明执行 AI 与时间；
- 如一条内容同时涉及多个 AI，应分别保留实际来源，不得把其他 AI 的原话冒充为当前 AI 的内容。
