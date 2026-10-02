**当前基线：** H3NSFW提示词技能skill第三版。Semantic Addition Gate = 优化权限唯一规范源。

# H3NSFW提示词技能skill第三版 — Strategy

**规范源：** SKILL.md 文首「第三版」硬规则；本文件仅摘要，冲突以 SKILL.md 为准。
**Semantic Addition Gate：** 成片新增语义须 USER/OFFICIAL/APPROVED SKILL/必要语言编译；禁止未授权 INFERENCE。
**收口：** 默认完整 H3 六段；内部状态不进成片；mpov 等 trigger 非默认。

对外名称：H3NSFW提示词技能skill第三版（内部：V13 baseline + 第三版最小集合）

Compile: Extract → Preserve → Normalize → Optimize → Recompile  
Instruction ≠ Prompt Content · PATCH ≠ OPTIMIZE · 硬 PRESERVE  
完整六段交付 · Runtime 不进成片 · Skill ≠ 项目资产  
LoRA = capability 框架，无来源不写 trigger；默认不输出 mpov  
POV = mode/angle/gaze/visible body/framing（通用摄影维）  
维护：先覆盖审计再 UPDATE-SKILL

# H3 NSFW Director — Strategy Lock

Portable summary so another AI (or a future session) does not depend on chat history.

## Product

- **Input:** rough NSFW request (pose, view, mood, refs).
- **Output:** paste-ready MiniMax H3 Ref2VA (or T2VA) prompt.
- **Users:** primary owner + other AIs reading this skill package only.

## Stack (Do Not Mix)

Includes **Source Material Ingestion** before Instruction Interpretation:

SOURCE MATERIAL (video / screenshots / foreign prompt) ≠ USER EDIT ≠ PROMPT CONTENT

Partial-source: extract only what was specified (pose only / camera only / face only / …). Never invent full-scene locks. Video for behavior ≠ automatic `<Video N>`.


```text
User message → Instruction Interpretation (content vs edit)
→ H3 Schema → Practical defaults → Project override → Final prompt
```

**User editing instructions are not prompt content.**

## Two Layers (Do Not Mix)

```text
H3 Schema (six sections + official reference semantics)
        ↓
Practical workflow defaults (overridable)
        ↓
Current project overrides
```

**Practical experience must not pollute H3 Schema.**

## H3 Schema (Hard)

1. Only six top-level sections, fixed order.
2. English body; original language only in `<d>` / lyrics / on-screen text.
3. Reference label semantic lock for the whole prompt.
4. `subject_definitions` = reference assets and roles — not target-only new action written as if it were locked reference.
5. `Picture` standalone only when it has independent frame/anchor duty.
6. `retention_analysis` only defined labels — no wild Man/Camera/Expression rows.
7. Audio role follows user intent; timbre-only ≠ reuse ≠ soundscape.
8. Video present ≠ automatic video editing.
9. Facial / Register / Conflict / Driver live **only** inside `detailed_description`.
10. Shot 1 has no timestamp; later shots `At 00:xx.000,`
11. Each Shot states **current** composition/state; prefer deltas vs prior shot without deleting required fields.

## Facial Performance Constraint Layer

Inside `detailed_description` only:

1. **UNIVERSAL** — identity lock, natural micro-motion, intensity fluctuation, cross-cut continuity, dynamic mouth (not locked open/closed). No % face panels.
2. **REGISTER** — affective baseline. Four Chinese presets are **shortcuts, not exhaustive**: 半推隐忍 / 强迫可怜 / 受用愉悦 / 主动浪.
3. **CONFLICT** — optional Primary/Secondary/Conflict/Control; omit when none.
4. **SHOT FACIAL DRIVER** — Shot1 establish; later continue+change; must state causal why.

When mood unclear: **suggest expression + dialogue delivery**, confirm, then write.

Never paste tier names / packaged / HARD GATES / U1 into H3 English body.

## Instruction Interpretation (P0)

- Classify user text: **prompt content** vs **editing instruction**.
- Edit verbs (修改/优化/改成/按 H3 优化, etc.) = operations, not in-video text.
- Semantic transform: "change X to Y" updates the owning H3 layer; never paste the chat phrase.
- **Edit scope:** narrowest layer (e.g. Shot 2 only).
- External short prompt → recompile to H3; existing H3 + edit → scoped change then full recompile.

## HARD GATES (core)

`Prompt = command what to DO, not a penalty sheet.`

- PIV: repeat positive insertion line in pose lock + shots + end as needed.
- Face: Constraint Layer; no blank default; no per-thrust open/close/blink machine; intensity fluctuates.
- Moans with lip-sync: continuous on-screen `<d>` string + soundscape bed.
- No ban-list as the main optimization tool.
- Pose/face: positive geometry only (e.g. head on pillow), not chat-style “not A, not B”.

## Practical Workflow Defaults

| Module | Default |
|--------|---------|
| Dual woman images | One Subject from both; next slot environment — not a second person |
| Environment image | Scene/bed reference |
| Third-person unspecified | External; prioritize heroine face |
| Pose lock | detailed_description / shots — not Subject reference lock |
| Dialogue | Short plot lines + 啊～喘串; delivery with Register; Audio timbre ≠ copy lines |
| LoRA | Optional; triggers only when user supplies model |
| 15s cuts | Prefer few angles (often 3); no default dense cutting |
| Skill edits | Confirm large changes; test expression/structure before commit; external shorts → six-section before archive |

## References

- Default single-woman: Picture 1 = woman, Picture 2 = background.
- Dual woman: P1+P2 same woman; background on next free slot.
- Never invent appearance or room furniture in text when refs define them.

## Poses

- Verified templates under `references/poses/做爱/…` and `切镜/…`.
- New `prompt.md` bodies only after user-confirmed takes.
- Prefer empty category folders over unverified long templates.

## Completion bar

1. Natural-language request → stable pasteable six-section prompt.
2. Face driven by Constraint Layer (not one fixed label face; not parameter panel).
3. Another AI can follow this package with no prior chat.


## Template freshness

- `references/poses/做爱/切镜/*` older verified files may lag the Constraint Layer; treat as archived until refreshed.
- Prefer writing from Schema + Constraint Layer + current user brief over stale intense-pleasure-only templates.


## NSFW Expression Compilation (Adult)

This skill owns adult facial/vocal compilation. Do not hollow out sex-plot expression.

- Plot → recommend Register + Conflict + delivery in plain language → user confirm → compile.
- 半推/抵抗台词 + body response → Primary reluctance + Secondary physical response + persistent conflict; lines broken between pants.
- 强迫感/可怜 → distress register + unstable control; no 15s frozen sad face.
- 偷感/怕发现 → tension + restraint + discovery triggers in Shot Driver.
- 主动浪 / 受用 → Register without forced conflict; intensity still fluctuates.
- In-video refusal or dirty lines in `<d>` are **content**; 修改/优化 chat phrases are **edit instructions**.


## Source recompiler engineering

- Observation ≠ Requirement  
- Specificity: SPECIFIC / ABSTRACT / UNSPECIFIED  
- KEEP/DISCARD negative extraction  
- Conflict priority: current user > project > source-selection > old prompt > observed > defaults  
- Temporal + causal extraction → Shot Driver  
- Cross-modal consistency (action↔face↔breath↔voice↔sound↔camera); NSFW: sex rhythm couples wet sound + vocal + face  
- Ambiguity → unspecified or ask  
- Compiler QA before deliver  
