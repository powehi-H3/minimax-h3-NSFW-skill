# H3NSFW Prompt Project — AI Onboarding
# H3NSFW Prompt 项目 — 新 AI 入组说明

> 本文件是给任何未来加入本项目的 AI 的第一份说明。
> 目标：AI 只要读取本文件，再按“阅读顺序”读取项目文件，就能理解这个仓库是做什么的、当前基线是什么、自己应该怎么工作，以及哪些事情不能擅自做。

---

## 1. 这个项目是什么？

这是一个 **MiniMax H3 NSFW Prompt Project**。

项目核心用途是：

- 根据 User 的需求编写 MiniMax H3 NSFW 视频提示词；
- 优化已有 MiniMax H3 NSFW Prompt；
- 根据图片、视频、Prompt 素材进行参考分析与重新编译；
- 重点处理多参考 / Multi-Reference / Multi-Image 工作流；
- 对 Prompt 进行实际测试，并记录观察结果；
- 在有充分证据并经过 User 批准时，最小化地优化 Skill 本身。

**项目的核心不是制造更多规则，而是让现有 Skill 更准确地表达 User 已授权的语义，并提高 MiniMax H3 Prompt 的实际可执行性。**

---

## 2. 当前唯一 Skill Baseline

当前项目 Skill：

**H3NSFW提示词技能skill第三版 — V1-5**

状态：**FROZEN / 冻结**

仓库中同时存在：

- 根目录的 Skill ZIP 源文件；
- `baseline/` 下的冻结 Skill 镜像；
- 项目正式库中的历史/正式版本记录。

未来 AI **必须先确认当前 STATUS.md 与 DECISIONS.md，再把 V1-5 当作当前 Skill 基线**。

不要因为历史对话、旧实验或自己的判断自动开启 V1-6，也不要自动重构 SKILL.md。

---

## 3. 新 AI 的第一阅读顺序

加入项目后，按下面顺序读取：

### 第 1：`AI_ONBOARDING.md`

理解整个项目。

### 第 2：`STATUS.md`

确认当前项目状态、当前 Skill Baseline、当前优先任务。

### 第 3：`DECISIONS.md`

读取已经被 User 正式确认的项目决策。

### 第 4：`ROLE_MATRIX.md`

理解 User、GPT、Grok、Gemini 以及未来 AI 的角色边界。

### 第 5：`PROJECT/README.md`

理解工作区、正式库、模板和任务生命周期。

### 第 6：当前 Skill Baseline

读取 `baseline/` 中当前冻结 Skill 镜像，并以其实际内容作为 Prompt 编写执行依据。

### 第 7：相关任务目录

只有在具体任务需要时，再读取：

- `PROJECT/WORKSPACE-工作区/`
- `research/`
- `experiments/`
- `GPT/`
- `GROK/`
- `GEMINI/`

不要为了普通 Prompt 任务把所有历史记录全部读一遍。

---

## 4. 官方 H3 规则优先级

MiniMax H3 官方资料对以下内容具有最高结构性优先级：

- 官方字段 / 六段结构；
- Reference 职责；
- 官方 Prompt syntax；
- 时间轴与 temporal 表达；
- Camera / POV 等官方机制；
- 官方明确规定的其他 Prompt 机制。

必须严格区分：

**官方机制 ≠ 官方示例内容。**

官方示例中出现的人物、剧情、动作、服装、场景、LoRA、措辞等，不会因为出现在官方示例里就自动成为本项目默认内容。

---

## 5. 素材如何使用

User 可能提供：

- Prompt 素材；
- 图片；
- 视频；
- 截图；
- Reference 图；
- 其他 H3 工作流资料。

必须区分：

### User 明确要求

可以进入最终 Prompt。

### Reference / Sample 观察

属于观察资料，不能自动变成最终 Prompt 内容。

### 模型推断

不能因为“这样可能更稳定”就自动写进 Prompt。

### Execution Enrichment

可以让已经授权的语义更容易被 H3 执行，但不能借此创造新的动作、状态、关系、情绪、限制或事件。

核心原则：

> **Learn the HOW, not unauthorized CONTENT.**

---

## 6. Prompt 修改纪律

如果 User 说：

- “只改这个”；
- “加这个，其他不动”；
- “把这一点改掉”；
- “只优化动作”；

就应该把它理解为**有限修改**。

修改指定内容，并尽可能 Preserve 其他已经批准的内容。

不要把 User 的修改指令原句直接写进最终 Prompt。

不要顺手把整份 Prompt 重新润色成另一个版本。

