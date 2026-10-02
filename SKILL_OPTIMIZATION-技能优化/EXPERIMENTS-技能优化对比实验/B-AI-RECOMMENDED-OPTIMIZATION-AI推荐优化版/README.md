# B — AI RECOMMENDED OPTIMIZATION / AI 推荐优化版

## 定位

PW-OPT-001 的独立实验路线 B。

**当前状态：EXPERIMENTAL / IMPLEMENTED SPECIFICATION / NOT VALIDATED**

B 版不是正式 Skill，不覆盖 V1-5，也不读取 A 版最终实现作为自身约束。

## 当前已完成

1. GPT 独立提出 B-01～B-26 工程强化候选。
2. Gemini 对 26 项进行了逐项二次逻辑审核。
3. Gemini 形成 B Version Recommended Final Checklist。
4. GPT 根据 Gemini 审核结果落地 B 实验 Skill 规范：`SKILL-B.md`。
5. 建立 B 编译器架构：`B-ARCHITECTURE.md`。
6. 建立 B 验证契约：`B-VERIFICATION.md`。

## Gemini 审核后的关键收敛

- B-03 Reference Conflict Resolver：内部 IR 处理，不输出 Conflict Table。
- B-04 Retention Analysis 2.0：Pre-flight 内部校验，不写入物理 Prompt。
- B-09 Spatial Geography：默认只到 L0-L2；L3 = RESEARCH ONLY。
- B-20 Debug Trace：内部日志/Meta 状态，最终 Payload 自动剥离。
- B-10 Adaptive Prompt Density：成为核心控制原则。
- B-16/B-17：采用 PATCH + Minimal Semantic Change。
- B-23：按 H3 Mode 差异化应用规则。
- B-25：采用多阶段 Output Compiler Pipeline。

## 与 A 组隔离

A = External Skill Full Reference。

B = AI Recommended Optimization。

A/B 在正式对比前不得互相污染。最终由 Grok 使用相同任务、素材和参数分别生成 Prompt A / Prompt B，再进行 H3 实测比较。

## 与正式 Skill 隔离

V1-5 Baseline = FROZEN。

任何 B 规则都不会因为本文件完成而自动进入正式 Skill。

## 下一步

1. Grok 读取 `SKILL-B.md` 并使用相同测试任务生成 `PROMPT-EXPERIMENT-B`。
2. A/B 使用统一实验条件进行 H3 渲染。
3. 根据实测结果记录 VALIDATED / RESEARCH / REJECT 等证据状态。
4. 只有用户明确批准后，才讨论是否进入正式 Skill。
