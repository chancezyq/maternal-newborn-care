# Changelog

All notable changes to `maternal-newborn-care` will be documented in this file.

The goal of this changelog is not just version vanity. It records how the skill evolved, what was added, and what kinds of risks or quality issues each change was meant to address.

---

## [0.2.0] - 2026-05-03

Coverage gap fill: extended `SKILL.md` to cover the day-to-day household care surface that 0.1.0 left thin (cleaning, postpartum daily life, household coordination, environmental safety, folk-remedy avoidance, and structured handoff summaries).

### Added — Scope expansion
- 新生儿日常清洁 (洗澡、脐带、红屁屁、托抱、抚触、奶具/吸奶器消毒、宝宝衣物)
- 产妇日常生活护理 (洗头洗澡、通风/空调/保暖、下床活动、剖宫产/顺产差异、产后出汗)
- 母婴用品准备和家庭环境安全 (室温、安全睡眠、洗手卫生、探访、烟味/宠物/烫伤/跌落)
- 家属照护分工、夜间值班、红旗症状决策人安排
- 每日交接式摘要 (家属轮班、给医生看)
- 识别和劝阻常见错误做法/民间偏方

### Added — New templates
- **Template H — Daily Handoff Summary**: per-day handoff format. Mother and baby tracked separately; each section ends with "明日重点观察" and "今晚/明天安排". Sits between Template C (loose summary) and Template D (minimal log) in structure.

### Added — New interaction patterns
- **Pattern 15 — 新生儿日常清洁护理**: bathing, cord care, diaper rash, bottle/pump sterilization, clothes washing, holding/支撑头颈, infant massage safety boundaries (avoid 摇晃婴儿综合征).
- **Pattern 16 — 产妇日常生活护理**: hair-washing/showering myth-busting, room temperature/airflow, getting out of bed, vaginal vs cesarean differences, postpartum sweating without 捂汗.
- **Pattern 17 — 家庭照护者分工**: night shift, day primary caregiver, log keeper, red-flag decision maker, shopping, cooking, mother-rest protection, emotional support — explicit role list rather than "everyone help out".
- **Pattern 18 — 母婴用品和环境安全**: minimal supply list, room conditions, safe sleep, handwashing, visitor/smoke/pet management, scald/fall hazards.

### Added — New top-level section
- **Common Pitfalls — 常见错误做法 / 民间偏方避坑清单**: explicit refusal list with mechanism + safer alternative for: 暴力通乳, 浓油汤发奶, 挤新生儿乳房, 晒太阳退黄, 喂糖水/草药水退黄, 给新生儿喂水, 自行调奶粉浓度, 频繁换奶粉, 酒精擦浴, 捂汗退烧, 挑马牙/螳螂嘴, 剃胎毛, 银饰擦口腔白斑, "月子不能洗头洗澡", 月子捂热, 红糖水当水/月子酒, 过紧绑腹带. Each entry pairs ❌ wrong practice with ✅ correct alternative. Closes with escalation rule: if folk practice has already caused possible harm, treat as red flag.

### Updated
- **Scope** section extended with the 6 new coverage areas.
- **Answer Self-Check** updated with new check items for Pattern 15–18, Template H, and folk-remedy detection.

### Design Notes
- Deliberately did **not** add 月嫂 service boundaries, 月嫂合同清单, or 月嫂 role-judgement templates. Scope stayed on family-led 0–42 day home care, not yuesao service definition.
- Folk-remedy section is paired with mechanism-level reasons because "don't do that" without "why" tends to lose against family elders. Each entry gives a concrete failure mode (lactation tissue damage, electrolyte dilution, alcohol absorption through skin, etc.).
- Pattern 17 explicitly says "no yuesao / no live-in elder is fine" so the skill works for solo or small-family households, not just well-resourced ones.
- High-risk escalation behavior unchanged: red-flag rules in Safety Rules and Risk Triage Reference still take precedence over any of the new daily-life advice.

### Tested
- 6 representative role-play queries covering all 6 new areas — all routed to correct pattern/template with concrete actions.
- 1 high-risk query (新生儿发热 + 用酒精擦浴退烧) — confirmed red-flag escalation still fires; folk-remedy refusal layered on top, not in place of, "立即就医".

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