---

## 7. 不要把问题自动升级成 Skill 问题

看到某一次 H3 生成失败时，先问：

1. 是 Prompt wording 问题？
2. 是 Reference Mapping 问题？
3. 是具体模型生成行为？
4. 是测试变量问题？
5. 还是确实存在 Skill 覆盖缺口？

只有有充分证据时，才提出 Skill Change Candidate。

**Research / Candidate / Experiment ≠ Skill Rule。**

---

## 8. 四方协作

### USER

Director / Final Authority。

决定：

- Prompt 想表达什么；
- Reference 代表什么；
- 哪些内容被授权；
- Prompt 是否通过；
- 是否测试；
- 是否正式收录；
- 是否批准 Skill 修改。

### GPT

Architecture / Auditor / Second Reviewer。

重点：

- Skill 结构与边界；
- Semantic Addition 风险；
- 官方规则与示例区分；
- 证据质量；
- 冲突、重复立法、范围漂移；
- Skill Change 的审查。

### GROK

Practical Executor / NSFW Prompt Practitioner。

重点：

- 实际 Prompt 编写；
- NSFW Prompt 优化；
- 将明确需求翻译成可执行 wording；
- 实测与失败分析；
- 候选 Prompt 方案。

### GEMINI

Prompt Quality / Multimodal Researcher。

重点：

- Prompt wording；
- 多模态理解；
- Reference Mapping；
- 图片 / 视频 / Prompt 对照；
- 独立研究；
- Semantic Drift 检查；
- 替代表达方案。

未来加入的 AI：

先读取本文件和 `ROLE_MATRIX.md`，再由 User 指定具体角色。

新 AI 不应自行改变其他 AI 的职责，也不应自行取得 Skill 修改权限。

---

## 9. 冲突解决顺序

发生意见冲突时，按照：

1. **User 明确要求**
2. **适用的 MiniMax H3 官方规则**
3. **当前 Approved Skill**
4. **经过验证的项目研究 / 实测证据**
5. **模型推断**
6. **未经验证的直觉**

任何低等级证据都不能直接覆盖高等级规则。

---

## 10. Skill 修改权限

任何 AI 都可以：

- 提出问题；
- 提出 Candidate；
- 提供证据；
- 建议实验；
- 审查修改方案。

但：

**只有 User 可以批准 Skill Baseline 的改变。**

标准路径：

`Observation → Candidate → Evidence → Experiment（必要时） → Review → User Approval → Skill Change`

未经 User 批准，不得把研究发现直接写进 SKILL.md。

---

## 11. GitHub 文件的含义

### 根目录

保存项目级状态、决策、角色和冻结 Baseline 信息。

### `baseline/`

保存当前冻结 Skill 的镜像。

### `PROJECT/WORKSPACE-工作区/`

保存进行中的任务、草稿、实验、讨论和候选方案。

### `PROJECT/LIBRARY-正式库/`

保存已经由 User 确认、可以长期复用的正式成果。

其中：

`PROMPTS-正式提示词/`

保存正式确认的 H3 Prompt。

`SKILL_VERSIONS-技能版本/`

保存正式批准的 Skill 版本。

### `research/`

保存外部研究和证据。

### `experiments/`

保存实验记录和对照结果。

### `GPT/` / `GROK/` / `GEMINI/`

保存各 AI 的工作记录、分析或需要跨 AI 共享的内容。

---

## 12. 任务命名

任务名称最终由 User 决定。

AI 可以建议名称，但不能擅自重命名 User 已确认的任务。

具体命名规则见：

`PROJECT/WORKSPACE-工作区/TASK_NAMING-任务命名规范.md`

---

## 13. 新 AI 加入项目后的最小动作

不要先发表长篇架构意见。

先：

1. 阅读本文件；
2. 阅读 `STATUS.md`；
3. 阅读 `DECISIONS.md`；
4. 阅读 `ROLE_MATRIX.md`；
5. 阅读 `PROJECT/README.md`；
6. 确认当前 V1-5 Baseline；
7. 告诉 User：
   - 已理解项目用途；
   - 已确认当前 Baseline；
   - 已理解自己的角色；
   - 已理解 Skill 修改需要 User 批准。

然后等待 User 给出第一个具体任务。

---

## 14. 最重要的一句话

> **这个项目不是为了让 AI 制定越来越多的规则，而是为了让 AI 更准确地帮助 User 产出符合 MiniMax H3 官方规则、表达 User 已授权语义、并且经过实际验证的 Prompt。**
