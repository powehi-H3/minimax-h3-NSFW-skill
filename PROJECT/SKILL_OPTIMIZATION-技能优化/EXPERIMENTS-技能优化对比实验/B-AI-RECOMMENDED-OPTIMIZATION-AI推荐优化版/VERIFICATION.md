# PW-OPT-001｜Version B Verification & Governance

状态：EXPERIMENTAL

## Shot-Level Contract

For every shot:
- [ ] exactly one dominant action
- [ ] secondary micro-actions are subordinate
- [ ] subject/reference roles are resolved
- [ ] camera state is independent
- [ ] environment scope is explicit when needed
- [ ] temporal state is carried forward correctly
- [ ] timestamp is monotonic and valid
- [ ] no unauthorized story/action invention

## Global Contract

- [ ] mode is correctly detected
- [ ] semantic Reference Map is internally consistent
- [ ] physical asset/socket order is separate from semantic roles
- [ ] conflicts are resolved before H3 compilation
- [ ] retention is checked internally
- [ ] prompt density is appropriate to task complexity
- [ ] Camera / Subject Action / Environment are separated
- [ ] PATCH changes only requested state
- [ ] no internal IR/metadata leaks into final payload
- [ ] output format is complete and deterministic

## Lifecycle

New mechanisms must be marked:

`RESEARCH` → `EXPERIMENTAL` → `VALIDATED` → `PROPOSED` → `FROZEN`

No mechanism is promoted merely because it sounds plausible.

## A/B isolation

B is evaluated against A under identical raw task input and asset conditions. Before evaluation:
- A final rules do not constrain B;
- B final rules do not constrain A;
- V1-5 remains frozen;
- neither experiment can modify the formal Skill.

## Debug trace

Every compiled element should be traceable internally to:
`USER_REQUIREMENT | REFERENCE | V1-5_INHERITED_RULE | EXTERNAL_RESEARCH | AI_RECOMMENDATION | USER_APPROVED_CREATIVE`

Trace is removed from the H3-facing payload.

## Promotion gate

A B rule may be considered for formal adoption only after:
1. A/B prompt generation by Grok under identical conditions;
2. H3 rendering comparison;
3. evidence recorded against agreed evaluation dimensions;
4. review of regressions and debug cost;
5. explicit user approval.

Until then, B remains experimental.
