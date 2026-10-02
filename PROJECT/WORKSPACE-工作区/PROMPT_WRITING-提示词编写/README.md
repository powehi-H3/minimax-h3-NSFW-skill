# PROMPT_WRITING — 提示词编写

用于从零开始编写新的 MiniMax H3 提示词。

## 标准流程

1. User 提供需求与可用素材。
2. GROK 负责形成第一版可执行提示词。
3. GPT 负责结构、语义边界、官方规则一致性和风险检查。
4. Gemini 负责独立的提示词表达、可执行性和质量复核。
5. GROK / GPT / Gemini 根据测试结果继续迭代。
6. User 最终确认。
7. 确认后的成品复制到 `PROJECT/LIBRARY-正式库/PROMPTS-正式提示词/`。

## 单任务建议结构

每个具体任务使用独立文件夹，例如：

```text
PW-0001-任务名称/
├── 00_BRIEF-需求.md
├── 01_GROK_DRAFT-初版.md
├── 02_GPT_REVIEW-审查.md
├── 03_GEMINI_REVIEW-审查.md
├── 04_TEST_RESULTS-测试结果.md
├── 05_FINAL-最终版.md
└── 06_DECISION-收录决定.md
```

## 重要规则

- 工作区里的版本不是正式资产。
- 没有 User 最终确认，不进入正式提示词库。
- 不因为素材中出现某个元素就自动加入最终提示词，除非 User 要求参考。
- 如果 User 要求只改某一点，其余内容应尽量保持。
