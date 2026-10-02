# Third-Person View Guide for H3 NSFW Prompts

**Mandatory:** When the user requests 第三人称 / third-person / 旁观视角 / external camera (not male POV), **read this file first** and apply it. Do not reuse first-person POV templates without rewriting camera and body-visibility language.

---

## 1. Definition

| | First-person POV (archived under 第一人称视角) | Third-person |
|--|-----------------------------------------------|--------------|
| Camera | Man’s eyes (look up / look down) | **External camera**; viewer outside the couple |
| Man’s body | Often lower body / arms only | **Can show full or partial man** |
| Composition | Easy to lose woman’s face after mount | Can show **both bodies + space + face** |
| Aspect | Often 9:16 | **16:9 preferred** for relationships; 9:16 allowed if user asks |
| Immersion | Strong “I am the man” | “Watching a scene” |

**Required phrases in prompts:**
- `third-person view` / `external camera` / `not POV` / `not first-person`
- Never write: `male first-person POV`, `from the man’s eyes`, `looking up at her` as camera identity

---

## 2. Official H3 camera vocabulary (third-person uses these)

Write as natural sentences. Prefer **one** main move per 15s clip.

| Type | Example |
|------|---------|
| Static Shot | The camera holds a completely static shot |
| Push In / Pull Out | The camera pushes in with small amplitude at slow speed toward her face |
| Pan / Truck | The camera trucks right… |
| Tilt / Pedestal | The camera tilts down slightly… |
| Arc Shot | The camera arcs around the couple with small amplitude |
| Tracking Shot | The camera tracks the hip motion (use sparingly; can shake) |
| POV | **Only** if user explicitly wants first-person — otherwise avoid |

Default for intercourse: **`completely static`** unless user asks for move.

---

## 3. Recommended angles by position (NSFW)

| Position | Preferred third-person angle | Must keep in frame |
|----------|------------------------------|--------------------|
| Missionary | Side 45° medium, or slight high angle | Her face + his back/side + hip drive along body axis |
| Cowgirl (bed) | Side 45° or front three-quarter medium | Her face/torso + vertical hip ride + man lying |
| Doggy | Side-rear 45° or rear medium | Her profile or look-back + his hip impacts |
| Seated lap straddle | Side or 3/4 front medium | Both upper bodies + hands on outer thighs + rise/sink |
| Standing carry | Full medium, slight low | Support legs + hold + optional push-in to face |

**Composition rules:**
- State **who is on which side of frame** and facing direction; do not flip left-right mid-clip
- Shot size: `medium` / `medium-full` so face is readable; avoid extreme wide if identity matters
- Explicitly: `her face remains clearly visible/readable in frame` when face matters
- This is **not** “camera = man’s eyes”; it is external framing that still may show her face

---

## 4. Motion axis = body axis (not camera direction)

Do not rely on pose labels alone. Write thrust direction from **body**:

| Pose | Axis language |
|------|----------------|
| Missionary | Hips drive **forward and back along the body axis** (not vertical piston) |
| Cowgirl | **Vertical** rise and sink of her hips |
| Doggy | He thrusts **from behind** into her; her hands/knees support |
| Seated straddle | She **rises and sinks on his lap**; his hands on **outer thighs**; weight on his thighs |

---

## 5. Reference image duties (third-person)

Six-section Ref2VA still applies.

| Asset | Typical duty |
|-------|----------------|
| Picture 1 + Picture 2 | Same woman dual identity lock (when user provides two woman refs) |
| Picture 3 | Environment (bed / room / chair) |
| Optional Picture 4+ | **Man identity** if face or full body required (third-person needs this more often than POV) |

Do not invent a man-face reference if user did not supply one; then man may be partial body only.

---

## 6. Forbidden carry-over from POV templates

| Remove from POV templates | Write instead |
|---------------------------|---------------|
| male first-person POV looking up/down | third-person medium shot, external camera, not POV |
| low-angle from the man’s eyes | side 45-degree / three-quarter view of both bodies |
| camera is the man’s viewpoint | man visible in frame as a subject (full or partial) |
| only lower foreground penis as camera anchor | both bodies placed in space relative to each other |

---

## 7. 15-second third-person structure

1. **0–2s** Establish: third-person medium, couple already in position, environment locked  
2. **2–12s** Single motion axis continuous (thrust / ride) + soundscape  
3. Dialogue in `<d>` only; tone matches plot (pleasure / resistance)  
4. Camera default static; optional one small push-in to face  
5. No forced climax in 15s unless user asks  

---

## 8. Skeleton clauses (copy and adapt)

```text
Third-person view, external camera, not first-person POV.
Medium shot, side 45-degree angle (or three-quarter).
Both bodies visible in frame: the woman [pose], the man [pose].
Camera completely static.
Her face remains clearly readable in the frame.
[Position-specific hip/thrust axis — see section 4]
Environment locked to <Picture N>.
Identity locked to <Picture 1> and <Picture 2> [if dual woman].
```

---

## 9. Archive path (when templates exist)

```text
references/poses/做爱/第三人称视角/
  (create subfolders per position when user validates prompts)
```

Until subfolders exist, **always apply this guide** when writing any third-person NSFW H3 prompt.

---

## 10. Checklist before delivery

- [ ] Explicit third-person / external / not POV  
- [ ] One clear shot size + angle  
- [ ] Body-axis thrust language for the position  
- [ ] Face readable if identity matters  
- [ ] Man visibility stated (full / partial / lower only)  
- [ ] No POV-only phrases left in the prompt  
- [ ] Soundscape still thrust-synced; dialogue in `<d>`  
