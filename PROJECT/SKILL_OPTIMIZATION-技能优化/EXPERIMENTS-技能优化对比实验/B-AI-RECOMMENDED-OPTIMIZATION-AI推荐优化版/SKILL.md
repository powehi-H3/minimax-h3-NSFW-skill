# PW-OPT-001｜Version B Skill — AI Recommended Optimization

**Status:** EXPERIMENTAL / FROZEN FOR EXPERIMENT
**Baseline:** V1-5 FROZEN
**Purpose:** independent B-group Prompt Compiler experiment

## 0. Non-negotiable boundaries

This Skill is an experimental compiler architecture, not a replacement for the formal V1-5 Skill.

Never:
- modify or supersede V1-5;
- import A-group final rules as B constraints;
- turn historical scene-specific preferences into general rules;
- invent story, actions, identities, references, camera moves, environment changes, or audio unless authorized by the user or selected through the explicit Ideation Gate;
- emit internal compiler metadata to the final H3 payload.

## 1. Compiler pipeline

`INPUT → MODE DETECTION → SEMANTIC PLAN → REFERENCE MAP → CONFLICT RESOLUTION → RETENTION CHECK → SHOT PLAN → STATE LEDGER → PHYSICAL EXECUTION PLAN → H3 FORMAT COMPILER → SHOT VERIFICATION → GLOBAL VERIFICATION → OUTPUT`

Creative ideation is a separate optional pre-stage:
`USER IDEA → IDEATION → USER APPROVAL → SEMANTIC PLAN`

If the user did not request creative help, skip Ideation and preserve user intent literally.

## 2. B-01 Mode Detection

Detect the applicable generation mode from the supplied task and assets:
- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

Classify each image/asset as one or more explicitly assigned roles:
- character/reference asset
- environment/style reference
- first-frame anchor
- last-frame anchor
- storyboard/keyframe

Asset presence alone never implies frame-anchor status. If mode or anchor role is materially ambiguous, ask the minimum necessary clarification.

## 3. B-02 Reference Role Mapping

Every reference receives an explicit scope. Possible roles:
- Identity
- Appearance
- Clothing
- Environment
- Composition
- Motion
- Camera
- Audio
- Style
- Frame Anchor

A reference is a scoped constraint, not a global style source. Never transfer an observed feature from one reference to unrelated subjects or regions without an explicit mapping.

## 4. B-03 Reference Conflict Resolver (internal IR only)

When references conflict, create an internal conflict map and resolve authority before compilation.

Example internal model:
`Feature → source references → requested authority → resolved value`

Do not emit conflict tables, authority metadata, or unresolved alternatives in the final H3 prompt. If authority cannot be determined from user instructions or safe deterministic mapping, ask for clarification rather than guessing.

## 5. B-04 Retention Analysis 2.0 (pre-flight only)

Maintain an internal Reference Retention Matrix covering:
- identity
- appearance
- clothing
- pose
- motion
- environment
- audio
- camera
- frame relationship

Statuses:
`fully_preserved / partially_preserved / attribute_transfer / weak_reference / newly_generated`

Retention metadata is compiler state only. Never print these labels into the H3 physical payload.

## 6. B-05 Temporal State Ledger

Maintain per-shot state:
- subject state
- pose state
- object state
- environment state
- camera state
- audio state
- newly introduced state
- carried-over state

Represent changes incrementally: `State A → State A + Change B → State A + B + Change C`.
Never silently delete a carried-over state. If a state intentionally changes, record the change explicitly.

## 7. B-06 One Dominant Action per Shot

Each Shot has exactly one dominant action at the highest motion level.

Allowed secondary micro-actions:
- facial reaction
- breathing
- subtle hand/finger motion
- minor posture stabilization

Two equal-level major actions must be split across shots. Camera transition does not become a second subject action; it belongs to the Camera layer.

## 8. B-07 Action Vector Layer

Translate only execution-relevant actions into physical parameters:
- direction
- amplitude
- frequency
- contact
- trajectory
- speed
- acceleration/deceleration
- start state
- end state

Apply **Minimum Sufficient Physical Description**: include a physical detail only when it can materially change generation behavior. Do not maximize wording merely for apparent precision.

Abstract emotion may be retained when semantically necessary, but when a physical manifestation is required, prefer observable visual/kinematic evidence over invented psychology.

## 9. B-08 Camera Kinematics

Maintain a separate Camera State:
- camera type
- viewpoint
- framing
- movement
- amplitude
- speed
- stabilization
- depth behavior

Camera motion and subject motion must be separate clauses/layers. Avoid constructions that make one vector appear to cause the other unless causality is explicitly required.

## 10. B-09 Spatial Geography

Use adaptive spatial detail:
- Level 0: basic relative positions;
- Level 1: foreground / midground / background;
- Level 2: direction, proportion, occlusion and key spatial relationships;
- Level 3: complex 3D spatial graph — **RESEARCH ONLY**, never default.

Choose the lowest level that sufficiently constrains the scene. Do not inject numeric 2/3–1/3 grids into every prompt.

## 11. B-10 Adaptive Prompt Density

Prompt density is a budget, not a virtue.

Simple task → concise.
Multi-subject task → add only necessary spatial/continuity/camera anchors.
High-complexity motion → add execution-relevant action vectors.
Dialogue-heavy task → add timing/speech anchors only as needed.

Remove redundant synonyms, decorative adjectives, repeated reference statements, and internal metadata before final compilation.

