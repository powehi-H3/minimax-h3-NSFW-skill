# PW-OPT-001｜当前任务进度

> 任务：**优化skill--参考别人的GitHub技能skill**
>
> 本文件属于 PW-OPT-001 主任务，不是独立新任务。

## 当前状态

**IN PROGRESS / EXPERIMENTAL**

正式 V1-5 Baseline：**FROZEN**

本任务中的实验路线不会直接修改正式 Skill。

**Last sync:** 2026-10-03 / Version B experimental skill implemented

---

## 实验路线

### A｜External Skill Full Reference（外部 Skill 全量参考版）

状态：🟡 实验资产已有 + **Prompt A 样本已生成**

目标：尽可能完整参考外部 `benjiyaya/Minimax-H3-Prompt-AgentSkill`，形成独立实验版本。

原则：
- 不修改 V1-5
- 不吸收 B 的优化意见
- 独立保存、独立测试

已有：
- `EXPERIMENTS/.../A-.../SKILL-A.md`
- `GROK/2026-10-03-PROMPT-EXP-A-桌下口交.md`
- `GROK/2026-10-03-PROMPT-PURE-EXTERNAL-桌下口交.md`（纯外部 Skill 对照样本，非项目正式风格）

### B｜AI Recommended Optimization（AI 推荐优化版）

状态：🟢 **B 版实验 Skill 已按 Gemini 二次审核后的 Final Checklist 落地；尚未 H3 验证**

B 版不是正式 Skill，也不是 A 版的修改版。

已落地：
- `EXPERIMENTS/.../B-AI-RECOMMENDED-OPTIMIZATION-AI推荐优化版/SKILL-B.md`
- B-01 ～ B-26 编译/验证/治理规则
- Compiler Pipeline
- Internal IR / Pre-flight / Verification / Debug Trace 隔离原则
- Mode-specific optimization
- PATCH / Minimal Semantic Change
- A/B Experimental Isolation

---

## 已完成

- [x] 确定 PW-OPT-001 任务范围
- [x] V1-5 Baseline 保持 FROZEN
- [x] A/B 双路线实验结构与隔离原则
- [x] 外部 Skill 第一轮结构分析
- [x] B 版候选清单与相关审核材料
- [x] **Gemini 完成 B-01 ～ B-26 二次逻辑审核并输出 Final Checklist**
- [x] **GPT 根据 Gemini Final Checklist 独立落地 Version B 实验 Skill**
- [x] **2026-10-03 Grok：按纯外部 Skill 写出桌下口交 Prompt**
- [x] **2026-10-03 Grok：按 Experiment A（SKILL-A）写出桌下口交 Prompt**
- [x] **2026-10-03 对话检查点写入 `GROK/2026-10-03-CONVERSATION-CHECKPOINT.md`**

## 当前进行中 / 待办

- [ ] 用户审阅 Pure External / EXP-A 两版 Prompt
- [ ] **由 Grok 基于同一原始任务 + Version B Skill 生成 Prompt B**
- [ ] 同素材 H3 实测（A vs B；可选 Pure External 作为额外对照）
- [ ] 统一指标记录与实验结论
- [ ] 用户批准前不写回正式 Skill

---

## 重要隔离规则

1. 不污染正式 Skill / V1-5
2. A/B 互不污染
3. 实验结果 ≠ 正式规则
4. Pure External 样本仅作对照，不代表项目默认写法
5. Grok 原稿与后续 Review 分层保存
6. B 版新增机制必须保持实验状态，除非经过实测与用户批准，不得自动升级

---

## 当前任务链（更新）

```text
PW-OPT-001
    │
    ├── A：External Skill Full Reference
    │       ├── SKILL-A.md
    │       └── Prompt A（Grok 2026-10-03 桌下口交）✓
    │
    ├── Pure External contrast sample（Grok 2026-10-03）✓
    │
    ├── B：AI Recommended Optimization
    │       ├── Gemini Final Checklist ✓
    │       ├── SKILL-B.md ✓
    │       └── Prompt B（Grok）← 下一步
    │
    └── H3 实测 → 指标 → 结论 → 用户批准
```

**当前节点：Version B 实验 Skill 已完成第一版落地；下一步是让 Grok 使用同一原始任务生成 Prompt B，然后进行 A/B 同条件测试。**
