# PW-OPT-001 Version B — Verification Contract

## Status

EXPERIMENTAL. This contract validates B internally before Grok performs the A/B generation comparison.

## Shot-level contract

For every shot:

- [ ] exactly one dominant action
- [ ] secondary micro-actions do not become competing dominant actions
- [ ] subject identity/reference roles are consistent
- [ ] camera state is explicit and separated from subject action
- [ ] environment state is consistent
- [ ] temporal state is inherited or explicitly changed
- [ ] timestamp is valid and monotonic
- [ ] no unauthorized narrative event is introduced

## Reference contract

- [ ] every reference asset has a declared role
- [ ] semantic role mapping is separate from physical input order
- [ ] conflicts are resolved internally before compilation
- [ ] unresolved material conflicts trigger clarification rather than guessing
- [ ] retention inspection is internal only
- [ ] no reference metadata leaks into final payload

## Density contract

- [ ] every sentence has execution value or required format value
- [ ] redundant visual modifiers are removed when reference imagery already establishes them
- [ ] action vectors contain only execution-relevant dimensions
- [ ] spatial detail is proportional to scene complexity
- [ ] L3 spatial graph remains research-only

## Creative contract

- [ ] user requirements and AI proposals are distinguishable
- [ ] creative enhancement is gated
- [ ] user-specified story is not silently rewritten
- [ ] unapproved brainstorming never reaches final payload

## Patch contract

- [ ] patch target is explicit
- [ ] non-target layers remain unchanged
- [ ] dependent changes are explicitly recorded
- [ ] patch does not trigger an unnecessary full semantic rewrite

## Global output contract

- [ ] mode-specific structure is correct
- [ ] reference labels are consistent
- [ ] timeline is valid
- [ ] camera/action/environment remain separable
- [ ] required fields are present
- [ ] internal IR, debug trace, retention matrix, conflict tables and governance metadata are removed
- [ ] no unauthorized creative invention remains
- [ ] B status remains EXPERIMENTAL

## Promotion rule

Passing this verification does not promote B to production. Promotion requires the controlled A/B test using identical task inputs and the user's final approval.
