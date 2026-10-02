# SKILL_OPTIMIZATION — 技能优化

用于讨论、分析和修改 H3NSFW Skill 本身。

## 标准流程

`问题 → 证据 → 多方分析 → 候选方案 → User 决定 → 最小修改 → 测试 → 版本确认`

## 单任务建议结构

```text
SO-0001-问题名称/
├── 00_PROBLEM-问题.md
├── 01_EVIDENCE-证据.md
├── 02_GROK_ANALYSIS-分析.md
├── 03_GPT_ANALYSIS-分析.md
├── 04_GEMINI_ANALYSIS-分析.md
├── 05_CANDIDATE-候选修改.md
├── 06_TEST-测试.md
└── 07_DECISION-最终决定.md
```

## 硬纪律

- V1-5 当前为 Frozen Baseline，普通任务不得自动升级版本。
- Agent 的建议不是授权；只有 User 批准后才能修改 Skill。
- 优先解决真实问题，不为了理论完整性制造新的 Framework / Gate / Layer。
- 修改必须尽可能小，并记录为什么改、改了什么、如何验证。
- 正式 Skill 版本必须进入 `PROJECT/LIBRARY-正式库/SKILL_VERSIONS-技能版本/`，并同步维护根目录协调文件。
