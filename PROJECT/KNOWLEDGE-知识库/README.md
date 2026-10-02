# H3NSFW Prompt Project — Knowledge Base
# H3NSFW Prompt 项目知识库

## 目的

本目录用于保存项目在实际 MiniMax H3 Prompt 编写、优化、研究和测试过程中形成的**可复用工程知识**。

它不是 SKILL.md，也不是新的 Skill Framework。

核心目的：

> 把实际经验、实验结果、失败现象和经过验证的表达规律与 Skill 本体分离保存，避免因为一次观察就修改通用 Skill。

---

## 知识进入路径

```text
Observation / Failure
        ↓
Research Record
        ↓
Candidate
        ↓
Experiment / A-B Test
        ↓
Validated Finding
        ↓
User Review
        ↓
Approved Knowledge
        ↓
（只有必要且获批准时）Skill Candidate
```

**Knowledge Base ≠ Skill。**

进入知识库不代表该内容自动成为 Skill 默认规则。

---

## 证据状态

每条知识记录建议明确标记来源状态：

### OFFICIAL
MiniMax 官方资料明确支持的机制、结构、格式或职责。

### APPROVED
已经被本项目用户明确确认并作为项目规则/知识采用的内容。

### EXPERIMENTAL
项目 A/B 测试或实际 H3 运行中得到的候选规律，尚未完成稳定验证。

### OBSERVATION
单次或少量样本观察到的现象。只记录，不推导成通用规则。

### COMMUNITY
来自社区、作者、工作流或第三方案例的经验。除非经过独立验证，不自动升级为项目规则。

### INFERENCE
模型或研究者的推断。必须明确标记，不能伪装成官方机制。

---

## Semantic Addition 边界

知识库可以记录“某种写法可能有用”，但不能因此自动改变用户没有授权的 Prompt 内容。

特别区分：

- **Execution enrichment**：让已经授权的语义更容易被 H3 执行。
- **Semantic invention**：增加用户没有要求的新动作、新状态、新限制、新剧情或新视觉内容。

前者可以作为 Prompt Engineering 观察；后者不得因为“模型可能更稳定”而自动进入最终 Prompt。

---

## NSFW Prompt Engineering 知识

本项目可以记录 NSFW Prompt 的工程性观察，例如：

- 动作描述是否容易被 H3 执行；
- 动作时序与状态连续性；
- 姿势和身体关系描述；
- 表情与动作之间的关系；
- 湿润/液体等视觉状态的连续性观察；
- 多参考图在 NSFW 场景中的 Reference Mapping；
- Camera / POV 对动作执行的影响；
- Temporal continuity；
- Prompt wording 的 A/B 测试结果；
- 常见失败模式及其复现条件。

这些记录属于**工程研究资料**，不自动成为 Skill 默认内容。

---

## Reference Mapping 知识

参考素材必须区分：

- 用户明确指定的职责；
- AI 提出的最小必要 Mapping 候选；
- 从素材中观察到但未获授权的内容。

素材观察不得自动升级为最终 Prompt 内容。

例如：

`Picture 1 = identity / face / hair`

并不意味着 Picture 1 中出现的所有服装、动作、背景和其他视觉元素都自动进入 Prompt。

---

## 实验记录原则

如果某种表达被认为“可能更稳定”，优先记录为实验候选，而不是修改 Skill。

A/B 实验原则：

- Baseline 与 Candidate 尽可能只改变一个变量；
- 记录输出差异；
- 记录副作用；
- 不以单次成功作为通用机制证明；
- 多次独立结果后再考虑升级为 Validated Finding；
- 最终是否进入 Skill 由用户决定。

---

## 与 SKILL.md 的边界

`baseline/` 保存当前冻结 Skill 镜像。

本知识库保存研究与工程知识。

两者关系：

```text
SKILL.md
  = 当前批准的执行规则

Knowledge Base
  = 项目研究、经验、实验和验证资料
```

不要因为 Knowledge Base 中出现某条规律，就直接修改 SKILL.md。

如果未来认为某条知识应该进入 Skill，必须先建立明确的 Skill Candidate，并经过用户批准。

---

## 与正式 Prompt Library 的边界

`PROJECT/LIBRARY-正式库/PROMPTS-正式提示词/`
保存用户确认的正式 Prompt。

Knowledge Base 保存的是“知识与证据”。

因此：

- 一个 Prompt 可以进入正式库，而不代表其中所有写法都成为通用知识；
- 一个知识观察可以存在于知识库，而不代表应该用于所有 Prompt；
- 正式 Prompt、实验 Prompt、知识观察必须保持可追溯关系。

---

## 新 AI 入组

任何未来加入本项目的 AI，先阅读根目录 `AI_ONBOARDING.md`，再阅读本 README。

随后根据具体任务读取相关 Knowledge、Experiment、Prompt 或 Skill 文件。

新 AI 不应仅因为“历史记录中某种写法出现很多次”就认定它是 Skill 默认规则。

---

## 当前状态

当前 Skill 基线：**V1-5 Frozen Baseline**。

本知识库的建立不会自动开启新的 Skill 版本，也不会改变当前 Skill。
