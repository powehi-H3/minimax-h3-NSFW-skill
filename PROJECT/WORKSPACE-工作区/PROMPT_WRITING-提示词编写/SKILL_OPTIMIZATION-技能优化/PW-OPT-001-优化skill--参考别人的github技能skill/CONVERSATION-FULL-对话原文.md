# 任务：优化skill--参考别人的github技能skill

## 任务性质
SKILL_OPTIMIZATION（技能优化 / 外部 Skill 参考研究）

## 重要版本纪律
- V1-5 Frozen。
- 本任务是外部 Skill 研究与对照，不自动修改 V1-5。
- 原始对话资料必须完整保留，不得净化、删改、重写后冒充原文。
- GPT / Gemini / Grok 的分析意见必须与原始资料分离保存。
- 任何候选修改必须形成新版本，并经用户明确批准后才能修改 Skill。

---

# 对话原文

## 用户
https://github.com/benjiyaya/Minimax-H3-Prompt-AgentSkill看一下这个

## GPT
我看完了。这个仓库是一个**独立的 MiniMax H3 Prompt Agent Skill**，目前公开仓库的核心文件是 `SKILL.md` 和 `references/` 下的 3 个参考文件；仓库 README 说明它面向 Ref2VA、T2VA、I2VA、FL2VA、L2VA，并强调把粗略创意和媒体素材转换成结构化 H3 Prompt。

### 我先给你一个初步判断

它和我们现在的 **V1-5 Skill** 有明显不同的定位：

| 方面 | benjiyaya 这个 Skill | 我们的 V1-5 |
|---|---|---|
| 核心 | **Prompt Enhancer / Agent** | **Prompt 编写与优化 Skill** |
| 模式 | Ref2VA + Base MultiShot 多模式 | 目前重点是多参 / Ref2VA |
| 创意增强 | 明确强调 7 个 cinematic enhancement dimensions | 更强调用户语义、Reference、PATCH/PRESERVE |
| 输出 | 严格按 H3 格式 | 六段 H3 结构 |
| 参考素材 | 有明确 Reference / Mode 分类 | 有 Reference 职责与身份锁定纪律 |
| 修改纪律 | 相对简单 | 我们的 PATCH / PRESERVE / Semantic Addition 更严格 |
| 验证 | 有 Verification Checklist | 我们还有更完整的权限/变更纪律 |
| 研究价值 | **很高** | 可以作为外部参考 |

这个仓库尤其值得我们研究的不是“照搬它的 Skill”，而是它里面几个**很实用的工程化东西**。

例如它明确要求：

> **一个 shot 一个 dominant action**

并且要求镜头变化如果只是距离/角度变化，不要滥用 cut，而应该使用 camera motion。它还要求 timestamp 严格递增、Reference labels 在各 section 保持一致。

它的 `SKILL.md` 还把 **Camera Identity、Visual Texture、Pacing Arc、Character Detail、Spatial Geography、Continuity Progression、Sound Design** 七个增强维度明确列出来。

这些东西对我们**有参考价值**。

但我现在不会直接把它们加入 V1-5。

### 我建议先做“外部 Skill 对照研究”

也就是：

```text
PROJECT/
└── RESEARCH-研究/
    └── EXTERNAL-SKILLS-外部Skill/
        └── Minimax-H3-Prompt-AgentSkill/
            ├── SOURCE-INFO
            ├── SKILL-ANALYSIS
            ├── FORMAT-COMPARISON
            ├── USEFUL-PATTERNS
            └── ADOPTION-CANDIDATES
```

然后我们逐条判断：

**它有什么 → 我们有没有 → 如果没有 → 是否真的值得加入 → 是否会和 V1-5 冲突。**

而不是：

> “别人 Skill 有这个 → 我们 Skill 也加这个。”

这点非常重要，因为这个仓库自己的定位就是**production-grade prompt enhancement**，它明显有意加入大量 cinematic creative enhancement；这和我们现在强调的“用户要求优先、不要擅自增加语义”的方向存在潜在张力。

所以我认为它**值得研究，但暂时不要修改 V1-5**。

