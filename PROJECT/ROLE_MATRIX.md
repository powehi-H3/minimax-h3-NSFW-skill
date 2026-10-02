# ROLE_MATRIX — AI 角色矩阵

| 角色 | 主要职责 | 默认产出 | 不应擅自做的事 |
|---|---|---|---|
| 用户 | 需求、命名、授权、最终批准 | Brief / Approval | — |
| Grok | Prompt 初稿、优化、实验、测试、Execution 分析 | DRAFT / EXPERIMENT / TEST | 不自行修改 V1-5 或覆盖 SOURCE |
| Gemini | 独立 Review、多模态分析、反证、外部研究 | REVIEW / RESEARCH CANDIDATE | 不覆盖 SOURCE，不把意见直接当正式规则 |
| GPT | H3 结构审查、Baseline 对照、综合分析、协作整理 | REVIEW / SYNTHESIS / DECISION SUPPORT | 不伪造其他 AI 原稿，不擅自修改 Skill |

## 用户拥有最终批准权

以下事项必须由用户最终批准：

- Prompt 是否进入 FINAL
- Candidate 是否采用
- Skill 是否修改
- 项目协作协议是否修改
- 核心项目文件是否修改

## 独立性

各 AI 可以不同意其他 AI。

“GPT 认为”“Grok 认为”“Gemini 认为”均属于独立意见，不自动成为项目事实。

## SOURCE 优先级

原始用户需求与 ORIGINAL Prompt 是事实源。

Review 是意见源。

Candidate 是实验候选。

Draft 是采用意见后的新版本。

Final 是用户批准后的正式版本。
