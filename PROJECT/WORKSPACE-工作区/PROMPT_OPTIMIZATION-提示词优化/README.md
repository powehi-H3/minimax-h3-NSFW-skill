# PROMPT_OPTIMIZATION — 提示词优化

用于优化已经存在的 MiniMax H3 提示词，而不是从零创建。

## 标准流程

1. 保存 User 指定的原始提示词。
2. 明确优化目标与必须保留内容。
3. GROK、GPT、Gemini 分别分析问题与候选改法。
4. 根据测试结果迭代。
5. User 确认最终版本。
6. 将确认后的版本收录到 `PROJECT/LIBRARY-正式库/PROMPTS-正式提示词/`。

## 单任务建议结构

```text
PO-0001-任务名称/
├── 00_BRIEF-需求.md
├── 01_SOURCE-原始提示词.md
├── 02_GROK_ANALYSIS-分析.md
├── 03_GPT_ANALYSIS-分析.md
├── 04_GEMINI_ANALYSIS-分析.md
├── 05_CANDIDATES-候选方案.md
├── 06_TEST_RESULTS-测试结果.md
├── 07_FINAL-最终版.md
└── 08_DECISION-收录决定.md
```

## PATCH 纪律

如果 User 说“只改某一点 / 其他不动”，任务默认按最小修改处理：只改变授权范围内的内容，不借优化之名重写其它部分。
