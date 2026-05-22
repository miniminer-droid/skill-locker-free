# Anti-Slop Checker — Changelog

## v1.1.0 — 2026-05-15

**Improvement cycle**: Karpathy Loop runs 001-003
**Test cases**: 6 active + 2 held-out

### What improved
- Academic writing no longer false-flagged as AI (ho-002: 5/10 → 3/10)
- Added context calibration system — skill now adjusts severity based on content type (academic, legal, corporate, ESL, SaaS/marketing)
- Domain-specific AI tells added (SaaS/tech: "scalable", "enterprise-grade", "end-to-end", "data-driven", "ecosystem", etc.)
- Score calibration table added with anchor examples for each score range
- Personal slop fingerprint now requires specific citations from the user's text, not generic category descriptions

### Evidence
- ho-002 (academic prose): 5/10 → 3/10 (correctly recognises academic vocabulary as register-appropriate)
- tc-006 (good writing): stable at 0/10 across all 3 runs (no regressions)
- tc-005 (mixed human/AI): 4/10 with correct paragraph-level attribution (strongest output in the battery)
- ho-001 (ESL writer): 7/10 — known limitation, skill does not yet distinguish ESL patterns from AI patterns

### What changed in the skill
1. Added "Context calibration" section before Pass 1 with guidance for academic, legal, corporate, ESL, and SaaS/marketing registers
2. Added score calibration table with anchor examples (what a 3 looks like vs a 6 vs a 9)
3. Added domain-specific AI tells to Category A (scalable, enterprise-grade, end-to-end, data-driven, forward-thinking, ecosystem, best-in-class, next-generation, turnkey, actionable insights)
4. Tightened fingerprint section to require specific text citations rather than generic category descriptions

### Known limitations
- ESL writing may be over-scored. The skill does not yet reliably distinguish non-native English patterns from AI patterns. Both produce similar surface-level features (simple structure, limited vocabulary range, generic phrasing). Future iteration should address this.

---

## v1.0.0 — 2026-05-15

**Initial release**

First version of the Anti-Slop Checker. 5-category detection system (Hollow Intensifiers, Filler Transitions, Performative Enthusiasm, Structural Tells, Hedging & Disclaimers), 3-pass analysis (phrase detection, voice/rhythm analysis, full rewrite), slop scoring, and personal slop fingerprint.

Tested against 6 test cases: obvious AI LinkedIn post, moderate AI blog intro, corporate email, SaaS product description, mixed human/AI text, and genuinely good human writing. Passed 5/6 (over-scored moderate AI text at 8/10, expected 5-7).
