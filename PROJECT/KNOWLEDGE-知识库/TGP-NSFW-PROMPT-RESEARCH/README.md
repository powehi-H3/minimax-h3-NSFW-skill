# TGP — NSFW Prompt Research
# TGP — NSFW 提示词研究与协作区

## Purpose / 用途

本目录用于保存**无法在某一 AI 对话界面中直接完成的 NSFW Prompt 相关研究、审查意见、Prompt 工程候选和跨 AI 协作记录**。

它是项目 Knowledge Base 的一个专门分区。

它不是 SKILL.md，也不是新的 Skill Framework。

## Important boundary / 重要边界

如果某个 AI 在自己的交互环境中存在内容能力边界，该 AI **不能通过 GitHub 把被拒绝生成的内容“绕过限制”**。

GitHub 在这里的作用是：

- 保存已经允许进入项目的研究资料；
- 保存用户提供的素材与待审查 Prompt；
- 保存其他 AI 已经合法完成的 Prompt 草稿/分析；
- 保存审核意见、实验结果和版本记录；
- 让不同 AI 在项目层面共享上下文。

**GitHub 是协作与知识记录层，不是安全限制的绕过层。**

## Recommended workflow / 推荐流程

```text
User Request
    ↓
AI 判断自己能否直接处理
    ↓
如果可以 → 正常对话处理
    ↓
如果需要跨 AI 审查 → 写入对应 TGP 任务记录
    ↓
Grok / Gemini / 其他有能力的参与者按各自角色处理
    ↓
GPT / Gemini / Grok 交叉审查
    ↓
User Final Approval
    ↓
正式 Prompt → PROJECT/LIBRARY-正式库/PROMPTS-正式提示词/
研究发现 → Knowledge Base
Skill 改动 → 只有 User 批准后进入 Skill 变更流程
```

## What belongs here / 可以保存什么

### 1. Prompt Review

已有 Prompt 的结构、表达、Reference Mapping、时序、Camera、动作连续性等审查记录。

### 2. Prompt Candidates

经过项目参与者提出、但尚未正式批准的候选写法。

### 3. Cross-AI Review

GPT / Grok / Gemini 对同一 Prompt 的不同意见和最终结论。

### 4. NSFW Engineering Observations

实际 H3 测试中发现的工程现象，例如动作执行、状态连续、Reference 污染、镜头稳定等。

### 5. Accepted Prompt Archive Link

已经通过 User 审核的 Prompt 应进入正式 Prompt Library；这里可以保存其研究来源和决策链，而不是把正式库与研究库混在一起。

## Evidence discipline / 证据纪律

每个候选至少标记：

- `OFFICIAL`
- `APPROVED`
- `EXPERIMENTAL`
- `OBSERVATION`
- `COMMUNITY`
- `INFERENCE`

不要因为某个 Prompt 成功一次，就把写法升级为 Skill 默认规则。

## Skill boundary / Skill 边界

TGP 中的任何内容默认不会改变 V1-5 Frozen Skill。

如果发现真正的 Skill 缺口：

```text
Observation
→ Candidate
→ Evidence
→ Experiment（必要时）
→ Review
→ User Approval
→ Skill Change Candidate
→ User Approval
→ Skill Update
```

## Task naming / 任务命名

具体任务名称由 User 命名。

建议格式：

`TGP-XXXX-用户命名`

例如：

`TGP-0001-桌下场景Prompt优化`

但最终名称以 User 指定为准。
