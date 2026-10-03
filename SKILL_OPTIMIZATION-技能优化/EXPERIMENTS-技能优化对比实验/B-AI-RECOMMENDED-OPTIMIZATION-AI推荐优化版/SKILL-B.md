# PW-OPT-001 / B — AI 推荐优化实验版

Status: EXPERIMENTAL / DESIGNED / NOT H3-VALIDATED / NOT FORMAL.

This B skill is the independent GPT + Gemini reconstruction. V1-5 remains FROZEN. Experiment A is read-only and does not become a rule source for B before testing.

## Compiler pipeline

USER INPUT → IDEATION / INTENT GATE → MODE DETECTION → SEMANTIC PLAN → REFERENCE MAP + CONFLICT RESOLUTION → RETENTION / PRE-FLIGHT → SHOT PLAN + TEMPORAL STATE LEDGER → PHYSICAL EXECUTION PLAN → DENSITY BUDGET + COMPRESSION → H3 FORMAT COMPILER → SHOT VERIFICATION → GLOBAL VERIFICATION → FINAL H3 PAYLOAD.

Internal IR, Conflict Tables, Retention Matrices, Debug Trace and Evidence metadata are compiler state and must not leak into the final H3 payload.

## B-01 Mode Detection

Detect Ref2VA, T2VA, I2VA, FL2VA, L2VA. Classify supplied assets as reference, environment/style, first-frame, last-frame, or storyboard/keyframe. Do not infer a frame anchor merely because an image exists; ask the minimum necessary clarification when role is ambiguous.

## B-02 Reference Role Mapping

Map each asset explicitly to Identity, Clothing, Environment, Composition, Motion, Camera, Audio, Style and/or Frame Anchor. Multiple roles are allowed, but scope must be explicit. Reference constraints are scoped, not global style pollution.

## B-03 Reference Conflict Resolver

Resolve conflicting references in internal IR. User-specified authority wins; existing V1-5 mappings outrank guesses. If unresolved, ask. Conflict tables never enter the final H3 payload.

## B-04 Retention Analysis 2.0

Use an internal Reference Retention Matrix as pre-flight inspection. Track identity, appearance, clothing, pose, motion, environment, audio, camera and frame relationship with statuses fully_preserved, partially_preserved, attribute_transfer, weak_reference and newly_generated. Do not emit retention metadata by default.

## B-05 Temporal State Ledger

Track subject, pose, object, environment, camera, audio, newly introduced and carried-over state per Shot. Use additive state inheritance; established state does not disappear without an explicit change.

## B-06 One Dominant Action per Shot

One same-level dominant action per Shot. Micro-actions, breathing and facial reactions may coexist. Split competing major actions into separate Shots/time ranges.

## B-07 Action Vector Layer

Translate execution-critical actions into direction, amplitude, frequency, contact, trajectory, speed, acceleration/deceleration, start and end state. Apply Minimum Sufficient Physical Description: only information that can change execution belongs in the final payload.

## B-08 Camera Kinematics

Maintain a separate Camera State: type, viewpoint, framing, movement, amplitude, speed, stabilization and depth behavior. Compile camera and subject action separately to reduce semantic coupling.

## B-09 Spatial Geography

Adaptive levels: L0 basic positional relations; L1 foreground/midground/background; L2 direction, proportion and occlusion; L3 complex 3D spatial graph is RESEARCH ONLY. Do not force numeric ratios unless they improve execution.

## B-10 Adaptive Prompt Density

Use a Prompt Density Budget. Simple tasks stay concise; complex spatial tasks receive necessary spatial/continuity/camera anchors; difficult motion receives necessary action vectors; dialogue-heavy tasks receive timing/speech information. Avoid attention overcrowding.

## B-11 Creative Enhancement Gating

Separate USER-SPECIFIED STORY, USER REQUESTS CREATIVE HELP and ROUGH IDEA. AI proposals are never silently promoted to user requirements.

## B-12 Narrative Creative Enhancement

Keep ideation separate from compilation: User Idea → Brainstorm → Candidate A/B/C → User Selection → Prompt Compilation. Only confirmed ideas enter the final payload.

## B-13 Environmental Reactivity

Default OFF. Enable only when explicitly requested, story-critical, or execution-helpful. Otherwise prefer background stability.

## B-14 Visual Texture Budget

Prefer Reference over redundant prose. With a strong visual reference, compress extra texture/lighting/film-look descriptors. Without a reference, add only necessary visual parameters.

## B-15 Three-layer decoupling

Keep CAMERA, SUBJECT ACTION and ENVIRONMENT as separate prompt layers. Relationships may be represented, but avoid unnecessary long mixed sentences.

## B-16 PATCH Architecture

Support PATCH_CAMERA, PATCH_ACTION, PATCH_CHARACTER, PATCH_ENVIRONMENT, PATCH_AUDIO, PATCH_TIMING and PATCH_REFERENCE. A patch identifies its target layer and requested change.

## B-17 Minimal Semantic Change

A patch changes only the user-specified layer. Non-target layers default to PRESERVE. Do not use a local patch as an excuse to rewrite the whole prompt.

## B-18 Shot-Level Verification

Before emitting each Shot, assert dominant-action uniqueness, subject, reference, camera, environment, state continuity, timestamp validity and absence of unauthorized new plot. Prefer local repair over global rewrite.

## B-19 Global Verification

Verify reference labels/roles, timeline order/duration/continuity, camera-action separation, semantic fidelity/no unauthorized invention, exact output schema and required fields.

## B-20 Debug Trace

Internally trace each prompt element to User Requirement, Reference, V1-5 inherited rule, External Skill research, AI recommendation or User-approved creative addition. Strip Debug Trace from final H3 payload.

## B-21 Evidence / Candidate Status

Lifecycle: RESEARCH → EXPERIMENTAL → VALIDATED → PROPOSED → FROZEN. No experiment becomes a formal rule automatically.

## B-22 A/B Isolation

B inputs are V1-5 Frozen, raw external research, GPT independent analysis, Gemini independent review and explicit user requirements. A's final implementation is not a B constraint before testing.

## B-23 Mode-Specific Optimization

Ref2VA emphasizes reference mapping/retention/wiring; I2VA emphasizes frame continuity/state; FL2VA emphasizes first/last frame relationships; L2VA emphasizes end-frame relationship; T2VA emphasizes timeline/shot/action/camera. Do not load every enhancement into every mode.

## B-24 Asset Wiring Awareness

Keep semantic Reference Mapping separate from physical socket order. Image 1 maps to physical input 1, etc., while semantic responsibility remains an independent mapping.

## B-25 Output Compiler

Compile through IDEATION → SEMANTIC PLAN → REFERENCE MAP → SHOT PLAN → PHYSICAL EXECUTION PLAN → H3 FORMAT COMPILER → VERIFICATION. Do not jump directly from natural language to a complex final payload.

## B-26 Constitution

User semantics first; reference constraints first; H3 executability first; minimum sufficient description; creative/compilation separation; camera/action/environment separation; experimental/formal separation; traceable, testable and reversible additions; no historical-context invention; no V1-5/A/formal-skill modification without user approval.

## Final Ref2VA interface

When compiling to the project's Ref2VA payload, preserve the existing six-field interface: subject_definitions, summary, retention_analysis, detailed_description, overall_soundscape, non_diegetic_music. Internal IR/debug/verification metadata must not contaminate it.
