# V31 Five-Dimensional + Performance Reference (Updated)

Use these patterns inside the `detailed_description` section of the official six-section output.

## 1. Temporal Anchors

Insert explicit visual milestones every 2–3 seconds. Give long Chinese resistance lines enough time (usually 4–5.5 s for Shot 1).

Example:
- Temporal anchor at 00:02.500: she is now lying on her back on the bed, upper body against the sheets, head facing the camera, eyes locked on the lens, upper clothing still fully worn.
- Temporal anchor at 00:08.000: [key contact / pose state for this scene — add full-depth lock only if the user requested it].
- Temporal anchor at 00:13.500: thrusting intensity remains high; her facial muscles tremble more strongly.

## 2. Lighting Physics

Always declare a fixed light source and describe the resulting shadows.

Recommended defaults:
- Top-Left Soft Key
- Top-Left Hard Light
- Soft overhead practical

Example:
Lighting remains Top-Left Soft Key; short soft shadows fall from the man’s hands onto her inner thighs and from her raised legs onto the sheets.

## 3. Fluid Inertia

Describe residual motion after impact when it matters for the scene.

Examples:
- After each impact the flesh of her thighs and lower belly continues a brief residual jiggle before settling.
- Thin translucent strands of lubrication stretch between the base and the labia, break, and reform with the rhythm — **only if the user wants fluid detail**.
- Saliva flows from the corner of her mouth — **only if the user requests drool/saliva**.

Do not add lubrication or saliva lines by default to every prompt.

## 4. Face + Emotion Persistence (Sex vs Non-Sex)

**Sex / intercourse (default):** one continuous positive state matching the user (comfort and pleasure / sensual / resisting). Lips stay parted with ongoing breath and any continuous `<d>` moan string. Do **not** stack per-thrust eyelid/brow toggles. Do **not** default “eyes locked on camera” (often freezes blinks)—only if the user asks for continuous look-at-camera; still allow natural blinks. No forced climax face unless the user asks for climax in this clip.

**Emotion Persistence Gate**:
- Once the target emotion is established, do not reset to neutral.
- Action end or dialogue end ≠ emotional reset.
- End state still shows residual of that emotion (pleasure, resistance, etc.), not the reference blank face.

**Non-sex / user asks climax:** then optional stronger progression; still prefer continuous state over dense micro-beat lists. Saliva only if user requested.

## 5. Background Stability

All static objects in the environment subject (usually <Subject 3>, or <Subject 2> when only woman + background are provided) remain completely stable with no drift or jitter.

## Precise Anatomy Patterns (Use Only When the Scene Needs Them)

### Full-length Insertion (optional — when user wants depth lock)
- The entire cylindrical shaft is buried inside her vagina, with only the base of the shaft remaining visible at the entrance.
- Fully seated / entire shaft fully buried on every deep stroke.

### Contact & Deformation
- Labia stretched into a tight ring around the root of the shaft.
- Outer labia slightly parted and flushed deep pink.
- Inner thighs compressed and slightly indented under the man’s grip.
- Lower belly shows a subtle impact ripple with each full-depth thrust.

### Fluid (optional — only when user asks)
- Thin translucent strands of lubrication stretch, break, and reform.
- Saliva flowing and dripping from the corner of the mouth.

## Motion Booster (dynv2) Pattern

dynv2. From the first frame the thrusting is already at high intensity: continuous, forceful, rhythmic forward-and-back motion that keeps the full length of the penis fully seated on every deep stroke, delivering clear impact, deep penetration, visible compression of her flesh against the pubic area, strong hip rebound, and natural secondary bounce of thighs, hips, and lower belly.

## Clothing Retention Pattern (Critical)

Strong statement (use in subject_definitions + beginning of detailed_description + End State):

Her upper clothing must remain completely unchanged and fully worn exactly as shown in <Picture 1> throughout the entire video. The upper clothing is never removed, pulled up, or altered. Only the lower body is completely nude.

## Strict Dialogue Isolation

- All spoken language only inside `<d>[Chinese] 原文</d>`.
- Delivery description immediately before `<d>`.
- After `</d>` only non-verbal aftermath.
- Never restate or partially quote the line outside `<d>`.

## Performance Density

- Prefer 2–4 meaningful beats in 10–15 seconds.
- Ordinary beat = 1 main face state + 1 main body action.
- Avoid stacking too many simultaneous micro facial changes in the same second.

## Aspect Ratio Notes

- **9:16 portrait**: Add “The framing prioritizes her face in the upper portion of the vertical frame and the insertion in the lower portion.”
- **16:9 landscape**: Wider environment, insertion detail may be reduced.

## End State Requirement

Always close with a clear End State that records what must not drift for **this** scene:
- Limb / body positions relevant to the pose
- Upper clothing still fully worn (when required)
- Eyes still locked on the camera (when continuous eye contact was requested)
- Residual climax intensity (not neutral) — Emotion Persistence
- Optional only when the user asked for them: full-insertion depth lock; saliva still dripping
- Residual micro-tremors when climax intensity was established
