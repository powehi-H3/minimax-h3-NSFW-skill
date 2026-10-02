# PW-OPT-001｜Version B — AI 推荐优化版｜GPT 独立研究清单（原始稿）

> 状态：GPT 独立研究稿 / 待 Gemini 二次审核
> 正式 V1-5 Baseline：FROZEN
> A 组：外部 Skill 全量参考版
> B 组：GPT + Gemini 独立重构优化版
> A/B 完全独立，不互相覆盖、不反向污染正式 Skill。
> 最终需由 Grok 基于相同任务分别生成 Prompt A / Prompt B，再进行 H3 实测对比。

## B-01｜H3 Mode Detection Layer

优先级：核心

外部 Skill 首先根据输入资产判断：
- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

B 版建议保留这个思想，但不要机械照搬。

设计目标：
1. 根据用户素材自动判断生成模式；
2. 判断图片是 character/reference asset、environment/style reference、first frame、last frame、storyboard/keyframe；
3. 如果存在模式歧义，优先询问最小必要问题；
4. 不允许因为素材存在就自动把图片当成 frame anchor。

理由：外部 Skill 明确区分 reference asset 与 concrete frame anchor，这个概念值得吸收。

## B-02｜Reference Role Mapping Layer

优先级：核心

保留并进一步强化 V1-5 已有的 Reference Semantics。

每一个输入素材必须拥有明确职责：
- Identity
- Clothing
- Environment
- Composition
- Motion
- Camera
- Audio
- Style
- Frame Anchor

重点：一张图片可以承担多个角色，但必须显式定义。

同时禁止：因为图片里出现某个特征，就自动把该特征扩展到其他角色/其他区域。

Reference = 有范围的约束，不是全局风格污染源。

## B-03｜Reference Conflict Resolver

优先级：核心新增

当 Picture 1 锁脸、Picture 2 锁服装、Picture 3 锁环境，但三者出现冲突时，不能直接融合。

应该先建立 Reference Conflict Table。

示例：

| Feature | P1 | P2 | P3 | Final Authority |
|---|---|---|---|---|
| Face | ✓ | — | — | P1 |
| Hairstyle | ✓ | ✓ | — | User mapping |
| Clothing | — | ✓ | — | P2 |
| Environment | — | — | ✓ | P3 |

如果用户没有指定冲突优先级，不自行猜测。

## B-04｜Retention Analysis 2.0

优先级：核心

外部 Skill 的 retention_analysis 值得保留，但 B 版应该把它从“描述性检查”升级成 Reference Retention Matrix。

每个主体记录：
- identity
- appearance
- clothing
- pose
- motion
- environment
- audio
- camera
- frame relationship

并区分：
- fully_preserved
- partially_preserved
- attribute_transfer
- weak_reference
- newly_generated

注意：新增剧情/动作本身不是 reference loss。

## B-05｜Temporal State Ledger

优先级：核心

外部 Skill 的 timestamp / continuity 机制值得吸收，但 B 版不应该只记录 Shot 时间。

应该建立 Temporal State Ledger。

每一个 Shot 记录：
- subject state
- pose state
- object state
- environment state
- camera state
- audio state
- newly introduced state
- carried-over state

例如：
Shot 1：State A
Shot 2：State A + Change B
Shot 3：State A + B + Change C

这样可以避免 Shot 2 突然忘掉 Shot 1 已经建立的状态。

## B-06｜One Dominant Action per Shot

优先级：核心

正式加入 B。

每个 Shot 只能存在一个 Dominant Action。

允许存在：
- secondary micro-actions
- facial reactions
- breathing
- subtle hand movement

但不得存在第二个同等级主动作。

如果出现 Action A + Action B + Camera Transition，应拆成：
- Shot 1 → Action A
- Shot 2 → Action B
- Shot 3 → Camera Transition

目的：降低 H3 并行动态冲突。

## B-07｜Action Vector Layer

优先级：核心

把抽象动作转换成：
- direction
- amplitude
- frequency
- contact
- trajectory
- speed
- acceleration/deceleration
- start state
- end state

但增加一条重要限制：不要为了物理精确而无限增加文字。

B 版应该追求 Minimum Sufficient Physical Description，而不是 Maximum Physical Description。

只描述能够改变模型执行结果的物理信息。

## B-08｜Camera Kinematics Layer

优先级：核心

Camera 必须独立于主体动作。

建议单独建立 Camera State，包括：
- camera type
- viewpoint
- framing
- movement
- amplitude
- speed
- stabilization
- depth behavior

