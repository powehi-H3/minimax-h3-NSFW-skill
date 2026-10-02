---
name: h3-nsfw-experiment-a-external-full
version: EXP-A-0.1
status: EXPERIMENTAL
source_strategy: External Skill full-reference adaptation
baseline_reference: V1-5 Frozen (read-only)
external_reference: benjiyaya/Minimax-H3-Prompt-AgentSkill
---

# PW-OPT-001 / A — 外部 Skill 全量参考实验版

> **实验资产，不是正式 Skill。**
> 
> 本文件用于测试：如果把外部 `Minimax-H3-Prompt-AgentSkill` 的完整工程思想尽可能完整地迁移到本项目，并与本项目现有 H3 NSFW 工作流结合，会得到什么结果。
>
> **V1-5 Frozen Baseline 不修改、不覆盖、不回写。**
>
> 本实验版的目的不是证明外部 Skill 正确，而是生成一个可独立运行、可由 Grok 编译 Prompt、并最终与 B 版进行同条件 H3 实测比较的实验对象。

## 1. 实验定位

A 版遵循“外部 Skill 全量参考”原则：

1. 优先采用外部 Skill 的工作流结构。
2. 采用其 Mode Classification、Parameter Gathering、Creative Enhancement、Per-shot Quality Bar、Camera Vocabulary、Continuity、Sound Design、Verification Checklist 等工程方法。
3. 保留本项目必须的 H3 NSFW Ref2VA 六段输出结构、Reference Mapping、成人角色约束、PATCH/PRESERVE/OPTIMIZE 等既有项目接口。
4. 不在 A 版阶段预判哪些外部方法最终应该进入正式 Skill。
5. 所有外部方法先作为实验变量存在。

## 2. Mode Classification

先判断 H3 模式：

- Reference assets / character / style / voice → Ref2VA
- 无参考素材、纯文字 → T2VA / Base MultiShot
- 首帧图 → I2VA
- 首尾帧 → FL2VA
- 末帧图 → L2VA

若素材职责不明确，先询问或建立最小 Reference Mapping 候选，不自行把参考图当成首帧/末帧。

## 3. Parameter Gathering

任务开始时收集或合理标记：

- duration_s
- aspect ratio
- shot count
- asset inventory
- Reference Mapping
- camera viewpoint
- dialogue / voiceover
- wardrobe / identity lock
- environment lock
- LoRA / trigger information（仅用户或已批准来源明确提供时）

缺失参数可以提出最小必要假设，但假设必须记录在实验任务中，不得伪装成用户要求。

## 4. External-Skill Creative Enhancement Layer

A 版完整保留外部 Skill 的七维增强思想：

### 4.1 Camera Identity

明确物理机位、镜头类型、POV/第三人称、镜头运动、镜头缺陷与视觉格式。

### 4.2 Visual Texture / Look

描述光线、色彩、对比度、材质、颗粒、数字/胶片质感等视觉属性。

### 4.3 Pacing Arc

允许根据完整时长规划能量变化、镜头节奏与情绪推进。

### 4.4 Character Detail

建立角色外观、服装、视觉识别锚点与跨 Shot 一致性。

### 4.5 Spatial Geography

显式规划前景 / 中景 / 背景、屏幕方向、移动向量、环境布局与遮挡关系。

### 4.6 Continuity Progression

跟踪人物状态、服装状态、道具状态、环境状态与情绪状态在时间轴上的连续变化。

### 4.7 Sound Design

规划 ambience、动作音效、对白、voiceover、diegetic music、non-diegetic music。

> **A 版特意不提前删除上述增强维度。**
> 它们正是本实验要验证的变量。

## 5. Per-Shot Quality Bar

每个 Shot 尽量明确：

- composition
- camera angle
- camera motion
- subject action
- environment / lighting
- sound cue
- Reference labels
- temporal state

### One Dominant Action

A 版采用外部 Skill 的明确规则：

> 每个 Shot 只有一个 Dominant Action。