如果你同意，我下一步可以继续把它的 `references/` 三个文件也逐个读完，然后给你做一份**“它 vs 我们 V1-5”逐项对照表**，只做研究，不修改我们的 Skill。

---

## 用户
全部读完

## GPT
我已经把这个仓库的**主 Skill + 3 个 references 全部实际读取并核对过了**。其中 `creative-showcase.md` 很长，单次读取会被工具截断，所以我又用仓库搜索把后续 Pattern 4–9 的内容逐项核验了；没有把没读到的部分当成已读。

## 我现在已经掌握它的完整结构

### 1. `SKILL.md`

它的核心不是单纯“写 H3 格式”，而是：

**输入粗略创意 + 媒体素材 → 自动判断 H3 模式 → 做 cinematic enhancement → 编译成 H3 格式 → Verification。**

它支持：

- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

并把增强分成 **7 个维度**：

1. Camera Identity
2. Visual Texture
3. Pacing Arc
4. Character Detail
5. Spatial Geography
6. Continuity Progression
7. Sound Design

而且明确要求每个 Shot 具有 composition、camera motion、subject action、environment/lighting、sound cue、reference labels；其中**一个 Shot 一个 dominant action**是它的硬规则。

---

## 2. `ref2va-format.md`

这个文件是它最值得我们认真研究的部分。

它对 **Ref2VA 的 Reference Semantics** 定义得非常细：

### `<Subject N>`

是**可重复使用的视觉内容**：

- 人
- 动物
- 物体
- 环境
- 服装
- Props
- Style
- Action
- Expression
- Pose

而且可以组合多个 Reference。

### `<Picture N>`

非常重要：

> **只有当图片本身是具体 Frame / Composition Anchor 时，才使用 `<Picture N>`。**

如果图片只是：

- 人物参考
- 场景参考
- Style reference

就应该放到 `<Subject N>` 里，而不是把它当成 `<Picture N>`。

### `<Video N>`

代表：

- source video
- continuation source
- camera movement
- cuts
- rhythm
- temporal structure

但视频里面看到的人物内容，如果要作为视觉参考，仍然应该进入 `<Subject N>`。

### `<Audio N>`

区分：

- 直接复制 signal
- voice timbre
- music style
- dialogue
- SFX
- beat/rhythm

这个 Reference 职责划分非常清楚。

---

## 3. 它的 `retention_analysis` 也很值得借鉴

它不是简单写“参考图保持一致”。

而是固定使用：

### Visual

- `fully_preserved`
- `partially_preserved`
- `attribute_transfer`
- `weak_reference`

### Audio

- `fully_copy`
- `partially_copy`
- `reference`
- `weak_reference`

而且特别强调：

> 新增剧情、新动作、新背景，并不意味着 Reference fidelity 丢失。

这个概念和我们自己的 **PRESERVE / Semantic Addition** 非常接近，但它的表达更加直接。

---

# 4. 它对 Shot 的工程化要求非常强

它反复强调：

> **ONE dominant action per shot**

以及：

> 如果只是距离或角度改变，不应该 CUT，而应该使用 camera motion。

另外：

- Shot 1 没有 timestamp
- 后续 Shot 必须严格递增
- Cut 必须增加新信息
- 每个 Shot 必须有 Camera Motion
- 身份 Anchor 要跨 Shot 重复
- 状态变化必须连续

这些都是非常实用的**执行稳定性规则**。

---

# 5. Base MultiShot 也很完整

它对：

- T2VA
- I2VA
- FL2VA
- L2VA

分别规定了身体结构。

特别值得注意的是：

### FL2VA 默认单 Shot

它明确规定：

> **FL2VA DEFAULT TO A SINGLE SHOT**

只有用户明确要求，才拆成多个 Shot。

这是非常具体的模式级策略。

---

# 6. `creative-showcase.md` 才是这个 Skill 真正“聪明”的地方

它不是单纯规范文件，而是**大量高级 Prompt pattern 的案例库**。

我核对到至少这些 Pattern：