角色动作单独写。

避免类似“camera moves closer as the character moves closer”这种可能产生语义耦合的句式。

## B-09｜Spatial Geography Layer

优先级：高

吸收外部 Skill 的 Spatial Geography，但不强制每个 Prompt 都使用 2/3、1/3 等数字。

应该根据复杂程度选择：
- Level 0：普通位置关系。
- Level 1：foreground / midground / background。
- Level 2：明确空间比例、方向、遮挡关系。
- Level 3：复杂多主体 3D spatial graph。

Spatial Detail 应该按场景复杂度自适应。

## B-10｜Adaptive Prompt Density

优先级：非常重要

不要固定要求“Prompt 越详细越好”。

应该根据任务复杂度动态决定 Prompt 信息密度：
- 简单任务 → 短。
- 复杂多主体 → 增加 spatial / continuity / camera anchors。
- 高难动作 → 增加 action vectors。
- Dialogue-heavy → 增加时间轴和 speech timing。

建立 Prompt Density Budget，目标是避免 Attention Overcrowding。

## B-11｜Creative Enhancement Gating

优先级：核心

外部 Skill 的 Creative Enhancement 不应该自动执行。

建立明确 Gate：

Mode A：USER-SPECIFIED STORY → 严格执行。

Mode B：USER REQUESTS CREATIVE HELP → 可以进行 Narrative Creative Enhancement。

Mode C：USER GIVES ROUGH IDEA → 可以提出候选创意，但必须区分 User Requirement 与 AI Proposal。

不得把 AI Proposal 自动写成用户要求。

## B-12｜Narrative Creative Enhancement

优先级：可选模式

保留外部 Skill 的 Pacing Arc 思想，但彻底从 Prompt Compiler 中解耦。

流程：
User Idea
↓
Narrative Brainstorm
↓
Candidate A / B / C
↓
User Selects
↓
Prompt Compilation

只有用户确认后，创意才进入最终 Prompt。

## B-13｜Environmental Reactivity Controller

优先级：实验功能

外部 Skill 喜欢增加 curtain movement、lighting changes、environmental motion、object reaction。

B 版不默认加入。

建立：Environmental Reactivity = OFF

除非：
1. 用户明确要求；
2. 环境反应是剧情核心；
3. 环境反应对动作执行有实际帮助。

否则保持 Background Stability。

## B-14｜Visual Texture Budget

优先级：实验功能

外部 Skill 的 Visual Texture（grain、palette、exposure、cinematic texture、volumetric lighting）不能无限堆叠。

B 版应该优先 Reference。Reference 已经明确视觉风格时少写文字；没有 Reference 时才补必要视觉参数。

目标：避免 Style Drift。

## B-15｜Camera / Subject / Environment 三层解耦

优先级：核心

Prompt 内部建立三个独立层：
- CAMERA
- SUBJECT ACTION
- ENVIRONMENT

三层之间允许产生关系，但不能混成一个长句。

这样方便：
- Debug
- PATCH
- A/B Test
- 单独修改 Camera
- 单独修改 Action
- 单独修改 Environment

## B-16｜PATCH Architecture

优先级：核心

B 版应该正式支持 PATCH。

当用户要求“只改镜头”时，不能重新生成整个 Prompt。

应该：
- PATCH_CAMERA
- PATCH_ACTION
- PATCH_CHARACTER
- PATCH_ENVIRONMENT
- PATCH_AUDIO
- PATCH_TIMING
- PATCH_REFERENCE

目标：降低修改造成的语义漂移。

## B-17｜Minimal Semantic Change

优先级：核心

任何 PATCH 只修改用户指定部分。

例如用户：“镜头从 Static 改成 Slow Push In。”

那么 Character、Action、Environment、Sound、Reference 全部保持不变。

这是 B 版非常重要的纪律。

## B-18｜Shot-Level Verification

优先级：核心

每一个 Shot 在生成后检查：
- Dominant Action 是否唯一；
- Subject 是否正确；
- Reference 是否正确；
- Camera 是否正确；
- Environment 是否正确；
- State 是否连续；
- 时间戳是否合法；
- 是否引入未经授权的新剧情。

## B-19｜Global Verification

优先级：核心

最终 Prompt 输出前进行全局检查：

Reference：labels consistent；no invented references；roles consistent。

Timeline：timestamps increasing；duration valid；state continuity。

Camera：camera/action separation。

Semantic：no unauthorized plot；no accidental creative invention。

