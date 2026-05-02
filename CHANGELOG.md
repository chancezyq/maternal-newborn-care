# Changelog

All notable changes to `maternal-newborn-care` will be documented in this file.

The goal of this changelog is not just version vanity. It records how the skill evolved, what was added, and what kinds of risks or quality issues each change was meant to address.

---

## [0.1.0] - 2026-05-02

Initial structured skill package for postpartum and newborn home care support.

### Added
- Created `SKILL.md` as the main skill definition.
- Defined skill purpose: postpartum 0–42 day maternal-newborn care support for mothers, newborns, and caregivers.
- Added risk triage model with three levels:
  - Green: home observation
  - Yellow: contact clinician today
  - Red: urgent / emergency evaluation
- Added output behavior rules:
  - lead with risk judgment
  - provide actionable next steps
  - specify observation points
  - define escalation boundaries
- Added tone and safety guidance for high-risk and emotionally sensitive cases.

### Templates
- Added core response templates:
  - `templates/core/answer-normal.md`
  - `templates/core/answer-urgent.md`
  - `templates/core/daily-summary.md`
- Added scenario templates:
  - `templates/scenarios/lochia.md`
  - `templates/scenarios/breast-pain-mastitis.md`
  - `templates/scenarios/jaundice.md`
  - `templates/scenarios/poor-feeding-low-urine.md`
  - `templates/scenarios/fever.md`
  - `templates/scenarios/postpartum-mood.md`

### References
- Added maternal red flag reference:
  - `references/red-flags-mother.md`
- Added newborn red flag reference:
  - `references/red-flags-newborn.md`
- Added lightweight logging schema reference:
  - `references/logging-schema.md`

### Testing and QA
- Added acceptance cases:
  - `TESTCASES.md`
- Added sample dialogue references:
  - `EXAMPLES.md`
- Added manual execution guide:
  - `RUNBOOK.md`
- Added scoring rubric:
  - `SCORING.md`
- Added gold responses for boundary stress cases:
  - `BOUNDARY_GOLD_RESPONSES.md`
- Added common failure-mode guide:
  - `PITFALLS.md`
- Added regression workflow:
  - `REGRESSION_CHECKLIST.md`

### Documentation
- Added human-facing package overview:
  - `README.md`
- Organized template directory into:
  - `templates/core/`
  - `templates/scenarios/`
- Updated README to reflect final folder structure.

### Design Notes
- Centered the skill around household decision support rather than fake diagnostic certainty.
- Prioritized maternal-newborn linked problems instead of treating mother and baby as isolated tracks.
- Explicitly strengthened handling for:
  - minimized-risk language from users
  - emotional crisis / self-harm risk
  - delayed-care resistance
  - incomplete or contradictory descriptions

### Known Gaps / Next Steps
- Add more scenario templates for additional postpartum and newborn issues.
- Consider structured summary output formats for handoff to clinics.
- Consider caregiver task delegation templates.
- Consider finer-grained guidance by postpartum stage and newborn age window.

---

## Versioning Notes

This skill is still in an early design-and-validation phase.

Suggested future versioning approach:
- `0.1.x` for prompt, safety, and template refinements
- `0.2.x` for expanded scenario coverage or structured outputs
- `0.3.x` for caregiver workflows, logging integrations, or richer summaries
- `1.0.0` only after repeated regression passes and stable real-world usage patterns
