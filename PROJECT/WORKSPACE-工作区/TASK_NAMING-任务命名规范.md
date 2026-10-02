# H3NSFW Prompt Project — Task Naming Convention
# H3NSFW Prompt 项目任务命名规范

## 1. 基本原则

任务名称由用户最终决定。

AI 可以提出名称建议，但不得擅自改变用户确定的任务名称。

本文件属于 **GitHub 项目协作管理规范**，不属于 MiniMax H3 Prompt Skill，不应写入或反向修改 SKILL.md。

## 2. 当前任务命名示例

### Prompt Writing — 提示词编写

格式：

`PW-XXXX-编写提示词---（用户指定名称）`

用途：从用户需求出发，从零开始编写新的 MiniMax H3 NSFW Prompt。

### Prompt Writing from Reference — 参考提示词写提示词

格式：

`PW-XXXX-参考提示词写提示词---（用户指定名称）`

用途：基于用户提供的 Prompt、图片、视频或其他素材进行参考、映射、重写或重新编译。

参考素材中的观察内容不得自动等同于用户最终要求。

### Prompt Optimization — 提示词优化

格式：

`PO-XXXX-优化提示词---（用户指定名称）`

用途：对已经存在的 Prompt 进行优化、修正、PATCH 或测试迭代。

如果用户只要求修改某一点，应尽量只修改该授权部分，其余已批准内容保持不变。

### Skill Optimization — 技能优化

格式：

`SK-XXXX-优化技能skill---（用户指定名称）`

用途：研究、验证或修改 Skill 本身。

Skill 修改不是普通 Prompt 任务的一部分，必须遵守现有项目审批纪律。

### H3 Research — H3 研究

格式：

`RE-XXXX-研究 H3---（用户指定名称）`

用途：研究 MiniMax H3 官方资料、工作流、模型行为、社区实测或其他外部证据。

研究结果默认属于 Research / Candidate，不自动进入 Skill。

### Prompt Testing — 提示词实测

格式：

`TE-XXXX-实测提示词---（用户指定名称）`

用途：记录已经生成或候选 Prompt 的实际 H3 输出测试、异常、对照结果与结论。

## 3. 编号规则

- `XXXX` 为项目连续编号。
- 编号用于项目管理和追踪，不代表 Skill 版本。
- 任务类型前缀仅用于方便识别，不构成新的 Framework、Gate、Layer 或 Universal Rule。

## 4. 命名权限

- 用户是任务最终命名者。
- AI 可以建议名称。
- 用户确认后的名称不得被 AI 擅自重命名。
- 如果用户只给出任务名称而没有指定任务类型，AI 可以根据上下文提出分类建议，但最终以用户决定为准。

## 5. 与 SKILL.md 的边界

本命名规范只解决：

> “项目任务如何命名、分类和存档。”

SKILL.md 只解决：

> “如何根据用户需求编写、修改和优化 MiniMax H3 Prompt。”

不得因为任务管理需求而向 SKILL.md 添加项目管理规则。

## 6. 目录原则

正在进行中的任务进入：

`PROJECT/WORKSPACE-工作区/`

完成并经用户正式确认的 Prompt 进入：

`PROJECT/LIBRARY-正式库/PROMPTS-正式提示词/`

经过用户批准的 Skill 版本进入：

`PROJECT/LIBRARY-正式库/SKILL_VERSIONS-技能版本/`
