# PW-OPT-001｜B 版优化清单｜Gemini Review Request

> **用途：** 本文件用于让 Gemini 直接读取 GPT 针对 Version B（AI 推荐优化版）的独立研究与审核请求。
>
> **当前状态：** EXPERIMENTAL / REVIEW REQUEST
>
> **重要：** 不修改 V1-5 Frozen Baseline；不修改 A 版；不自动升级任何 Candidate 为正式 Skill Rule。

---

## 1. 当前实验结构

PW-OPT-001 已确定采用两条完全独立的实验路线：

- **A：External Skill Full Reference**
  - 尽可能完整参考 `benjiyaya/Minimax-H3-Prompt-AgentSkill`
- **B：AI Recommended Optimization**
  - GPT + Gemini 独立重新设计
  - 不直接复制 A 的具体实现

两者最终交给 Grok，在相同任务、相同素材、相同参数下分别生成 Prompt A / Prompt B，再进行 H3 实测对比。

正式 V1-5 Baseline 继续 FROZEN。

---

# 2. GPT 对外部 Skill 的重新研究结论

GPT 重新检查了外部仓库的主要结构与参考资料，包括：

- `SKILL.md`
- `references/ref2va-format.md`
- `references/base-multishot-format.md`
- `references/creative-showcase.md`

重新核对后，GPT 判断外部 Skill 的价值并不只在“六段提示词格式”，还包括：

- Mode Detection
- Reference Role Mapping
- Retention Analysis
- Timestamp / Continuity
- Shot-level orchestration
- Camera vocabulary
- Sound design
- Verification
- Output compilation discipline
- Creative Enhancement 的独立定位

因此 B 版不应该只做原先 Gemini 提出的 5 项执行强化，而应进一步研究外部 Skill 的工程层机制。

---

# 3. B 版 GPT 独立优化候选清单

以下全部是 **Review Candidates**，不是已经批准的规则。

## B-01｜H3 Mode Detection Layer

根据输入资产判断：

- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

并判断输入图片属于：

- character/reference asset
- environment/style reference
- first frame
- last frame
- storyboard/keyframe

如果模式存在歧义，应询问最小必要问题，不应自行猜测。

**重点审核：** 是否值得成为 B 的统一前置层？

---

## B-02｜Reference Role Mapping Layer

每个输入素材明确职责：

- Identity
- Clothing
- Environment
- Composition
- Motion
- Camera
- Audio
- Style
- Frame Anchor

Reference 是有范围的约束，不是全局风格污染源。

**重点审核：** 与 V1-5 现有 Reference Semantics 的边界如何划分？

---

## B-03｜Reference Conflict Resolver

当多个 Reference 对同一属性存在冲突时，不自动融合。

建立：

`Reference Conflict Table`

例如：

| Feature | P1 | P2 | P3 | Final Authority |
|---|---|---|---|---|
| Face | ✓ | — | — | P1 |
| Clothing | — | ✓ | — | P2 |
| Environment | — | — | ✓ | P3 |

没有用户指定优先级时，不自行猜测。

**重点审核：** 是否为真正新增能力？

---

## B-04｜Retention Analysis 2.0

将 retention_analysis 从单纯描述性检查升级为 Reference Retention Matrix：

- identity
- appearance
- clothing
- pose
- motion
- environment
- audio
- camera
- frame relationship

状态可区分：

- fully_preserved
- partially_preserved
- attribute_transfer
- weak_reference
- newly_generated

**重点审核：** 是否会与 V1-5 重复？如果重复，应如何避免冗余？

---

## B-05｜Temporal State Ledger

每个 Shot 记录：

- subject state
- pose state
- object state
- environment state
- camera state
- audio state
- newly introduced state
- carried-over state

核心思想：

`Shot N = Previous State + Explicit Change`

防止跨 Shot 状态丢失。

**重点审核：** 是否值得独立成为 B 的状态层？

---

## B-06｜One Dominant Action per Shot

每个 Shot 只允许一个 Dominant Action。

可以存在：

- secondary micro-actions
- facial reactions
- breathing
- subtle hand movement