如果用户要求连续动作，则通过多个 Shot / 时间节点表达，而不是在同一 Shot 中堆叠多个高频主动作。

## 6. Reference Semantics

Reference asset 的职责必须明确：

- `<Picture N>`：仅在其被定义为画面锚点时使用。
- `<Subject N>`：用于角色/主体身份与参考职责。
- `<Video N>`：视频参考。
- `<Audio N>`：声音参考。

多图时建立职责隔离，避免脸型、服装、环境、动作、风格之间发生无授权特征污染。

## 7. Ref2VA 六段编译接口

当任务为 Ref2VA 时，A 版最终仍使用项目六段接口：

1. `subject_definitions:`
2. `summary:`
3. `retention_analysis:`
4. `detailed_description:`
5. `overall_soundscape:`
6. `non_diegetic_music:`

### detailed_description

采用：

- 总体 style opener
- `[Shot 1]`
- `[Shot 2] At MM:SS.mmm`
- 后续严格递增时间戳
- End state / continuity

## 8. Camera Vocabulary

允许采用外部 Skill 的 Camera Vocabulary：

- Zoom In / Out
- Push In / Pull Out
- Pan L/R
- Truck L/R
- Tilt Up / Down
- Pedestal Up / Down
- Arc Shot
- Tracking Shot
- Static Shot
- Shake Slightly / Strongly
- POV
- Roll CW / CCW

需要同时表达自然语言中的：

- motion type
- amplitude
- speed

## 9. Continuity

A 版强调 Progressive Continuity：

- 物理状态应在 Shot 之间延续。
- 角色身份、服装、道具、环境变化必须具有时间因果。
- 如果某个状态在 Shot 1 产生，在 Shot 2 仍存在时应明确保留。
- 不允许无原因瞬间恢复或消失。

## 10. Narrative Creative Enhancement

A 版保留外部 Skill 的 Pacing Arc / narrative enhancement 思路，但实验任务必须区分两种情况：

### 用户要求创意

可以主动增强剧情张力、节奏、镜头推进与视觉潜台词。

### 用户已经给定完整剧情

实验仍记录外部 Skill 的增强行为，但必须在实验记录中标记其是否产生 Semantic Drift。

这正是 A/B 实验要验证的重点之一。

## 11. Sound Design

A 版采用外部 Skill 的声音规划：

- ambience
- physical action sounds
- dialogue
- voiceover
- diegetic music
- non-diegetic music

必须区分角色能够听到的声音与非叙事背景音乐。

## 12. Output Discipline

最终 Prompt 应保持 H3 可执行格式。

内部实验标签（例如 EXP-A、TARGET、CHANGE、PRESERVE、DEPENDENCIES）不得混入最终成片 Prompt，除非实验任务明确要求输出调试版。

## 13. 实验记录要求

每个使用 A 版生成的真实任务，应记录：

- 原始用户需求
- Reference Mapping
- A 版采用的外部增强项
- 生成的最终 Prompt
- H3 实测结果
- 成功/失败
- 语义漂移
- 人物一致性
- 空间关系
- 动作执行
- 连续性
- 镜头稳定性
- 信息密度
- Debug 难度

## 14. 与正式 Skill 的隔离

禁止：

- 修改 `baseline/` 下的 V1-5
- 修改正式 Skill
- 将 A 版研究结果自动写入 DECISIONS
- 将 A 版候选自动升级为 Universal Rule
- 用 A 版结果覆盖 B 版

只有 A/B 实测完成、结果分析完成并得到用户明确批准后，才允许讨论正式 Skill 是否升级。

## 15. A 版实验假设

本实验主要验证：

> 外部 Skill 的完整增强体系，是否能够在我们的 H3 NSFW Prompt 工作流中带来可测量的实际收益，还是会因为提示词长度、注意力竞争与语义扩张产生负面影响。

**当前状态： EXP-A-0.1 / 未实测 / 未验证 / 不进入正式 Skill。**
