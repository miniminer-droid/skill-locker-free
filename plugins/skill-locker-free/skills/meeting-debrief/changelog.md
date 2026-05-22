# Meeting Debrief — Changelog

## v1.3.0
**Diagnosed weaknesses:**
1. No quick mode — users frequently just want "who's doing what" but the skill always produces the full 5-section output. For a lead magnet skill, demonstrating versatility matters.
2. No conversation flow — the skill never asks the user anything, even when the meeting type is genuinely ambiguous and a single question would dramatically improve extraction quality.
3. Common anti-patterns undocumented — inflating sparse meetings, upgrading discussion to decision, softening conflict, guessing owners. Paid skill loops consistently show that explicit "do NOT do this" lists outperform positive instructions alone.

**Changes:**
- Added Quick Mode section: "just the action items" produces stripped-down action table only, same extraction rigour
- Added context-gathering guidance: ask ONE question about meeting type when genuinely ambiguous, skip when obvious
- Added "Common mistakes" anti-pattern list: 6 explicit failure modes with examples
- Added tc-006 (quick mode trigger) to test bank

**Anchors check:** Quick mode is additive — full 5-section framework remains the default. Context question is gated ("only ask if truly unclear"). Anti-patterns reinforce existing principles (don't inflate, don't editorialise) with concrete examples. Core identity, tone, and output format unchanged.

## v1.2.0
**Diagnosed weaknesses:**
1. No handling of conflict/tension dynamics — the skill says "don't editorialise" but gives no guidance for factually reporting disagreement. ho-002 (sprint retro with conflict) exposed this gap entirely.
2. No classification for status updates and individual recommendations — standups and review meetings are mostly status updates, which are neither decisions nor discussions. Content gets orphaned.
3. Dual-classification items not addressed — "Need to backfill Sarah's role by end of month" is both a decision and an action item. The skill forced a choice instead of allowing both.

**Changes:**
- Added "Conflict and disagreement" guidance: report tension factually, capture both sides, note partial vs full resolution
- Added "Recommendations vs group positions" guidance: one person's opinion is not a near-decision
- Added "Status updates" guidance: fold into Discussion Points as factual background or TL;DR
- Added "Dual-classification items" guidance: list in Decisions AND create corresponding action item
- Added tc-005 (status-heavy standup) to test bank

**Anchors check:** All changes add classification guidance within Signal Detection. No structural changes to output format. Decided/discussed distinction is strengthened, not altered. Neutral tone preserved — conflict handling explicitly says "never soften, spin, or omit."

## v1.1.0
**Diagnosed weaknesses:**
1. Decision signals too narrow/formal — real meeting decisions use casual language ("Let's just do it", "alright so we're doing X") that didn't match any listed patterns
2. Sparse notes produce proportionally short output but never surface what's MISSING — the highest-value feedback for incomplete notes
3. No quality gate to catch dropped numbers, names, or dates despite the skill saying "never drop a number"

**Changes:**
- Added colloquial decision signals with guidance that group convergence = decision even without formal language
- Added "Gaps in these notes" callout for sparse input — coaches the user on what to capture next time
- Added pre-delivery check (numbers, names, dates verification) as an explicit instruction block

**Anchors check:** All changes preserve the 5-section framework, decided/discussed distinction, neutral tone, and all key principles. No structural changes to output format.

## v1.0.0
- Original skill (103 lines)
