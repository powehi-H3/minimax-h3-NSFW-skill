# PW-0001 — 办公室桌下口交

## Task Type
PROMPT_WRITE（多参 / Multi-Ref）

## Baseline
H3NSFW提示词技能 skill 第三版 / V1-5 Frozen。
本任务不得修改 Skill。

## User Task
用户要求基于多张参考图编写一份 MiniMax H3 NSFW 视频提示词。

核心素材映射：
- Picture 1 + Picture 2：联合锁定视频女主的身份特征。
- Picture 3：办公环境参考，核心空间元素包括办公桌及旁边的沙发床区域。

剧情参与者：
- 一名成年男性；
- 一名成年女性（由 Picture 1 + Picture 2 锁定）；
- 沙发区域的另外两名成年人，他们进行交流并对前景活动保持不知情。

用户要求的场景属于明确的成人性行为，并包含强迫/非自愿情境。具体色情动作内容以原始用户对话为准；本文件只记录任务元数据与协作状态，不重写该具体内容。

## User-specified / Confirmed Parameters
- 参考：Picture 1 + Picture 2 + Picture 3
- 画幅：9:16
- 时长：15 秒
- POV：第一人称、从男性视角向下观察桌下区域
- 对白：用户未指定具体台词
- 摄像机：Grok 初版采用固定机位假设
- Skill：保持 V1-5 Frozen

## Workflow
1. GROK：第一版 Prompt
2. GPT：H3 官方结构、Reference Mapping、语义边界与 Skill 纪律审查
3. Gemini：独立表达、可执行性与质量复核
4. 测试结果记录
5. 根据测试结果进行最小 PATCH / 优化
6. User 最终确认
7. 最终确认版本才可进入正式 Prompt Library

## Important Discipline
- 素材观察不自动等于最终要求。
- Reference Mapping 必须保持职责分离。
- 不因本任务中的局部技巧直接修改 Skill。
- 用户只要求修改某一点时，其余已确认内容尽量保持。
- 任务名称由 User 指定，不由 AI 擅自更名。
