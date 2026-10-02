# MATERIAL_RESEARCH — 素材研究

用于单独记录参考图片、视频、提示词样本、官方资料等素材的观察与研究。

## 核心原则

- 素材观察结果不等于 User 最终要求。
- 只有 User 明确要求参考的素材信息，才进入最终提示词。
- 研究结论可以支持 Prompt 任务或 Skill 优化任务，但不能自动改变 Baseline。
- 对素材的身份、环境、镜头、动作等职责映射应单独记录，避免在多个任务里重复解释。

## 建议结构

```text
MR-0001-素材名称/
├── 00_BRIEF-研究目标.md
├── 01_SOURCE-素材记录.md
├── 02_GROK_RESEARCH-研究.md
├── 03_GPT_RESEARCH-研究.md
├── 04_GEMINI_RESEARCH-研究.md
└── 05_CONCLUSION-结论.md
```