但不得出现第二个同等级主动作。

**状态：** 高优先级 Candidate。

---

## B-07｜Action Vector Layer

将动作拆成：

- direction
- amplitude
- frequency
- contact
- trajectory
- speed
- acceleration/deceleration
- start state
- end state

但必须遵循：

> Minimum Sufficient Physical Description

不是 Maximum Physical Description。

**重点审核：** 如何避免 Prompt 过长导致 Attention Overcrowding？

---

## B-08｜Camera Kinematics Layer

Camera 独立于主体动作。

建立独立 Camera State：

- camera type
- viewpoint
- framing
- movement
- amplitude
- speed
- stabilization
- depth behavior

避免将 Camera Transform 与主体动作混在同一语义句中。

**重点审核：** 是否与外部 Skill 的 Camera Vocabulary 形成有效工程增强？

---

## B-09｜Spatial Geography Layer

根据场景复杂度自适应：

- Level 0：普通位置关系
- Level 1：foreground / midground / background
- Level 2：空间比例、方向、遮挡关系
- Level 3：复杂多主体 3D spatial graph

不要强制所有 Prompt 使用数字比例。

**重点审核：** 自适应等级是否优于外部 Skill 的固定空间描述？

---

## B-10｜Adaptive Prompt Density

根据任务复杂度动态决定 Prompt 信息密度。

简单任务 → 短。

复杂多主体 → 增加 spatial / continuity / camera anchors。

高难动作 → 增加 action vectors。

Dialogue-heavy → 增加 timing / speech structure。

目标：

> Minimum Sufficient Information / Avoid Attention Overcrowding

**重点审核：** 是否应成为 B 的核心原则之一？

---

## B-11｜Creative Enhancement Gating

Creative Enhancement 不自动执行。

建议模式：

### Mode A
用户给定完整故事 → 严格执行。

### Mode B
用户要求创意帮助 → 可以 Narrative Enhancement。

### Mode C
用户只给粗略想法 → AI 可以提出候选，但必须标记为 AI Proposal。

AI Proposal 未经用户确认，不得进入最终 Prompt。

---

## B-12｜Narrative Creative Enhancement

保留外部 Pacing Arc 的思想，但彻底从 Prompt Compiler 解耦。

流程：

`User Idea → Narrative Brainstorm → Candidate A/B/C → User Selects → Prompt Compilation`

**重点审核：** 是否作为独立前期创意模式，而不是 Skill 默认规则。

---

## B-13｜Environmental Reactivity Controller

外部 Skill 的环境动态不默认加入。

默认：

`Environmental Reactivity = OFF`

只有以下情况才启用：

1. 用户明确要求；
2. 环境反应是剧情核心；
3. 环境反应确实有助于动作执行。

**重点审核：** 是否保留为可选实验能力？

---

## B-14｜Visual Texture Budget

对：

- grain
- palette
- exposure
- cinematic texture
- volumetric lighting

设置预算。

Reference 已经提供视觉风格时，减少 Prompt 中的重复视觉修饰。

无 Reference 时才补必要参数。

目标：减少 Style Drift。

**重点审核：** 是否值得进入 B，还是保持纯实验项？

---

## B-15｜Camera / Subject / Environment 三层解耦

Prompt 内部建立：

`CAMERA`

`SUBJECT ACTION`

`ENVIRONMENT`

三层允许互相关联，但不要混写成单一长句。

目标：

- Debug
- PATCH
- A/B Test
- 单独修改 Camera
- 单独修改 Action
- 单独修改 Environment

---

## B-16｜PATCH Architecture

正式支持局部 Patch：

- PATCH_CAMERA
- PATCH_ACTION
- PATCH_CHARACTER
- PATCH_ENVIRONMENT
- PATCH_AUDIO
- PATCH_TIMING
- PATCH_REFERENCE

只改变用户指定部分。

---

## B-17｜Minimal Semantic Change

任何 PATCH 都必须遵守：

> 只修改用户指定部分。

例如用户只说：

“镜头从 Static 改成 Slow Push In。”

则 Character / Action / Environment / Sound / Reference 全部保持不变。

