# H3NSFW提示词技能skill第二版 · 修改摘要

内部标记：V13 → 第二版最小集合（仅 A1–A7, B1–B4, C1, C3, C4, D5）

## 实际修改

| ID | 动作 |
|----|------|
| A1 | HARDEN Instruction ≠ Prompt Content |
| A2 | HARDEN PATCH ≠ OPTIMIZE；「其他不动」=硬 PRESERVE |
| A3 | HARDEN 完整六段重编译交付 |
| A4 | HARDEN Runtime/内部状态不进成片 |
| A5–A6 | HARDEN Skill≠项目；默认≠硬约束 |
| A7 | HARDEN 禁止无关 side-effect |
| B1 | ADD Phase 状态转换 |
| B2 | HARDEN Shot 去重不丢当前状态 |
| B3 | HARDEN 统一流水线 Extract→…→Recompile |
| B4 | HARDEN 「优化」vs 只改X 的默认解释 |
| C1 | ADD LoRA capability 框架 |
| C3 | ADD POV 五维（通用摄影，非某 LoRA） |
| C4 | HARDEN 无确认不写 trigger（并入 C1） |
| D5 | ADD 先审计再 UPDATE-SKILL |

## 未改（保护区）

六段 Schema、Facial 四层、Reference 语义、实战默认正文、项目样例、全部 NSFW 黑盒正文。

## Deferred（明确未实施）

Audio 四职表、Picture/Video 独立 label 完整判据、Change Ledger 正式格式、Protected NSFW 专名、暗号体系、Male POV 永久默认、mpov 全局默认、新 Facial/NSFW 内容规则。

## 第二版收口修正（同版本号，非第三版）

- 规范源 SSOT：文首第二版硬规则；Runtime 只展开不另立
- Recompile 默认仅 H3 六段；取消易误导的默认 T2VA 分支
- LoRA 实例：禁止因正文出现过 trigger 字样而自动输出
- STRATEGY：声明以 SKILL.md 为规范源

## T2VA 残留规则消歧（仍第二版）

仅消解执行歧义：当前 H3 Ref2VA 工作流 Recompile 默认完整六段；T2VA 三字段仅纯文本无参考或用户明确要求。未删 T2VA 资料性说明。

## Semantic Addition Gate（第二版通用优化权限收口）

- Optimize 不得把 MODEL INFERENCE 升级为成片新语义（新动作/状态/限制/禁止/阶段行为）
- 成片新增语义须可追溯 USER / OFFICIAL / APPROVED SKILL / 必要语言编译
- Negative Action 堆叠视为该根因的症状；防回流优先 completion→transition→active state
- 用户明确要求的 Negative Constraint 仍属 USER，可保留
- 未改 NSFW 黑盒、Facial、六段 Schema、样例（无强制冲突同步）
