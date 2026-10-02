# PW-OPT-001 — Version B Experimental Skill

**Status:** EXPERIMENTAL / A-B TEST ASSET
**Baseline:** V1-5 FROZEN
**Route:** B — AI Recommended Optimization
**Scope:** independent prompt-compilation experiment; not the formal Skill

## 0. Hard isolation rules

1. Never modify or replace the formal V1-5 Skill.
2. Never import Experiment A's final implementation as a B rule.
3. B may use the external Skill as research input, but B rules must be independently justified.
4. Experimental mechanisms never become formal rules automatically.
5. Final B output must be auditable, testable, and rollbackable.
6. User requirements have priority over AI proposals.
7. Historical task details, old prompts, and prior creative preferences must not silently become requirements for a new task.

## 1. Compiler pipeline

B treats prompt generation as a staged compiler:

`IDEATION -> SEMANTIC PLAN -> REFERENCE MAP -> SHOT PLAN -> PHYSICAL EXECUTION PLAN -> H3 FORMAT COMPILER -> VERIFICATION`

Only the final compiled payload is intended for the target model. Internal tables, trace metadata, conflict tables, and verification annotations must not leak into the final payload unless the target format explicitly requires them.

### 1.1 IDEATION

Creative enhancement is optional and gated. It is not automatically applied during compilation.

- Complete user story: execute faithfully.
- Explicit creative-help request: brainstorming is allowed.
- Rough idea: AI may propose candidates, but proposals must remain visibly separate from requirements until approved.

### 1.2 SEMANTIC PLAN

Normalize the user's requirements without adding unauthorized plot, action, emotion, style, or environment changes.

Classify each element as one of:

- USER_REQUIREMENT
- REFERENCE_CONSTRAINT
- INHERITED_RULE
- AI_PROPOSAL
- EXPERIMENTAL_MECHANISM

### 1.3 REFERENCE MAP

Every reference asset receives an explicit semantic role. Supported roles include:

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

A reference constrains only its declared scope. Do not infer global transfer from an incidental feature.

### 1.4 SHOT PLAN

Represent time and continuity explicitly. Each shot records its state transition and one dominant physical action.

`Shot N = carried-over state + explicit change`

### 1.5 PHYSICAL EXECUTION PLAN

Translate only execution-relevant abstractions into physical language.

Action vectors may include:

- direction
- amplitude
- frequency
- contact
- trajectory
- speed
- acceleration/deceleration
- start state
- end state

Use **Minimum Sufficient Physical Description**. Do not expand every action into unnecessary prose.

### 1.6 H3 FORMAT COMPILER

Compile the internal representation into the required H3 prompt contract for the selected generation mode.

The compiler must preserve:

- reference labels
- required fields
- mode-specific structure
- timestamps
- continuity
- camera/action/environment separation

## 2. Mode Detection

B-01 is a required preflight layer.

Detect the applicable generation mode:

- Ref2VA
- T2VA
- I2VA
- FL2VA
- L2VA

Also classify assets as reference assets, environment/style references, frame anchors, storyboard/keyframe assets, or other supported input roles.

If the mode or asset role is materially ambiguous, ask the smallest necessary clarification instead of guessing.

## 3. Reference conditioning

### B-02 Reference Role Mapping

Map every input asset to explicit roles and scope.

### B-03 Reference Conflict Resolver

Resolve conflicting references in internal Intermediate Representation only. Do not emit a conflict table or internal authority metadata into the final H3 payload.

When authority is not specified and the conflict materially changes the result, request clarification rather than inventing a priority.

### B-04 Retention Analysis 2.0

Run as a preflight inspection. Track expected retention across identity, appearance, clothing, pose, motion, environment, audio, camera, and frame relationship.

Retention metadata is internal state; it is not final prompt prose.

### B-24 Reference Asset Wiring Awareness

Keep semantic reference mapping separate from physical input order. Semantic role assignment must never silently reorder physical input sockets.

## 4. Temporal and physical controls

### B-05 Temporal State Ledger

Track per-shot:

- subject state
- pose state
- object state
- environment state
- camera state
- audio state
- newly introduced state
- carried-over state

### B-06 One Dominant Action per Shot

Each shot has one dominant action. Secondary micro-actions, breathing, facial reactions, and subtle movements may accompany it, but a second same-level dominant action must be moved to another shot.

### B-07 Action Vector Layer

Use minimum sufficient physical descriptors that materially affect execution. Avoid decorative physical detail that consumes attention without changing execution.

### B-08 Camera Kinematics Layer

