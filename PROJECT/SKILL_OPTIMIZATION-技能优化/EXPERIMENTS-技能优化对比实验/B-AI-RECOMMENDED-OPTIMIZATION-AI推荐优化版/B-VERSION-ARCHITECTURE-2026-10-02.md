# PW-OPT-001｜Version B AI 推荐优化版｜架构记录

状态：EXPERIMENTAL / DESIGN-FROZEN（仅限实验组，不进入正式 Skill）

## 目的

Version B 是 GPT + Gemini 独立重构路线，用于与 Version A（外部 Skill 全量参考版）进行 A/B 实验。

正式 V1-5 Baseline 保持 FROZEN。A/B 两组完全隔离，B 不复制 A 的最终实现，也不反向修改正式 Skill。

## Gemini 二次审核后的 B 版最终设计清单

### Phase 1｜模式分流与资产约束

- B-01 H3 Mode Detection Layer：Ref2VA/T2VA/I2VA/FL2VA 模式识别与防止误把 Reference 当 Frame Anchor。
- B-02 Reference Role Mapping Layer：显式定义 Identity、Clothing、Environment、Composition、Motion、Camera、Audio、Style、Frame Anchor 等作用域。
- B-03 Reference Conflict Resolver：在内部 IR 阶段解决多 Reference 冲突；Conflict Table 不进入最终 H3 Payload。
- B-24 Reference Asset Wiring Awareness：语义 Reference Mapping 与物理 Image Input Socket 顺序分离并保持一致。

### Phase 2｜动作、运镜与空间物理控制

- B-06 One Dominant Action per Shot：每个 Shot 仅一个同等级主导动作；次要微动作允许存在，但不得形成第二主动作。
- B-07 Action Vector Layer：direction、amplitude、frequency、contact、trajectory、speed、acceleration/deceleration、start/end state；遵循 Minimum Sufficient Physical Description。
- B-08 Camera Kinematics Layer：Camera State 与 Subject Action 分离，避免语义耦合。
- B-09 Spatial Geography Layer：自适应 L0-L2；L3 复杂 3D spatial graph 暂列 RESEARCH ONLY。
- B-13 Environmental Reactivity Controller：默认 OFF，仅在用户要求、剧情核心或对执行确有帮助时开启。
- B-14 Visual Texture Budget：有 Reference 时减少冗余视觉质感词；无 Reference 时才补必要视觉参数。

### Phase 3｜状态递推与 Prompt Budget

- B-05 Temporal State Ledger：记录 subject/pose/object/environment/camera/audio/newly-introduced/carried-over state，确保 Shot 间增量继承。
- B-10 Adaptive Prompt Density：按任务复杂度动态分配 Prompt Density Budget，避免 Attention Overcrowding。
- B-15 Camera / Subject / Environment 三层解耦：三个独立层，可互相关联但不得混成不可调试的长句。

### Phase 4｜创意隔离、PATCH 与 Debug

- B-11 Creative Enhancement Gating：严格区分 User Requirement 与 AI Proposal。
- B-12 Narrative Creative Enhancement：脑暴与 Prompt Compilation 解耦；用户确认后才进入最终 Prompt。
- B-16 PATCH Architecture：支持 PATCH_CAMERA、PATCH_ACTION、PATCH_CHARACTER、PATCH_ENVIRONMENT、PATCH_AUDIO、PATCH_TIMING、PATCH_REFERENCE 等局部修改。
- B-17 Minimal Semantic Change：PATCH 只改变用户指定层，非目标层保持锁定。
- B-20 Debug Trace：内部保留来源追踪，最终 H3 Payload 自动剥离 Debug 元数据。

### Phase 5｜Compiler、Verification 与治理

- B-04 Retention Analysis 2.0：升级为 Pre-flight Reference Retention Matrix，只作为内部校验，不输出元数据标签给 H3。
- B-18 Shot-Level Verification：逐 Shot 检查 Dominant Action、Subject、Reference、Camera、Environment、State Continuity、Timestamp 与 Semantic Invention。
- B-19 Global Verification：最终检查 Reference labels、Timeline、State continuity、Camera/Action separation、语义漂移与输出格式契约。
- B-21 Evidence / Candidate Status：RESEARCH → EXPERIMENTAL → VALIDATED → PROPOSED → FROZEN 的生命周期治理。
- B-22 A/B Experimental Isolation：B 与 A 在评估前完全隔离，避免实验污染。
- B-23 Mode-Specific Optimization：按 Ref2VA/I2VA/T2VA/FL2VA/L2VA 差异化启用增强机制。
- B-25 Output Compiler Layer：IDEATION → SEMANTIC PLAN → REFERENCE MAP → SHOT PLAN → PHYSICAL EXECUTION PLAN → H3 FORMAT COMPILER → VERIFICATION。
- B-26 总体原则：用户语义优先、Reference 约束优先、H3 可执行性优先、Minimum Sufficient Description、创意与编译解耦、Camera/Action/Environment 解耦、实验与正式规则解耦、可追溯/可测试/可回滚。

## Gemini 审核结论

B-01、B-02、B-05、B-06、B-07、B-08、B-10、B-11、B-12、B-13、B-14、B-15、B-16、B-17、B-18、B-19、B-21、B-22、B-23、B-24、B-25、B-26：ACCEPT。

B-03、B-04、B-09、B-20：MODIFY；其中 B-09 Level 3 明确降为 RESEARCH ONLY。

## 隔离纪律

1. 不修改正式 V1-5 Baseline。
2. 不把本文件中的实验设计自动当作正式 Skill Rule。
3. 不让 B 读取 A 的最终优化实现作为自身约束。
4. A/B 必须使用相同测试任务，由 Grok 分别生成 Prompt A / Prompt B，再进行 H3 实测比较。
5. 实验结果经过用户最终批准后，才可能讨论是否进入正式 Skill。

## 当前阶段

B 设计审核已完成；下一阶段是根据本清单在本目录中落地 B 实验 Skill，再交由 Grok 做同任务 Prompt A/B 对比测试。
