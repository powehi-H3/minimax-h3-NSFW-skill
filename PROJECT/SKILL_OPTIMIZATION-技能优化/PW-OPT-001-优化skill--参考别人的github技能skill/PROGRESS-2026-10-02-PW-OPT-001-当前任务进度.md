# PW-OPT-001｜当前任务进度

> 任务：**优化skill--参考别人的GitHub技能skill**
>
> 本文件属于 PW-OPT-001 主任务，不是独立新任务。

## 当前状态

**IN PROGRESS / EXPERIMENTAL**

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

状态：🟡 **GPT 第一轮候选完成 / Gemini 二次审核中**

当前 B 版候选清单已经建立在：
- V1-5 Frozen Baseline
- 外部 Skill 研究
- GPT 独立工程分析
- Gemini 已提供的初步方向

之上。

B 版不是正式 Skill，也不是 A 版的修改版。

---

## 已完成

- [x] 确定 PW-OPT-001 任务范围：研究外部 GitHub Skill，并形成独立优化实验。
- [x] 确定 V1-5 Baseline 保持 FROZEN。
- [x] 确定 A/B 双路线实验结构。
- [x] 建立 A/B 实验隔离原则。
- [x] 完成外部 Skill 的第一轮结构与机制分析。
- [x] 完成 B 版第一轮优化候选清单（B-01 ～ B-25）。
- [x] 建立 Gemini B 版独立审核入口。
- [x] Gemini 已收到 B 版审核要求。

## 当前进行中

- [ ] Gemini 对 B-01 ～ B-25 逐项审核。
- [ ] Gemini 输出 **B Version Recommended Final Checklist**。

## 下一阶段

- [ ] 完成 A 版实验 Skill。
- [ ] 根据 Gemini 审核结果完成 B 版实验 Skill。
- [ ] 由 Grok 基于同一原始任务分别生成 Prompt A / Prompt B。
- [ ] 使用相同素材、画幅、时长及输入条件进行 H3 A/B 实测。
- [ ] 记录统一指标。
- [ ] 分析 A/B 实测结果。
- [ ] 形成 PW-OPT-001 最终实验结论。
- [ ] 用户最终批准后，才考虑是否进入未来正式 Skill Candidate / 正式版本。

---

## 重要隔离规则

### 1. 不污染正式 Skill

A/B 实验结果不能直接修改 V1-5。

### 2. A/B 互不污染

A 不读取 B 的最终结论作为自身规则；B 也不把 A 的实验实现直接当作自身规则。

### 3. 实验结果不是正式规则

即使某项实验表现优秀，也只能先标记为 `VALIDATED / CANDIDATE`，必须经过用户最终批准才能进入正式 Skill。

### 4. B 当前仍处于审核阶段

B-01 ～ B-25 是 **Review Candidates**，不是已批准规则。

### 5. Grok 介入点

Grok 的主要实验职责发生在 A/B 两个实验版本准备完成后：

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
    │       ├── GPT 候选 B-01～B-25
    │       ├── Gemini 二次审核 ← 当前
    │       └── 实验 Skill
    │              └── Prompt B（Grok）
    │
    └── H3 A/B 实测
            └── 统一指标
                    └── 实验结论
                            └── 用户最终批准
```

**当前节点：Gemini 二次审核 B 版候选清单。**