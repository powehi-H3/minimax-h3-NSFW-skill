# WORKFLOW — Prompt 任务工作流

## 0. 用户命名

用户负责给任务命名。

例如：

- 编写提示词 — xxx
- 参考提示词写提示词 — xxx
- 优化技能 Skill — xxx

项目文件夹使用英文主名 + 中文解释，方便用户识别。

## 1. Brief

用户提出任务与素材。

记录：

- 任务名称
- 任务类型
- 参考素材
- Reference Mapping（如有）
- 时长 / 画幅 / 输出要求
- 必须保留
- 明确禁止新增

## 2. SOURCE

保存用户原始需求以及已有原始 Prompt。

SOURCE 不修改。

## 3. 初稿

通常由 Grok 负责 Prompt 初稿和第一轮 Execution-oriented 处理。

初稿保存为独立版本。

## 4. 独立 Review

Gemini 与 GPT 分别进行 Review。

Review 不覆盖初稿。

Review 可以指出：

- Reference 问题
- H3 结构问题
- 空间问题
- 动作连续性问题
- Camera 问题
- 语义问题
- 测试假设

## 5. Candidate

如果发现值得测试的新方法，先记录为 `RESEARCH CANDIDATE`。

不自动升级为 Skill 规则。

## 6. 用户批准

用户选择哪些意见进入下一版本。

只有批准的修改才进入 Draft V2/V3。

## 7. Test

记录实际测试：

- 输入版本
- 测试参数
- 成片表现
- 失败点
- 改进点

## 8. Final

只有用户明确批准后，Prompt 才进入正式 Prompt Library。

## 9. Skill Optimization

Skill 优化任务单独进入 `SKILL_OPTIMIZATION-技能优化/`。

流程：

```text
问题 → SOURCE / 对话证据 → 独立分析 → Research Candidate → 实验/验证 → 最小修改候选 → 用户批准 → Skill 更新
```

不因为单个 Prompt 的偶发失败直接修改 Skill。
