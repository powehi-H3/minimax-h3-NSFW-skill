# PW-OPT-001｜Version B — AI 推荐优化版

状态：**EXPERIMENTAL / FROZEN FOR EXPERIMENT**

本目录是 PW-OPT-001 的 B 组独立实验资产。

## 隔离纪律

- 正式 V1-5 Baseline：FROZEN，不修改。
- A 组：外部 Skill 全量参考版，独立保存。
- B 组：GPT + Gemini 独立重构版，独立保存。
- B 不复制 A 的具体实现。
- B 不反向污染正式 Skill。
- A/B 测试前不互相读取最终优化规则作为约束。
- 任何具体历史剧情、人物、动作或旧 Prompt 偏好只可作为 Benchmark，不得自动升级为通用 Skill Rule。

## B 版来源

B 版设计来自：
1. V1-5 Baseline 的通用结构与 Reference Semantics；
2. 外部 `benjiyaya/Minimax-H3-Prompt-AgentSkill` 的公开工程思想研究；
3. GPT 独立 B-01～B-26 研究清单；
4. Gemini 对 B-01～B-26 的第二次独立逻辑审核。

## 三阶段落地

1. **Architecture**：`Ideation → Semantic Plan → Reference Map → Shot Plan → Physical Execution Plan → H3 Format Compiler → Verification`
2. **B Skill**：按 `SKILL.md` 实现实验编译规则；内部 IR/Retention/Debug 元数据不得泄漏到最终 H3 Payload。
3. **Verification**：执行 Shot-Level 与 Global Verification，并记录规则生命周期。

## 当前状态

- B 设计审核：COMPLETED
- B 推荐清单：FROZEN FOR EXPERIMENT
- B Skill 落地：本分支进行中
- Grok Prompt A/B：PENDING
- H3 A/B 实测：PENDING
- 正式 V1-5 升级：NOT APPROVED
