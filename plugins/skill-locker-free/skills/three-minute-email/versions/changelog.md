# Changelog -- The 3-Minute Email

## v1.1.0

**Diagnosed weaknesses:**
1. Near-zero-context inputs (e.g., "just write me an email") had no structured handling -- the one-question rule couldn't extract enough information
2. Follow-up emails with thin context produced generic or fabricated "new value" additions
3. Dual-version trigger was purely subjective ("tricky, high stakes") with no concrete criteria

**Changes:**
- Added Step 0: minimum viable context gate (who + what + desired outcome). If all three are missing, asks for them in one structured prompt. If one is missing, asks only for that piece. Prevents both generic output and unnecessary interrogation.
- Added thin-context fallback to Follow-up framework: when user hasn't provided new value, reframe the original pitch rather than fabricating details (use a different angle, add time-bound element, or try a lighter ask).
- Replaced vague dual-version trigger with four explicit criteria: bad news + ongoing relationship, user signals relationship matters, email involves money/deadlines/performance, user sounds unsure about directness.
- Updated "What you never do" section to align clarifying-question rule with new Step 0 logic.

**Anchor check:** All changes verified against anchors.md. Output format unchanged. Core identity preserved. Tone unchanged. Key principles (150-word target, one ask, no filler) intact.

## v1.2.0

**Diagnosed weaknesses:**
1. No pre-delivery self-check -- emails could pass all framework rules but still contain placeholder language, invented details, or buried asks
2. Request framework failed on compassion/policy requests (e.g., deadline extension due to family emergency) where "why it benefits them" doesn't apply
3. "Why this works" section lacked specificity -- tended toward generic advice instead of teaching the specific strategic choice

**Changes:**
- Added Step 4: silent self-check before delivery. Three checks: no unauthorized assumptions (flag unknowns with [brackets]), no placeholder language (cut anything that could appear in any email), ask is unmissable within 5 seconds of reading.
- Added compassion/policy exception to Request framework: when the ask is based on extenuating circumstances, replace "why it benefits them" with brief honest context. One sentence. Don't overshare.
- Sharpened "Why this works" guidance with explicit good/bad examples and instruction to name the specific framework used and explain why it fits THIS situation.
- Added tc-005 to test bank (lease/pet request -- tests compassion/policy variant of request framework).
- Renumbered steps: length check is now Step 5, format is Step 6.

**Anchor check:** Output format (Subject + body + "Why this works") unchanged. Core identity preserved -- still fast and opinionated. Tone still direct and anti-filler. 150-word target and one-ask rule intact. Self-check is silent, so it doesn't slow the user experience.

## v1.3.0

**Diagnosed weaknesses:**
1. Subject line guidance was one-size-fits-all -- didn't address how subject lines differ by email type (follow-ups need thread references, bad news needs neutral framing, cold outreach needs curiosity without clickbait)
2. No reply vs. new thread guidance -- the skill assumed every email was a new message, but many real scenarios involve existing threads
3. No refine/edit mode -- when users paste an existing email and ask for improvements, the skill had no pathway for refinement vs. generation from scratch

**Changes:**
- Replaced generic subject line guidance with type-specific examples: request, follow-up, bad news, cold outreach, apology, introduction, and status update each get a concrete pattern.
- Added reply vs. new thread guidance to Step 0: replies are shorter and skip re-establishing context; when in doubt, write fresh (easier to paste into a reply than to extract from one).
- Added Refine mode section before Step 0: when user pastes an existing email, the skill edits rather than rewrites. Identifies email type, applies anti-patterns, cuts filler, delivers in the same format but explains what changed and why. Only rewrites from scratch if the original is structurally broken.
- Added tc-006 to test bank (adversarial: user pastes a filler-heavy email asking for improvement -- tests refine mode).

**Anchor check:** Output format preserved -- refine mode uses the same Subject/Body/"Why this works" structure. Core identity intact -- still opinionated, still produces ready-to-send output. Tone unchanged. Key principles (150 words, one ask, no filler) apply equally to refined and generated emails.
