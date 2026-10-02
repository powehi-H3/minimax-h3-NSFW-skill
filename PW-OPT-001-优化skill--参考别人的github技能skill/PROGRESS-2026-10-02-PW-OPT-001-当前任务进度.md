# PW-OPT-001｜当前任务进度

> 任务：**优化skill--参考别人的GitHub技能skill**
>
> 本文件属于 PW-OPT-001 主任务，不是独立新任务。

## 当前状态

**IN PROGRESS / EXPERIMENTAL — B SPECIFICATION IMPLEMENTED**

正式 V1-5 Baseline：**FROZEN**

本任务中的实验路线不会直接修改正式 Skill。

---

## 实验路线

### A｜External Skill Full Reference（外部 Skill 全量参考版）

状态：🟡 实验资产路线

目标：尽可能完整参考外部 `benjiyaya/Minimax-H3-Prompt-AgentSkill`，形成独立实验版本。

原则：
- 不修改 V1-5
- 不吸收 B 的优化意见
- 独立保存、独立测试

### B｜AI Recommended Optimization（AI 推荐优化版）

状态：🟢 **Gemini 二次审核完成 / B 实验 Skill 规范已落地 / 尚未 H3 验证**

B 已完成 GPT 第一轮候选 → Gemini 二次逻辑审核 → GPT 落地实验规范的闭环。

B 的设计规范已写入：

`SKILL_OPTIMIZATION-技能优化/EXPERIMENTS-技能优化对比实验/B-AI-RECOMMENDED-OPTIMIZATION-AI推荐优化版/SKILL-B.md`

配套文件：
- `B-ARCHITECTURE.md`
- `B-VERIFICATION.md`
- `README.md`

---

## 已完成

- [x] 确定 PW-OPT-001 任务范围：研究外部 GitHub Skill，并形成独立优化实验。
- [x] 确定 V1-5 Baseline 保持 FROZEN。
- [x] 确定 A/B 双路线实验结构。
- [x] 建立 A/B 实验隔离原则。
- [x] 完成外部 Skill 的第一轮结构与机制分析。
- [x] 完成 GPT B-01 ～ B-26 独立工程候选清单。
- [x] Gemini 完成 B-01 ～ B-26 二次逻辑审核。
- [x] 形成 Gemini Recommended Final Checklist。
- [x] 根据 Gemini 审核结果完成 B 实验 Skill 规范。
- [x] 建立 B Compiler Architecture。
- [x] 建立 B Verification Contract。

## 当前进行中

- [ ] 完成 / 审核 A 版实验 Skill。
- [ ] Grok 读取 A / B 实验资产并使用同一原始任务生成 Prompt A / Prompt B。

## 下一阶段

- [ ] 使用相同素材、画幅、时长及输入条件进行 H3 A/B 实测。
- [ ] 记录统一指标。
- [ ] 分析 A/B 实测结果。
- [ ] 形成 PW-OPT-001 最终实验结论。
- [ ] 用户最终批准后，才考虑是否进入未来正式 Skill Candidate / 正式版本。

---

## Gemini 二次审核后的 B 核心收敛

- B-01 Mode Detection：保留为前置层。
- B-02 Reference Role Mapping：保留。
- B-03 Conflict Resolver：内部 IR 处理，不向 H3 输出冲突表。
- B-04 Retention Analysis 2.0：作为 Pre-flight，不写入最终 Prompt。
- B-05 Temporal State Ledger：保留。
- B-06 One Dominant Action：保留。
- B-07 Action Vector：保留，并执行 Minimum Sufficient Physical Description。
- B-08 Camera Kinematics：保留并与主体动作解耦。
- B-09 Spatial Geography：默认 L0-L2；L3 = RESEARCH ONLY。
- B-10 Adaptive Prompt Density：保留为核心原则。
- B-11/B-12 Creative Enhancement：Gate + 独立 Ideation 阶段。
- B-13 Environmental Reactivity：默认 OFF。
- B-14 Visual Texture Budget：Reference 优先，压缩冗余修饰。
- B-15 Camera / Subject / Environment：三层解耦。
- B-16/B-17 PATCH + Minimal Semantic Change：保留。
- B-18/B-19 Shot + Global Verification：保留。
- B-20 Debug Trace：内部日志，最终 Payload 剥离。
- B-21 Evidence / Candidate Status：保留生命周期治理。
- B-22 A/B Isolation：保留。
- B-23 Mode-Specific Optimization：保留。
- B-24 Reference Asset Wiring：保留语义映射与物理 socket 顺序分离。
- B-25 Output Compiler Layer：保留多阶段编译管线。
- B-26 Overall Charter：作为 B 总原则。

---

## 重要隔离规则

### 1. 不污染正式 Skill

A/B 实验结果不能直接修改 V1-5。

### 2. A/B 互不污染

A 不读取 B 的最终结论作为自身规则；B 也不把 A 的实验实现直接当作自身规则。

### 3. 实验结果不是正式规则

即使某项实验表现优秀，也只能先标记为 `VALIDATED / CANDIDATE`，必须经过用户最终批准才能进入正式 Skill。

### 4. B 已完成“设计规范落地”，但未完成“实验验证”

B Skill 已写入实验目录，但尚未通过 Grok 同场 A/B Prompt 生成及 H3 实测。因此当前状态不能标记为 VALIDATED 或 FROZEN。

### 5. Grok 介入点

Grok 的主要实验职责现在正式进入：

`A Skill → Prompt A`

`B Skill → Prompt B`

然后在相同测试条件下进行对照。

---

## 当前任务链

```text
PW-OPT-001
    │
    ├── A：External Skill Full Reference
    │       └── 实验 Skill
    │              └── Prompt A（Grok）
    │
    ├── B：AI Recommended Optimization
    │       ├── GPT 独立候选 B-01～B-26
    │       ├── Gemini 二次逻辑审核 ✓
    │       ├── B Skill 规范落地 ✓
    │       ├── Compiler Architecture ✓
    │       └── Verification Contract ✓
    │              └── Prompt B（Grok）
    │
    └── H3 A/B 实测
            └── 统一指标
                    └── 实验结论
                            └── 用户最终批准
```

**当前节点：B 实验 Skill 设计规范已完成，下一节点是 A/B → Grok → Prompt A/B → H3 实测。**