**重点审核：** 是否值得成为 B 的核心修改纪律？

---

## B-18｜Shot-Level Verification

每个 Shot 输出前检查：

1. Dominant Action 是否唯一；
2. Subject 是否正确；
3. Reference 是否正确；
4. Camera 是否正确；
5. Environment 是否正确；
6. State 是否连续；
7. Timestamp 是否合法；
8. 是否引入未经授权的新剧情。

---

## B-19｜Global Verification

最终 Prompt 输出前检查：

### Reference
- labels consistent
- no invented references
- roles consistent

### Timeline
- timestamps increasing
- duration valid
- state continuity

### Camera
- camera/action separation

### Semantic
- no unauthorized plot
- no accidental creative invention

### Output
- exact format
- required fields
- no extra commentary

---

## B-20｜Debug Trace

每个 Prompt 元素能够追溯来源：

- User Requirement
- Reference
- V1-5 inherited rule
- External Skill research
- AI recommendation
- User-approved creative addition

目标：H3 出现问题时可以追溯“这个东西是谁/什么机制加进去的”。

---

## B-21｜Evidence / Candidate Status

新增机制状态：

`RESEARCH`

`EXPERIMENTAL`

`VALIDATED`

`PROPOSED`

`FROZEN`

防止实验技巧自动升级成永久规则。

---

## B-22｜A/B Experimental Isolation

B 不读取 A 的最终优化规则作为自身约束。

B 的设计输入：

- V1-5
- External Skill source
- GPT / Gemini independent analysis
- User requirements

A/B 结果在测试前不得互相污染。

---

## B-23｜Mode-Specific Optimization

不要让所有 H3 模式使用同一套增强机制。

分别考虑：

- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

例如：

Reference Mapping 对 Ref2VA 更重要；
Frame Continuity 对 I2VA / FL2VA 更重要；
Multishot Timeline 对 T2VA 更重要。

**重点审核：** 是否值得成为 B 的模式分流机制。

---

## B-24｜Reference Asset Wiring Awareness

Reference Mapping 与物理 Input Socket 顺序分离。

例如：

Picture 1 → Image Input 1
Picture 2 → Image Input 2

同时：

“Picture 2 负责锁脸”

只是 Semantic Role，不代表它可以改变物理输入顺序。

---

## B-25｜Output Compiler Layer

建议将 B 的内部流程分层：

`IDEATION`

↓

`SEMANTIC PLAN`

↓

`REFERENCE MAP`

↓

`SHOT PLAN`

↓

`PHYSICAL EXECUTION PLAN`

↓

`H3 FORMAT COMPILER`

↓

`VERIFICATION`

避免：

`User sentence → Prompt`

---

# 4. B 版总原则

B 最终应遵循：

> 用户语义优先
>
> Reference 约束优先
>
> H3 可执行性优先
>
> 最小充分描述
>
> 创意与编译解耦
>
> Camera / Action / Environment 解耦
>
> 实验机制与正式规则解耦
>
> 所有新增能力必须可追溯、可测试、可回滚

---

# 5. 请 Gemini 进行二次审核

请不要直接照单全收。

请逐项给出：

`ACCEPT`

`MODIFY`

`REJECT`

`RESEARCH ONLY`

重点审核：

- B-07 Action Vector
- B-09 Spatial Geography
- B-10 Adaptive Prompt Density
- B-11 / B-12 Creative Enhancement
- B-13 Environmental Reactivity
- B-14 Visual Texture
- B-16 / B-17 PATCH Architecture
- B-20 Debug Trace
- B-23 Mode-Specific Optimization
- B-25 Output Compiler Layer

最终输出：

## B Version Recommended Final Checklist

即：经过 Gemini 二次审核后，B 版真正应该实现哪些项目。

这一步仍然只是 B 版设计审核：

- 不修改 V1-5
- 不修改 A
- 不自动升级 Candidate 为正式 Skill Rule
- 不把 Gemini 的审核意见直接视为最终用户决策

Gemini 完成审核后，请将结果写成独立意见返回，由 GPT 负责后续归档和 B 版实现。