Maintain a separate camera state containing viewpoint, framing, movement, amplitude, speed, stabilization, and depth behavior. Do not linguistically fuse camera transforms with subject motion when separation is possible.

## 5. Spatial and attention controls

### B-09 Spatial Geography Layer

Adapt spatial detail to scene complexity:

- L0: basic relative positions
- L1: foreground / midground / background
- L2: ratios, direction, occlusion, and explicit spatial relationships
- L3: complex 3D spatial graphs — **RESEARCH ONLY**, not part of the default B implementation

### B-10 Adaptive Prompt Density

Allocate prompt detail according to task complexity. More detail is justified only when it improves execution. The compiler should prefer minimum sufficient information over maximum description.

### B-13 Environmental Reactivity Controller

Default: OFF.

Enable only when the user explicitly requests environmental motion, the environment is central to the action/story, or the environmental response materially improves execution.

### B-14 Visual Texture Budget

Prefer reference-driven visual identity. When a reference already establishes appearance/style, suppress redundant texture and cinematic modifier stacking. Without a sufficient reference, add only necessary visual parameters.

## 6. Creative gating

### B-11 Creative Enhancement Gating

Separate user requirements from AI proposals. AI proposals never become requirements without user approval.

### B-12 Narrative Creative Enhancement

Keep brainstorming outside prompt compilation:

`User Idea -> Brainstorm -> Candidate A/B/C -> User Approval -> Compilation`

No automatic Pacing Arc or narrative escalation is injected into a user-specified story.

## 7. Structural separation and patching

### B-15 Camera / Subject / Environment separation

Maintain three independently addressable layers:

- CAMERA
- SUBJECT ACTION
- ENVIRONMENT

Relationships are allowed, but do not collapse all three into one opaque sentence when separable structure improves correctness and debugging.

### B-16 PATCH Architecture

Support targeted patch operations conceptually:

- PATCH_CAMERA
- PATCH_ACTION
- PATCH_CHARACTER
- PATCH_ENVIRONMENT
- PATCH_AUDIO
- PATCH_TIMING
- PATCH_REFERENCE

### B-17 Minimal Semantic Change

A patch changes only the requested target layer. Untargeted layers remain locked unless the requested change logically requires a dependent update, which must be explicitly recorded.

## 8. Verification

### B-18 Shot-Level Verification

For every shot verify:

- exactly one dominant action
- subject/reference role correctness
- camera correctness
- environment correctness
- state continuity
- valid timestamp
- no unauthorized narrative addition

### B-19 Global Verification

Before output verify:

- reference labels and roles are consistent
- no invented references
- timestamps increase and fit duration
- state continuity is coherent
- camera/action separation is preserved
- no unauthorized plot or creative invention exists
- output format and required fields are correct
- no internal commentary leaks into the final payload

### B-20 Debug Trace

Maintain source attribution internally for each meaningful compiled element:

- USER_REQUIREMENT
- REFERENCE
- V1-5_INHERITED_RULE
- EXTERNAL_RESEARCH
- AI_RECOMMENDATION
- USER_APPROVED_CREATIVE

Debug trace must be stripped from the final H3 payload.

## 9. Governance

### B-21 Evidence / Candidate Status

Every experimental mechanism carries a lifecycle state:

- RESEARCH
- EXPERIMENTAL
- VALIDATED
- PROPOSED
- FROZEN

### B-22 A/B Experimental Isolation

B is independent from A until evaluation. A's implementation must not become a hidden B constraint.

### B-23 Mode-Specific Optimization

Apply mechanisms according to generation mode rather than forcing every enhancement into every mode.

Examples:

- Ref2VA: reference mapping and role isolation receive priority.
- I2VA / FL2VA: frame and temporal continuity receive priority.
- T2VA: timeline and shot orchestration receive priority.

### B-26 Overall charter

The B implementation follows this priority order:

1. User semantic fidelity
2. Reference constraints
3. Target-model executability
4. Minimum sufficient description
5. Creative/compilation separation
6. Camera/action/environment separation
7. Experimental/formal rule separation
8. Traceability, testability, and rollback

## 10. Explicit non-goals

B does not:

- alter the formal V1-5 baseline;
- silently adopt A's final rules;
- guarantee exact visual identity or generation outcomes;
- force complex spatial graphs;
- inject narrative escalation into specified stories;
- expose internal IR, retention matrices, conflict tables, or debug traces to the target model;
- treat experimental mechanisms as validated merely because they are theoretically plausible.

## 11. Experimental status

This file is the **B experimental skill specification**, not the production Skill. It must be tested against the same task/material/parameters used for A before any promotion decision.
