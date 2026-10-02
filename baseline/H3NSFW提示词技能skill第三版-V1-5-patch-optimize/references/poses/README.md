# Pose Visual Library (Dynamic)

Images here are for the **skill only** — to write accurate pose descriptions.  
They are **never** passed to H3 as Ref2VA reference pictures.

## Folder structure

```text
poses/
├── cowgirl (骑乘)/
│   ├── cowgirl_front (正向骑乘)_01.jpg
│   ├── cowgirl_front (正向骑乘)_02.jpg
│   └── cowgirl_reverse (反向骑乘)_01.jpg
├── missionary (传教士)/
│   ├── missionary_leg_up (平躺抬腿)_01.jpg
│   └── missionary_hold_hands (抓手抬腿)_01.jpg
├── standing (站立)/
│   └── standing_carry (抱操壁咚)_01.jpg
├── sofa_side (沙发侧入)/
│   └── sofa_half_lie (半躺插入)_01.jpg
└── 做爱/
    ├── 第一人称视角/ (传教士 · 床上骑乘 · 坐边上骑乘 …)
    ├── 第三人称视角/
    │   ├── 侧卧/prompt.md
    │   └── 半仰卧抬腿侧入/prompt.md
    └── 切镜/
        ├── 骑乘位切镜/prompt.md
        └── 侧卧切镜/prompt.md
```

- **Level 1:** `poses/` root (fixed)
- **Level 2:** Big category = `english (中文)` or `做爱/视角/姿势` — relatively stable
- **Level 3:** Files = images or `prompt.md` verified templates — add/delete freely
- Verified **text templates** under `做爱/…/prompt.md` are paste-ready skeletons; still switch expression tier and lines per user request.

## Naming convention

- Folder: `cowgirl (骑乘)`
- File: `cowgirl_front (正向骑乘)_01.jpg`

Match by **folder name** and **filename keywords** (English or Chinese). Do not hard-code exact filenames.

## Skill read rules

1. Detect target pose from user request (e.g. cowgirl front / 正向骑乘).
2. List files under the matching category folder(s).
3. Prefer files whose names contain the specific pose keywords.
4. Read 1–several current images; extract body relation, leg position, insertion angle, support points, camera height.
5. Write those into the H3 prompt as English geometry/action text.
6. If the folder is empty or no match → fall back to text-only position templates. Do not fail.

## What not to do

- Do not put these images into H3 Picture/Subject reference slots.
- Do not hard-code specific filenames in SKILL.md.
- Do not invent pose details that contradict what is visible in the current images.
