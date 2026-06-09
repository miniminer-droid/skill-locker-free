# Skill Locker — Free Tier

Eight hand-authored Claude Code skills, free under MIT. The gateway tier from the [Skill Locker](https://skilllocker.ai) catalog.

## What's in here

| Skill | What it does |
|---|---|
| **Anti-Slop Checker** | Detects AI-sounding phrases and patterns in any text and rewrites them to sound human. Context-calibrated for different registers (academic, legal, SaaS, ESL). |
| **3-Minute Email** | Writes ready-to-send emails under 150 words from any situation description — picks the right framework (cold, follow-up, apology, request), enforces the ask, kills the throat-clearing. |
| **60-Second Bio** | Generates platform-correct short bios (LinkedIn, X, Instagram, speaker intro, About page) from minimal input. Different rules for each platform. |
| **Content Idea Machine** | 20 specific, scroll-stopping content ideas with hooks, format recommendations, and a 5-day calendar — engineered for diversity across 5 content pillars, not 20 versions of the same idea. |
| **Meeting Debrief** | Extracts structured debriefs from messy meeting notes. Built around the one distinction summarisation tools fudge: *decisions* vs *discussion*. |
| **Flashcard Generator** | Turns any notes, article, or chapter into spaced-repetition flashcards optimised for long-term retention — not just question/answer pairs. |
| **Sleep Optimisation Plan** | Diagnoses your specific sleep problem and builds a prioritised protocol that targets the root cause — not generic "avoid screens before bed" advice. |
| **Personal Brand Architect** | Builds a complete positioning system — who you're for, what you stand for, and how to say it — not surface-level "just be authentic" advice. |

The last three are deliberately from non-developer domains (learning, health, personal brand) that the free/OSS Claude-skill ecosystem barely covers — so you can see the kind of skill the paid catalogue focuses on, not just the commodity ones.

Each skill includes its full SKILL.md and a `versions/` directory showing iteration history.

## Try each skill (copy-paste these prompts)

| Skill | Paste this into Claude Code |
|---|---|
| Anti-Slop Checker | *"Check this for AI tells and make it sound human: [paste your text]"* |
| 3-Minute Email | *"Write a follow-up email to a client who hasn't replied in a week about the project proposal."* |
| 60-Second Bio | *"Write me a LinkedIn bio — freelance UX designer, 8 years, ex-agency, now solo, working with fintech startups."* |
| Content Idea Machine | *"Give me 20 content ideas about [your topic] with hooks and a 5-day posting calendar."* |
| Meeting Debrief | *"Turn these messy meeting notes into decisions, action items, and owners: [paste notes]"* |
| Flashcard Generator | *"Make spaced-repetition flashcards from these notes: [paste notes or a chapter]"* |
| Sleep Optimisation Plan | *"I wake at 3am most nights and can't get back to sleep — build me a plan."* |
| Personal Brand Architect | *"Help me build my personal-brand positioning. I'm a [role] who wants to be known for [topic]."* |

## Install (via Claude Code plugin marketplace)

```
/plugin marketplace add miniminer-droid/skill-locker-free
/plugin install skill-locker-free@skill-locker-free
```

That's it. The skills register automatically and trigger when relevant.

## Install (manually)

Each `skills/*/SKILL.md` file is a complete, installable Claude Code skill. To install one:

```bash
mkdir -p ~/.claude/skills/<skill-name>
cp plugins/skill-locker-free/skills/<skill-name>/SKILL.md ~/.claude/skills/<skill-name>/SKILL.md
```

Restart Claude Code if it's running. The skill triggers automatically when a relevant prompt appears.

## Why publish these free

Three reasons.

**One:** if the free skills are good, they're the most credible evidence that the paid skills (288 more across 33 pillars on [skilllocker.ai](https://skilllocker.ai)) are also good. The free tier IS the proof of the bar.

**Two:** the Claude skills ecosystem is dominated by free open-source skills already. Holding the free tier closed would be both ungenerous and bad strategy. Free here, paid for the rest.

**Three:** these skills have been through real Karpathy-loop improvement cycles. They're not first drafts. Putting them under MIT means anyone can read the SKILL.md to see how a polished skill is structured, fork them to adapt to their own context, and learn from the iteration history in `versions/`.

## How these were built

Each skill went through this loop:

1. **Initial draft** — encode the workflow with frontmatter trigger description, body instructions, and explicit edge-case handling.
2. **Adversarial held-out tests** — small set of prompts the skill *shouldn't* handle naively (different registers, sparse input, sensitive contexts, sarcasm, etc.).
3. **Identify failure mode** — read the held-out outputs honestly. The bug is usually an assumption the original draft made silently.
4. **Patch + re-verify** — fix the SKILL.md, run the held-out cases again, commit as a new version (v1.0.0 → v1.1.0 → ...).

Look at `skills/anti-slop-checker/versions/` for a concrete example of what each iteration added (ESL register handling, academic register calibration, etc.).

## The paid catalog

If these are useful, the [paid Skill Locker catalog](https://skilllocker.ai) has 288 more across:

- **AI Foundations** (16) — prompt engineering, MCP, workflow design, CLAUDE.md
- **Second Brain** (8) — Obsidian, distillation, weekly review
- **Notion** (5) — workspaces, dashboards
- **Learning** (7) — concept maps, debate partners, teach-back
- **Content Repurposing** (5) — podcast→show notes, blog→social
- **Course Creation** (8) — curriculum, lessons, sales pages
- **Websites** (11) — landing pages, CRO, about pages
- **Presentations** (5) — slide decks, narrative
- **Write Like a Human** (6) — voice cloning, blog writing
- **Email & Outreach** (10) — cold email, follow-up, difficult conversations
- **Voice-First** (4) — voice memo routing, meeting transcripts
- **Social Media** (9) — content calendars, growth, viral analysis
- **Business** (14) — pricing, niching, SOPs, retainers
- **Career** (10) — resume, interview prep, salary negotiation
- **Data & Analysis** (9) — dashboards, forecasts, reports
- **Project Management** (16) — OKRs, retros, weekly planning
- **Research** (6) — synthesis, gap-finding
- **AI Memory** (5) — context handoff, decay audits
- **Lead Gen & Sales** (9) — ICP, cold outreach, sales calls
- **Document Intelligence** (4) — PDF, DOCX, form filling
- **Command Centre** (10) — life dashboard, burnout warning
- **Finance** (7) — cash flow, pricing models
- **Video Production** (8) — scripts, repurposing
- **E-Commerce** (14) — product descriptions, cart recovery
- **Legal & Compliance** (7) — contracts, privacy policies
- **Health & Wellness** (13) — nutrition, recovery, coaching ops
- **Recruitment** (8) — job descriptions, interview banks
- **Agency Operations** (16) — capacity planning, client reports
- **Personal Brand** (6) — content pillars, signature frameworks
- **Fundraising** (9) — pitch decks, investor outreach
- **Community Building** (6) — paid communities, retention
- **Customer Support** (8) — ticket triage, help articles
- **SEO & Content** (9) — blog writers, on-page audit, technical SEO

Open catalog dataset: [skilllocker.ai/skills.json](https://skilllocker.ai/skills.json). Lifetime updates on every paid purchase.

## License

MIT — read, use, fork, adapt, learn from. See `LICENSE`.

The catalog metadata at [skilllocker.ai/skills.json](https://skilllocker.ai/skills.json) is also free to read and build on. The *paid* SKILL.md files (the other 288) stay gated behind purchase, but the catalog identity and these 8 free skills are open.
