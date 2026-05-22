# Changelog — The 60-Second Bio

## v1.3.0

**Diagnosed weaknesses:**
1. No context adaptation — skill treated B2B corporate bios and creator bios identically despite very different platform priorities and tone requirements
2. No dual-identity handling — portfolio careers (teacher+YouTuber, engineer+newsletter writer) had no guidance on which identity leads on which platform
3. Character/word count verification was implicit — no quality gate forcing actual counting before output, leading to potential limit violations

**Changes made:**
- Added Context Sensing block between Step 1 and Step 2: four context types (B2B/corporate, Creator/B2C, Dual-identity, New/transitioning) with tone and platform-emphasis guidance for each. Inferred silently from input, not asked.
- Dual-identity handling: explicit instruction to pick the leading identity per platform based on where that audience lives, with a bridging pattern for connecting both.
- Added Quality Gate section before Output Format: explicit instruction to count characters/words for every platform version and fix violations before presenting output. No "it's 5 characters over" notes — just fix it.

**Anchor check:** Output format unchanged. Core identity preserved. Tone remains anti-generic. All 5 principles intact. Context sensing is additive — it adjusts HOW the skill executes, not WHAT it produces.

**Final stats:** 219 lines (up from 184). Net additions: quick mode, thin-credentials strategy, bio improvement diagnosis, context sensing, quality gate, expanded kill list (+5 entries), freelancer/solopreneur adaptations, hook diversity enforcement, dual-identity handling.

## v1.2.0

**Diagnosed weaknesses:**
1. No quick mode — someone asking for just a LinkedIn headline gets all 6 platforms, wasting time and feeling bloated
2. Bio improvement path underdeveloped — no guidance on diagnosing what's wrong before rewriting
3. Kill list too short — missing common AI-generated filler that the skill should catch

**Changes made:**
- Added Quick Mode section before Step 1: detects single-platform requests, delivers only what's asked for, offers full set as upsell
- Rewrote bio improvement instructions: now requires a 2-3 sentence diagnosis referencing the kill list before extracting facts and rewriting. Handles the "zero specifics" case by forcing follow-up questions
- Expanded kill list with 5 new entries: "at the intersection of", "leveraging X to drive Y", "dedicated to empowering", "innovative solutions", "dynamic professional"
- Added tc-005 (quick mode test) and tc-006 (bad bio improvement) to test bank

**Anchor check:** Output format for full runs unchanged. Quick mode is a subset, not a replacement. Core identity and tone preserved. All 5 principles intact.

## v1.1.0

**Diagnosed weaknesses:**
1. No strategy for thin credentials (career changers, pre-traction founders, new graduates)
2. Hook options could be 3 variations of the same idea instead of genuinely different techniques
3. LinkedIn headline formula assumed a company name — broke for freelancers/solopreneurs

**Changes made:**
- Added "When credentials are thin" block to Step 1 with 3 concrete strategies: prior career as proof, training as signal, lean on belief hooks
- Strengthened hook diversity requirement in Step 2 — explicit instruction that each hook MUST use a different technique, with a reader-test for genuine distinctness
- Added freelancer/solopreneur adaptation to LinkedIn Headline rules — alternative formula when there's no company name, plus fallback for missing proof points

**Anchor check:** All changes checked. Output format unchanged. Core identity unchanged. Tone remains anti-generic. All 5 principles preserved.

## v1.0.0
- Original skill as authored. 184 lines. Strong foundation covering hook generation, 6 platform formats, anti-pattern list, and output template.
