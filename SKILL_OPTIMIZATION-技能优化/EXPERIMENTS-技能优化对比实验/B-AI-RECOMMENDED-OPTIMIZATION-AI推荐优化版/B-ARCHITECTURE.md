# PW-OPT-001 Version B — Architecture

## Status

EXPERIMENTAL. V1-5 remains FROZEN. Experiment A and B remain isolated.

## Compiler architecture

```text
USER INPUT
   |
   v
[IDEATION GATE]
   |
   v
[SEMANTIC PLAN]
   |
   +--> user requirements
   +--> reference constraints
   +--> inherited rules
   +--> AI proposals (not requirements until approved)
   |
   v
[MODE DETECTION]
   |
   v
[REFERENCE MAP]
   |
   +--> role mapping
   +--> conflict resolution (internal IR)
   +--> retention preflight (internal)
   +--> physical wiring map
   |
   v
[SHOT PLAN]
   |
   +--> temporal state ledger
   +--> one dominant action / shot
   +--> camera state
   +--> spatial level L0-L2
   |
   v
[PHYSICAL EXECUTION PLAN]
   |
   +--> minimum sufficient action vectors
   +--> state carry-over
   +--> environmental reactivity gate
   +--> visual texture budget
   |
   v
[H3 FORMAT COMPILER]
   |
   +--> mode-specific output
   +--> required fields
   +--> reference labels
   |
   v
[VERIFICATION]
   |
   +--> shot-level checks
   +--> global checks
   +--> debug trace retained internally
   |
   v
[FINAL H3 PAYLOAD]
```

## Internal vs external boundary

The following remain internal and must not leak into the final model payload unless the target format explicitly requires them:

- Reference Conflict Table
- Retention Matrix
- Debug Trace
- Candidate Status metadata
- A/B governance metadata
- Compiler stage labels

The final payload should contain only model-relevant instructions and required format fields.

## Patch architecture

Patch requests should be represented as targeted transformations rather than whole-prompt rewrites:

```text
PATCH_CAMERA
PATCH_ACTION
PATCH_CHARACTER
PATCH_ENVIRONMENT
PATCH_AUDIO
PATCH_TIMING
PATCH_REFERENCE
```

Each patch declares its target layer and preserves all unrelated layers.

## Complexity adaptation

Prompt density and spatial detail are adaptive. Complexity increases only when it changes model execution. L3 spatial graphs remain research-only.

## Mode adaptation

Mode-specific compiler behavior is mandatory. A rule should not be emitted merely because it exists in B; it must be relevant to the detected H3 mode.