- Pattern 1：Long-Form Narrative Storytelling
- Pattern 2：Action Choreography
- Pattern 3：Wing Chun Street Fight
- Pattern 4：Samurai vs Ninja — Chambara Sword Duel
- Pattern 5：Anime Fight / SeeDance → H3 Conversion
- Pattern 6：Ninja Combo Indoor — Estate Infiltration
- Pattern 7：Ninja Silent Kill — Castle Assassination
- Pattern 8：Ninja Combo Out on Wooden — Temple Storm Chase
- Pattern 9：Contemporary Dance × Supernatural Blade Combat / Seedance → H3 Conversion

这些 Pattern 的共同价值不是具体剧情，而是**可迁移的 Prompt Engineering 方法**。

---

# 我认为对我们 V1-5 最有价值的东西

现在我不会修改我们的 Skill。

但研究价值已经很明确。

### A. Spatial Geography

它把空间关系写成：

> Screen Center-Deep → Front  
> Screen Right → Screen Left

甚至单独定义：

> `SPATIAL LAYOUT`

这对于我们以后处理**多人物、多参、复杂空间动作**非常有价值。

### B. Action Vectors

它会先定义：

```text
V1
V2
V3
```

然后把关键动作映射到 Shot。

这个特别适合复杂动作连续性。

### C. Progressive Continuity

它不是只说“保持一致”。

而是追踪：

- 头发越来越乱
- 衣服逐渐变化
- 灰尘累积
- 损伤累积
- 环境变化
- 情绪变化

这和我们现在的 **连续状态管理**非常接近。

### D. Camera Identity

它不只是：

> handheld

而是：

> 为什么是 handheld？  
> 手抖是什么程度？  
> autofocus 怎么表现？  
> exposure 是否变化？  
> framing 是否偶尔丢失？

这是非常好的**执行级 camera 描述方法**。

### E. Visual Texture

它把：

> cinematic

拆成：

- grain
- blur
- exposure
- contrast
- highlights
- skin tone
- lighting transitions

这比单纯堆“photorealistic / cinematic”强很多。

### F. Pacing Arc

它真正考虑：

```text
quiet → energetic
slow build → peak → settle
```

而不是简单罗列动作。

### G. Environmental Reactivity

这是我觉得非常值得我们观察的：

> 人物动作发生以后，环境也产生对应变化。

例如：

- 光线反射
- 地面反射
- 灯光闪烁
- 雾/尘
- 建筑损伤
- 环境声音

它让 Prompt 从“人物在背景里动”变成“人物和空间发生关系”。

---

# 但它有一个与我们 V1-5 很重要的区别

这个 Skill 的核心哲学是：

> **Creative Enhancement**

也就是用户给一个比较粗的想法，它主动帮用户丰富。

甚至 `SKILL.md` 明确把“Creative Enhancement”作为这个 Skill 的 distinctive value。

而我们 V1-5 更强调：

> **不要因为模型觉得这样更好，就擅自新增用户没有授权的语义。**

所以：

**不能直接把它的“Creative Enhancement”整体搬进我们的 Skill。**

但是可以把它当成：

> **外部 Pattern Library / Research Source**

从中研究**“怎么把已经授权的语义写得更可执行、更有空间感、更连续、更电影化”**。

这个区别非常关键。

---

## 所以我的结论

这个仓库**值得我们深入研究，而且价值不低**。

但现在最正确的动作不是修改 V1-5，而是：

```text
外部 Skill
     ↓
提取可迁移技术
     ↓
与 V1-5 对照
     ↓
区分：
  ① 我们已经有
  ② 它提供了更好的表达方法
  ③ 它提供了新的语义增强机制
     ↓
只有 ② 才有可能成为未来优化候选
③ 必须经过你的明确批准
```

尤其是 **Spatial Geography、Action Vectors、Progressive Continuity、Camera Identity、Visual Texture、Pacing Arc、Environmental Reactivity**，我建议作为后续重点研究对象。

**我目前不会把任何东西写入你 GitHub 的 V1-5 Skill。** 这次只是完成外部 Skill 的读取和分析。