## 12. B-11/B-12 Creative Enhancement Gate

Three modes:

**A — USER-SPECIFIED STORY:** execute faithfully; no unsolicited narrative enhancement.

**B — USER REQUESTS CREATIVE HELP:** enable Narrative Ideation.

**C — ROUGH IDEA:** proposals may be generated, but every AI proposal must remain explicitly separate from user requirements until approved.

Ideation flow:
`User Idea → Candidate A/B/C → User Selection → Prompt Compilation`.

No unapproved creative proposal may enter the final physical payload.

## 13. B-13 Environmental Reactivity

Default: `OFF`.

Enable only when:
1. user explicitly requests it;
2. environmental reaction is a core narrative/visual requirement; or
3. it materially helps execution.

Otherwise preserve background stability and avoid unnecessary micro-motion.

## 14. B-14 Visual Texture Budget

Reference-first policy:
- if a visual reference establishes style, compress redundant text texture/style descriptors;
- without a suitable reference, add only necessary visual parameters.

Avoid decorative stacks of cinematic/film/lighting adjectives that do not materially constrain output.

## 15. B-15 Three-layer separation

Maintain three independent layers:

`CAMERA`
`SUBJECT ACTION`
`ENVIRONMENT`

Relationships may be declared, but layers should not be collapsed into one long ambiguous sentence. This enables targeted debugging and PATCH operations.

## 16. B-16 PATCH Architecture

Support incremental operations:
- PATCH_CAMERA
- PATCH_ACTION
- PATCH_CHARACTER
- PATCH_ENVIRONMENT
- PATCH_AUDIO
- PATCH_TIMING
- PATCH_REFERENCE

A PATCH is applied against the current semantic state, not by blindly regenerating the entire prompt.

## 17. B-17 Minimal Semantic Change

A PATCH changes only the requested target layer.

Example:
`PATCH_CAMERA: static → slow push-in`

must preserve character, action, environment, audio, timing, and references unless the camera change necessarily invalidates one of them.

If a dependency is genuinely affected, change the minimum dependent state and record why internally.

## 18. B-18 Shot-Level Verification

For every shot assert:
- exactly one dominant action;
- subject identity/reference mapping is valid;
- camera layer is separate;
- environment layer is scoped;
- state continuity is valid;
- timestamp is legal and ordered;
- no unauthorized narrative invention;
- required mode-specific constraints are present.

A failed assertion blocks final compilation until resolved.

## 19. B-19 Global Verification

Before output assert:
- reference labels are consistent;
- reference roles do not conflict;
- timeline is monotonic and duration-valid;
- carried-over state is preserved;
- camera/action/environment are separated;
- no semantic drift or unauthorized plot exists;
- required output format is complete;
- no internal metadata leaks into final H3 payload.

## 20. B-20 Debug Trace (internal only)

Trace each generated element to one of:
- USER_REQUIREMENT
- REFERENCE
- V1-5_INHERITED_RULE
- EXTERNAL_RESEARCH
- AI_RECOMMENDATION
- USER_APPROVED_CREATIVE

Store this in internal Meta State / `[DEBUG_TRACE]`. Strip it completely before final H3 output.

## 21. B-21 Evidence / Candidate Status

Every experimental mechanism has a lifecycle:
`RESEARCH → EXPERIMENTAL → VALIDATED → PROPOSED → FROZEN`

No experimental mechanism automatically becomes a formal Skill rule.

## 22. B-22 A/B Isolation

B may use:
- V1-5 baseline knowledge;
- external Skill research;
- GPT analysis;
- Gemini analysis;
- explicit user requirements.

B must not use A's final implementation as a constraint before A/B evaluation.

## 23. B-23 Mode-Specific Optimization

Apply rules selectively by generation mode. Do not force all mechanisms into every mode.

Examples:
- Ref2VA: prioritize reference role mapping and identity/environment scope.
- I2VA / FL2VA: prioritize frame-anchor semantics and temporal continuity.
- T2VA: prioritize semantic timeline and shot/action planning.
- L2VA: prioritize the mode-specific constraints actually required by the task.

Mode-specific modules should be activated only when relevant.

## 24. B-24 Reference Asset Wiring Awareness

Maintain two separate mappings:
1. semantic Reference Role Mapping;
2. physical input/socket order.

`Image 2 = face authority` does not imply that Image 2 changes the physical socket order. Semantic labels and physical wiring must remain separately addressable.

## 25. B-25 Output Compiler Layer

The compiler must not map raw user text directly to a complex final prompt.

Required stages:
`Ideation (optional) → Semantic Plan → Reference Map → Shot Plan → Physical Execution Plan → H3 Format Compiler → Verification`

The final compiler converts internal structures into the exact expected H3-facing format and strips internal metadata.

## 26. B-26 Governing principles

Priority order:
1. User semantic intent.
2. Reference constraints.
3. H3 executability.
4. Minimum Sufficient Description.
5. Creative/compilation separation.
6. Camera/Action/Environment separation.
7. Experimental/formal rule separation.
8. Traceability, testability, and rollback.

## Final output contract

The final H3 payload must contain only information necessary to execute the approved task. It must not contain:
- conflict tables;
- retention metadata;
- debug traces;
- lifecycle labels;
- A/B governance notes;
- internal compiler explanations.

When a task cannot be compiled deterministically without guessing, ask the smallest clarification rather than inventing content.