Output：exact format；required fields；no extra commentary。

## B-20｜Debug Trace

优先级：新增

B 版应该能够追溯某个 Prompt 元素来自：
- User Requirement
- Reference
- V1-5 inherited rule
- External Skill research
- AI recommendation
- User-approved creative addition

这样出现 H3 问题时，可以反查：“这个东西是谁加进去的？”

## B-21｜Evidence / Candidate Status

优先级：核心

B 版内部所有新增机制都应该带状态：
- RESEARCH → 尚未验证
- EXPERIMENTAL → 正在 A/B 测试
- VALIDATED → 多次测试有效
- PROPOSED → 建议进入正式 Skill
- FROZEN → 正式 Skill 已采用

这样防止“一个实验技巧 → 自动变成永久规则”。

## B-22｜A/B Experimental Isolation

优先级：核心

B 版本身必须声明：不读取 A 版的最终优化规则作为自身约束。

B 的研究输入只能来自：
- V1-5
- 外部 Skill 原始资料
- Gemini / GPT 独立分析
- 用户明确要求

A/B 结果在测试阶段之前不得互相污染。

## B-23｜Mode-Specific Optimization

优先级：高

B 版不要强迫所有 H3 模式使用同一套增强机制。

分别考虑：
- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

因为外部 Skill 本身也是按照这些模式分别定义输出结构的。

例如：
- Reference Mapping 对 Ref2VA 极其重要。
- Frame Continuity 对 I2VA / FL2VA 更重要。
- Multishot Timeline 对 T2VA 更重要。

## B-24｜Reference Asset Wiring Awareness

优先级：高

外部 Skill 明确要求：ASSETS 顺序必须与物理输入 socket 顺序一致。

B 版应该保留这个工程意识：
- Image 1 → 第一个 Image Input
- Image 2 → 第二个 Image Input
- ……

同时把 Reference Mapping 和 Physical Wiring Order 分开。

也就是说：“Picture 2 负责锁脸”不等于“Picture 2 可以改变 Picture 1 的物理输入位置”。

## B-25｜Output Compiler Layer

优先级：核心

最终应该分成：
IDEATION
↓
SEMANTIC PLAN
↓
REFERENCE MAP
↓
SHOT PLAN
↓
PHYSICAL EXECUTION PLAN
↓
H3 FORMAT COMPILER
↓
VERIFICATION

而不是直接：用户一句话 → 生成 Prompt。

## B-26｜B版最重要的总体原则

B 版最终应当遵循：
- 用户语义优先
- Reference 约束优先
- H3 可执行性优先
- 最小充分描述
- 创意与编译解耦
- Camera / Action / Environment 解耦
- 实验机制与正式规则解耦
- 所有新增能力必须可追溯、可测试、可回滚。

## Gemini 审核要求

请 Gemini 重点审核，不要直接照单全收。

逐项给出：
- ACCEPT
- MODIFY
- REJECT
- RESEARCH ONLY

尤其重点审核：
- B-07 Action Vector
- B-09 Spatial Geography
- B-10 Adaptive Prompt Density
- B-11/B-12 Creative Enhancement
- B-13 Environmental Reactivity
- B-14 Visual Texture
- B-16/B-17 PATCH Architecture
- B-20 Debug Trace
- B-23 Mode-Specific Optimization
- B-25 Output Compiler Layer

最终给出：B Version Recommended Final Checklist，即经过 Gemini 二次审核后，B 版真正应该实现哪些项目。

## 本稿的实验边界

这一步仍然只是 B 版设计审核：
- 不修改正式 V1-5；
- 不直接修改 A；
- 不自动把任何 Candidate 升级成正式 Skill Rule；
- B 版最终需经独立审核、实验和 Grok 同任务 Prompt A / Prompt B 对比后，再决定是否进入后续阶段。

## GPT 当前判断

本次重新检查后，B 版核心不应只局限于 Gemini 最初归纳的“五大升级点”。外部 Skill 真正值得吸收的，还包括模式分流、Reference 角色映射、Retention、时间状态、输出编译、验证以及可调试性。外部仓库把这些能力分散在主 Skill 与 reference 文件中，而不是只有 cinematic dimensions。

尤其值得保留的工程思想包括：严格输出契约、时间戳、Reference label 一致性、每 Shot 一个 dominant action、Camera motion 的 type/amplitude/speed，以及输出前 Verification。

因此，本稿交给 Gemini 做一次独立筛选；Gemini 返回最终清单后，再把 B 版真正写入实验目录。