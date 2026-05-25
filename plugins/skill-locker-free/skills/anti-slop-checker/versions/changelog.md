# Anti-Slop Checker — Changelog

## v1.2.0 — 2026-05-23

**Improvement cycle**: Karpathy Loop run 004
**Test cases**: 7 active + 2 held-out (ho-001 promoted to tc-007; ho-003 added)

### What improved
- ESL writing is now correctly identified instead of false-flagged as AI (tc-007: 7/10 → 4/10)
- Added an explicit Pass 0 "Origin diagnostic" that runs before the existing phrase / voice / rewrite passes
- Output now includes an "Origin assessment" line so the model commits to ESL vs AI vs native-formal before scoring
- No regression on obvious-AI (tc-001 still scores 10/10) or genuinely good writing (tc-006 still scores 1/10)

### Evidence (run-004)
- tc-007 (ESL business email — the documented v1.1.0 limitation): 7/10 → **4/10**, with the origin correctly identified as ESL and 5 specific ESL markers cited (textbook opener "I am writing to inform you", preposition mismatch "help businesses to improve", "very + adjective" stacking, present-perfect-continuous quirk, formal textbook closing). Rewrite reframed as "naturalising for native readers" rather than "removing AI tells."
- tc-001 (obvious AI LinkedIn post — regression check): stable at **10/10**, all five AI categories still flagged.
- tc-006 (genuinely good human writing — regression check): stable at **1/10**, no rewrite produced, strengths cited from the actual text.

### What changed in the skill
1. **Added Pass 0: Origin diagnostic** before Pass 1. Uses six positive ESL markers (textbook openers, article irregularities, preposition mismatches, L1-translation constructions, verb-tense quirks, absence of idiomatic flourishes) rather than the absences-based heuristics in v1.1.0.
2. **Added an explicit decision rule** with three branches: 2+ ESL markers → cap score at 5 + reframe as naturalisation; 0-1 markers + uniform polish → proceed as AI; uncertain → ask the user one line before scoring.
3. **Removed the buried "Non-native English speakers" paragraph** from the context-calibration section, replaced by the structured Pass 0 above.
4. **Added "Origin assessment" line** to the output format so the model commits to a classification before producing a score.

### Why the v1.1.0 fix wasn't enough
v1.1.0 added an ESL note to the calibration prose but described it as "may indicate ESL" buried mid-paragraph, with the listed differentiator being *inconsistent vocabulary* — which is actually wrong, since well-educated ESL writers in business contexts are quite consistent. v1.2.0 replaces this with positive present-tense markers (article irregularities, preposition mismatches, etc.) that an AI model can actively scan for, plus a hard score cap so the model can't "feel" its way to a high score on text that has been correctly diagnosed as ESL.

### Known limitations
- The diagnostic is currently calibrated for English-as-second-language writers from European, Latin American, and South Asian backgrounds. Other L1 backgrounds may produce different marker patterns that aren't yet on the list. Future iteration could expand the marker set if real-world misses appear.
- Translated prose (where a native speaker has run their writing through a translator tool) may not match either profile cleanly. Currently this would likely route through the "uncertain → ask" branch, which is the right outcome.

---

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
