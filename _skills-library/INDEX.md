# Skills Library — Index

Ranked by likely hackathon value. Each entry: **when to tailor**, and **what to cut** when tailoring (these candidates were written for production engineering teams and always need trimming for hackathon use).

---

## Tier 1 — almost certainly needed at Barcelona

### `frontend-slides` — pitch deck builder
Zero-dependency, animation-rich HTML presentations. Viewport-fit enforced. Style-preview mode when user hasn't decided aesthetic.
- **Tailor when:** the demo day approaches and a 3–5 min pitch is needed. Realistically Day 2 or 3.
- **Cut:** PPT/PPTX conversion workflow (hackathon use is always "from scratch"), multi-language notes, anti-pattern section. Keep the viewport-fit rules and style-preview flow.

### `ui-demo` — Playwright demo video recorder
Records polished UI walkthrough videos with injected cursor, natural pacing. Insurance against live-demo glitches.
- **Tailor when:** after verifier signs off on the demo-moment slice. Before the final demo block.
- **Cut:** enterprise-scale discovery phase, extensive field-mapping for complex forms. For a hackathon MVP, keep the Rehearse → Record loop minimal.

### `product-lens` — validate the "why" before building
Pressure-tests product direction. Structured diagnostic questions on need vs. implementation.
- **Tailor when:** intake feels vague. The user says "I want to build X" but the demo moment sentence won't form cleanly. Run this skill *before* locking the demo moment.
- **Cut:** anything about PRDs, roadmaps, stakeholders. Distill to: "what breaks if this product doesn't exist" + "who gasps when they see it."

---

## Tier 2 — situational, depends on the hackathon's nature

### `frontend-design` — visual direction system
Catalog of named aesthetics (brutally minimal, editorial, industrial, etc.) and a workflow for committing to one.
- **Tailor when:** the hackathon UI needs a distinctive look and `designer.md`'s defaults aren't enough. Most hackathons: skip.
- **Cut:** production-system concerns (design tokens across a team). Keep the named aesthetics list and the "pick one, commit" principle.

### `search-first` — research before coding
Forces package/MCP/library search before writing custom code.
- **Tailor when:** builder is about to write something that likely exists as a package (auth, image upload, payments, markdown rendering, LLM wrappers). Use during slice handoff.
- **Cut:** the full multi-source evaluation matrix. At a hackathon, the decision is "first acceptable package wins." Keep the "search before coding" rule, simplify the evaluation to "install and move on if license is MIT/Apache."

### `browser-qa` — UI automation verification
Adds smoke test, interaction test, visual regression, accessibility to the verifier's arsenal.
- **Tailor when:** the hackathon is frontend-heavy and `verifier.md`'s point 4 (UI click-test) needs more rigor. Tailor by importing into `verifier.md`, not as a separate skill.
- **Cut:** accessibility audits (WCAG AA is overkill for 3 days), visual regression baselines (no baselines exist), Core Web Vitals (irrelevant for demo). Keep smoke test + interaction test.

### `claude-api` — Anthropic SDK patterns
Messages API, streaming, tool use, extended thinking, prompt caching.
- **Tailor when:** the hackathon project calls the Claude API. Very common at AI hackathons.
- **Cut:** batches, vision-from-PDF, anything not needed for the specific integration. Keep streaming + tool use + the one SDK (TS or Python) you're actually using.

### `deep-research` — multi-source research with citations
Uses firecrawl/exa MCPs for web research.
- **Tailor when:** the idea needs market-research validation ("does this exist already?"). Rare at hackathons — usually the idea is "build cool thing" not "study market."
- **Cut:** unless firecrawl/exa MCPs are already configured. WebSearch/WebFetch fallback works; adjust accordingly.

---

## Tier 3 — meta tools for kit maintenance

### `context-budget` — audit kit token overhead
Scans agents/skills/MCP for bloat. Surfaces top savings.
- **Tailor when:** between hackathons, to keep the drop-kit lean. Not during a hackathon.
- **Cut:** the MCP-heavy parts if this kit isn't using MCP servers. Keep the token-estimation heuristics and the "agents > skills > rules" ranking.

### `prompt-optimizer` — improve prompts iteratively
Refines agent/skill prompts based on observed failures.
- **Tailor when:** after Barcelona, in the post-mortem, to sharpen `mentor.md`/`builder.md`/`verifier.md` based on what choked. Not during a hackathon.

### `skill-stocktake` — audit skill quality
Quick scan or full stocktake of the skills library. Used by ECC to maintain their collection.
- **Tailor when:** between hackathons. If the library grows past ~10 candidates, use this to re-triage.

### `strategic-compact` — manual context compaction at phase boundaries
Suggests compacting at logical intervals rather than letting auto-compaction hit arbitrarily.
- **Tailor when:** a hackathon runs multi-session and context hygiene starts mattering (end of Day 1, for example).

---

## Tier 4 — thinking aids, rare use

### `council` — 4-voice structured disagreement
Four named voices argue an ambiguous decision before the mentor chooses.
- **Tailor when:** a truly ambiguous product or architecture call is blocking the user and mentor alone can't break the tie. Use sparingly — the mentor's own pushback is usually enough.

---

## Agents (subagent candidates)

### `silent-failure-hunter.md` — static adversarial code review
Hunts for swallowed errors, empty catches, dangerous fallbacks, log-and-forget patterns. Complements `verifier.md` (which is runtime-adversarial) with static-analysis adversarialism.
- **Tailor when:** the hackathon project grows past ~5 slices and silent failures start piling up. For a 3-day MVP, usually skip — verifier catches enough.
- **Cut:** nothing much — it's already tight.
