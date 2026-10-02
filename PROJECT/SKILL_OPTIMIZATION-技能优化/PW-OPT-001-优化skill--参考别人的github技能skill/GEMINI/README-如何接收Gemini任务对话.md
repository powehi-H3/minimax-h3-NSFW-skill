# Gemini 任务对话接收说明

> STATUS: ACTIVE / 协作记录机制
> 用途：Gemini 无法直接写 GitHub 时，由 GPT 接收用户转发的 Gemini 单个任务对话，并将其作为该任务的协作记录保存。

## 1. 基本原则

Gemini 的单个任务对话属于项目协作证据/工作记录。

当用户把 Gemini 与用户之间的某个具体任务对话转发给 GPT 时，GPT 应：

1. 先完整阅读用户提供的 Gemini 对话。
2. 保留 Gemini 的原始术语、判断、候选方案、证据、结论和不确定性。
3. 不把 Gemini 的候选意见自动改写成项目正式规则。
4. 不把 GPT 自己的观点混入 Gemini 原始记录。
5. 将 Gemini 对话保存到**对应的当前任务目录**。
6. 如需要，另建 GPT 的独立 Review 文件，不覆盖 Gemini 原始记录。

## 2. 当前任务定位

本规则首先用于：

`PW-OPT-001-优化skill--参考别人的github技能skill`

目录建议：

```text
PW-OPT-001-优化skill--参考别人的github技能skill/
├── SOURCE-外部Skill研究素材/
├── GEMINI/
│   ├── README-如何接收Gemini任务对话.md
│   └── [具体任务对话记录]
├── GROK/
├── GPT/
├── RESEARCH-CANDIDATES/
├── TEST/
└── COMPLETION-REPORT-完成报告.md
```

以后其他任务也可以复用同样机制。

## 3. “完整对话”与“GPT Review”必须分开

如果用户要求“把 Gemini 的本次任务对话完整放进 GitHub”，则保存的是：

**Gemini 原始对话记录。**

不要在原始记录中：

- 净化
- 重写
- 擅自纠错
- 合并 GPT 意见
- 删除 Gemini 的反对意见
- 把 Research Candidate 改成正式结论

如果 GPT 需要提出自己的判断，另建：

`GPT/REVIEW-...md`

## 4. 如果 Gemini 的对话很长

不要因为太长而只保存“GPT 认为重要的部分”作为所谓完整对话。

如果用户明确要求完整记录，应尽量保存用户实际提供的完整内容。

如果来源本身不完整，则明确标记：

`SOURCE STATUS: PARTIAL / 用户提供的对话并非完整记录`

不得把缺失部分自行补写成 Gemini 原话。

## 5. 任务状态

Gemini 的对话属于当前任务的一部分，不自动创建新任务。

例如当前任务是：

`PW-OPT-001-优化skill--参考别人的github技能skill`

那么 Gemini 的相关对话直接归入该任务的 `GEMINI/`。

只有当用户明确开始另一个独立任务时，才建立新的任务目录。

## 6. 多 AI 协作关系

Gemini 无法直接写 GitHub 并不意味着它的工作不进入项目。

用户将 Gemini 的任务对话转发给 GPT 后：

```text
用户 ↔ Gemini
       ↓
用户转发任务对话
       ↓
GPT 阅读 / 原样归档
       ↓
GitHub 当前任务/GEMINI/
       ↓
Grok / GPT / 其他 AI 读取
```

这样 Gemini 的研究和判断能够成为其他 AI 的可追溯协作记录。

## 7. 原始记录保护

Gemini 原始对话一旦归档，不应被后续 AI 直接覆盖。

后续若发现问题：

```text
Gemini 原始记录
       ↓
GPT Review / Grok Review
       ↓
用户批准
       ↓
正式任务结论
```

## 8. 用户批准仍然是最终决策源

Gemini 的分析可以是：

- 建议
- 研究结果
- 反证
- Research Candidate
- 风险分析
- 方案比较

但除非用户确认，否则不能自动升级为：

- 正式 Skill Rule
- Frozen Baseline 修改
- FINAL Prompt
- 项目级通用规则

## 9. 当前执行要求

当用户下一次把 Gemini 的一个具体任务对话发给 GPT 时：

**先完整阅读 → 确认它属于哪个当前任务 → 原始归档到该任务/GEMINI/ → 再根据用户是否要求 Review 决定是否建立 GPT Review。**

不要自行改变任务范围。
