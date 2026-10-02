# PROJECT

This area stores cross-agent project records and task workspaces.

## Purpose

- cross-agent issue resolution;
- consolidated research conclusions;
- approved project decisions;
- experiment comparisons;
- implementation handoff records;
- prompt-writing and prompt-optimization task histories;
- Skill optimization task histories.

Nothing in this area changes the Skill baseline unless the User explicitly approves the change.

## Workspace structure

```text
PROJECT/
├── WORKSPACE-工作区/
│   ├── PROMPT_WRITING-提示词编写/
│   ├── PROMPT_OPTIMIZATION-提示词优化/
│   ├── SKILL_OPTIMIZATION-技能优化/
│   └── MATERIAL_RESEARCH-素材研究/
│
├── LIBRARY-正式库/
│   ├── PROMPTS-正式提示词/
│   └── SKILL_VERSIONS-技能版本/
│
└── TEMPLATES-模板/
    ├── PROMPT_TASK_TEMPLATE.md
    └── SKILL_OPTIMIZATION_TASK_TEMPLATE.md
```

## Core lifecycle

### Prompt task

`需求 → GROK 初版 → GPT / Gemini 审查与优化 → 测试 → 用户确认 → 正式收录`

A prompt is copied into `LIBRARY-正式库/PROMPTS-正式提示词/` only after the User confirms that the prompt is ready for formal retention.

### Skill optimization task

`问题 → 证据/失败案例 → 分析 → GPT/Gemini/GROK 分别提出意见 → 汇总 → 用户决定 → 最小修改 → 测试 → 版本确认`

A Skill file is never changed merely because an agent suggested a change. User approval is required before a baseline change is committed.

## Important distinction

- `WORKSPACE-工作区/` = work in progress, discussion, drafts, tests, candidate solutions.
- `LIBRARY-正式库/` = confirmed, reusable project assets.
- `baseline/` = frozen source mirror of the current Skill package. It is not the place for ordinary task drafts.
- Root `STATUS.md`, `DECISIONS.md`, `CHECKPOINT.md`, and `ROLE_MATRIX.md` remain the project-level coordination records.

## Naming convention

Folder and file names use English identifiers followed by Chinese explanations where practical, so the structure is machine-readable while remaining understandable to the User.
