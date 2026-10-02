# AI-AVAILABILITY — AI 可用性与会话限制通用协作机制

> STATUS: ACTIVE / 通用协作规则
> 层级：PROJECT 协作层
> 不属于 V1-5 H3 Prompt Skill

## 1. 为什么需要这条规则

多 AI 协作项目中，不同 AI 可能存在：

- 对话次数限制
- 当日额度耗尽
- 暂时不可用
- 上下文长度限制
- 工具连接暂时不可用
- GitHub 权限暂时不可用
- 模型版本或服务状态变化
- 用户主动让某个 AI 暂停工作

这些属于**协作资源状态**，不应导致项目任务中断、丢失或重新开始。

因此，“某个 AI 下班/暂时不可用”本身应被视为一种正常的项目运行状态，而不是异常。

---

## 2. AI 暂时不可用 ≠ 任务失败

当一个 AI 暂时无法继续对话时：

**不得把 AI 不可用直接解释为任务失败。**

应该保存当前任务状态，并记录：

- 当前 AI
- 当前任务
- 已完成到哪一步
- 最后一次有效产出
- 尚未完成的事项
- 是否存在待审查内容
- 下一步应该由谁继续

然后根据任务角色矩阵决定是否需要其他 AI 接替。

---

## 3. 接替机制

如果某 AI 暂时不可用：

```text
AI-A 正常工作
      ↓
AI-A 暂时不可用
      ↓
保存状态 / 写入 GitHub
      ↓
判断任务是否允许接替
      ↓
AI-B 接替执行
      ↓
保留 AI-A 的原始产出
      ↓
AI-A 恢复后继续读取历史
```

接替 AI **不得伪装成原 AI**。

必须明确：

> “本次由 AI-B 临时接替 AI-A，AI-A 的原始产出保持不变。”

---

## 4. 接替前必须读取什么

接替 AI 不应该依赖用户重新口述整个项目。

优先读取：

1. `PROJECT/AI-ONBOARDING-新AI入职说明.md`
2. `PROJECT/PROJECT-README.md`
3. `PROJECT/COLLABORATION-PROTOCOL-协作协议.md`
4. `PROJECT/ROLE_MATRIX.md`
5. `PROJECT/WORKFLOW-工作流.md`
6. 当前任务目录
7. 当前任务的 SOURCE / ORIGINAL
8. 最近一次 REVIEW / DRAFT / TEST / COMPLETION-REPORT
9. 如涉及 Skill，再读取当前 V1-5 Skill

然后再决定是否能够安全接替。

---

## 5. 接替权限边界

“临时接替”只代表**继续执行当前任务允许执行的工作**。

不代表自动获得更高权限。

例如：

- Prompt Draft AI 暂时不可用 → Reviewer 可以继续 Review，但不能因此自动修改 Skill。
- Reviewer 暂时不可用 → 其他 Reviewer 可以继续独立审查，但不能冒充原 Reviewer 的结论。
- Skill Research AI 暂时不可用 → 其他 AI 可以继续研究，但已有 Research Candidate 不得被悄悄改写成正式规则。

所有原有审批和用户批准要求继续有效。

---

## 6. 原始产出保护

任何 AI 暂时离线时：

**必须保留它最后一次有效产出。**

不得因为接替而：

- 覆盖 SOURCE
- 删除原始 Draft
- 修改原 AI 的 Review 冒充新 Review
- 将新 AI 的判断写回旧 AI 文件
- 丢失原 AI 的失败实验记录

正确方式：

```text
GROK/DRAFT-V1.md
GEMINI/REVIEW-V1.md
GPT/REVIEW-V1.md

↓

新的 AI 接替

↓

GPT/TAKEOVER-REVIEW.md
```

而不是覆盖原文件。

---

## 7. “下班 / 暂停”状态记录

如果 AI 因对话次数、额度或服务限制暂时无法继续，可在当前任务目录建立：

`AI-STATUS-当前AI状态.md`

记录：

```text
AI：Grok
状态：TEMPORARILY_UNAVAILABLE
原因：会话次数 / 额度限制
任务：PW-XXXX
最后完成步骤：XXXX
最后有效产出：XXXX
待完成：XXXX
接替 AI：XXXX
```

恢复后，该 AI 优先读取状态文件即可继续。

如果用户不要求详细记录，也可以只在任务的 STATUS / HANDOFF 文件中记录，不强制增加文件数量。

---

## 8. HANDOFF 交接文件

当接替明显涉及上下文丢失风险时，使用：

`HANDOFF-交接记录.md`

至少记录：

- 原 AI
- 接替 AI
- 接替原因
- 当前任务状态
- 已完成内容
- 未完成内容
- 不允许改变的内容
- 下一步建议

### 重要

HANDOFF 是交接说明，不是新的决策来源。

它不能覆盖 SOURCE，也不能把“建议”伪装成用户批准的决定。

---

## 9. 不同 AI 恢复后的处理

原 AI 恢复后：

1. 先读取当前任务状态。
2. 读取 HANDOFF（如存在）。
3. 读取接替期间的新产出。
4. 区分：
   - 自己原来的产出
   - 接替 AI 的产出
   - 用户批准的内容
   - 尚未批准的候选
5. 不得自动撤销接替 AI 的工作。
6. 如有分歧，提交给用户或按角色矩阵进行独立 Review。

---

## 10. 用户切换 AI

用户可以随时决定：

- 让 GPT 接替 Grok
- 让 Grok 接替 GPT
- 让 Gemini 接替某个研究任务
- 暂停所有 AI
- 恢复之前的 AI
- 增加新的 AI

AI 不应把这种切换视为角色冲突。

项目的事实来源始终是 GitHub 中的版本化记录和用户批准的决策。

---

## 11. 新 AI 加入项目

如果以后增加第四、第五、第六个 AI：

不需要重新设计整个协作机制。

新 AI：

1. 阅读 AI-ONBOARDING。
2. 阅读 ROLE_MATRIX。
3. 用户指定其角色。
4. 从当前任务状态接入。
5. 保留原 AI 历史记录。

因此 AI 数量变化不会破坏项目工作流。

---

## 12. 任务完成优先于 AI 连续在线

项目追求的是：

**任务连续性，而不是某一个 AI 永久在线。**

AI 是可替换的协作角色；
GitHub 中的版本化任务记录才是项目连续性的基础。

因此：

> AI 可以下班，任务不能丢。

---

## 13. 与任务完成规则的关系

本规则与：

`COLLABORATION-OPERATING-RULES-协作层通用运行规则.md`

配合使用。

任务完成后仍必须：

- `STATUS: COMPLETED`
- `COMPLETION-REPORT-完成报告.md`

如果 AI 在任务中途不可用，则先执行本文件的状态保存 / HANDOFF 机制；任务完成后再执行标准完成归档。

---

## 14. 最小化原则

不要为了每一次短暂的额度限制制造大量文件。

原则：

- 简单切换 → 在任务 STATUS 中记录即可。
- 明显上下文交接 → 使用 HANDOFF。
- 长时间暂停 / 多 AI 接替 → 使用 AI-STATUS。
- 任务完成 → 使用 COMPLETION-REPORT。

**记录应足够让另一个 AI 无歧义接手，但不要制造无意义的文档负担。**
