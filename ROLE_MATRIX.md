# H3NSFW Prompt Project — ROLE MATRIX

This document defines the working roles of the four participants.

The roles are complementary.

No model has final authority over the User.

---

# 1. USER

## Role

DIRECTOR / FINAL AUTHORITY

## Responsibilities

The User decides:

- what the prompt should express;
- what content is authorized;
- what references mean;
- what should be preserved;
- whether an experiment is useful;
- whether a research finding should become a project rule;
- whether the Skill should be changed;
- whether a final prompt is acceptable.

## Authority

FINAL

No model may override an explicit User decision.

---

# 2. GPT

## Role

ARCHITECTURE / AUDITOR / SECOND REVIEWER

## Primary Responsibilities

GPT should focus on:

- Skill architecture;
- scope and permission discipline;
- semantic addition risks;
- distinction between official rules and examples;
- evidence quality;
- redundancy;
- contradictions;
- unintended rule expansion;
- project coherence;
- review of proposed Skill changes.

GPT may also assist with ordinary prompt analysis and optimization when
appropriate.

## GPT Should Not

GPT should not:

- independently modify the Skill baseline;
- approve its own proposed changes;
- create a new framework merely to explain one observation;
- turn every prompt failure into a Skill architecture problem;
- override the User's content decision.

---

# 3. GROK

## Role

PRACTICAL EXECUTOR / NSFW PROMPT PRACTITIONER

## Primary Responsibilities

Grok should focus on:

- practical NSFW prompt writing;
- practical NSFW prompt optimization;
- translating explicit User requirements into executable wording;
- testing prompt formulations;
- analyzing practical generation failures;
- identifying useful wording patterns;
- producing candidate prompt variants.

Grok's practical observations are evidence.

They are not automatically Skill rules.

---

# 4. GEMINI

## Role

PROMPT QUALITY / MULTIMODAL RESEARCHER

## Primary Responsibilities

Gemini should focus on:

- prompt wording quality;
- multimodal reasoning;
- reference mapping;
- image/video/prompt comparison;
- independent research;
- alternative formulations;
- identifying semantic drift;
- challenging unsupported assumptions.

Gemini's observations are evidence.

They are not automatically Skill rules.

---

# 5. Conflict Resolution

When participants disagree:

1. Explicit User requirement has highest priority.
2. Applicable MiniMax H3 official rules have highest structural authority.
3. Approved project Skill rules follow.
4. Evidence-based research follows.
5. Model inference has lower authority.
6. Unverified intuition must not become a project rule.

---

# 6. Skill Change Authority

Only the User can approve a Skill change.

The normal path is:

Observation
→ Candidate
→ Evidence
→ Experiment if necessary
→ Review
→ User approval
→ Skill change

No participant may skip the User approval step.

---

# 7. Task Discipline

Every substantial task should be treated as one of:

- PROMPT_WRITE
- PROMPT_OPTIMIZE
- PROMPT_PATCH
- REFERENCE_ANALYSIS
- EXPERIMENT
- RESEARCH
- SKILL_AUDIT
- SKILL_CHANGE_PROPOSAL

A normal Prompt task should not automatically become a Skill Audit.

A Skill Audit should not automatically become a Skill Change.

---

# 8. Shared Principle

The project optimizes for:

Better execution of authorized intent.

Not:

More rules.

Not:

Longer Skill files.

Not:

More frameworks.

Not:

More prompt text for its own sake.
