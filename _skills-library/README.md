# Skills Library

Raw, **untailored** skills and agents lifted from public Claude Code collections. They live here instead of `.claude/skills/` on purpose: nothing in this folder auto-loads into a session's context. That keeps the drop-kit lean at rest.

## Philosophy

A skill has no business being live until a specific hackathon's demo moment needs it. Pre-tailoring for "maybe-useful-someday" is how context bloat and kit-sprawl happen. Instead:

1. During **intake / planning** for a new hackathon, the mentor reads `INDEX.md` and evaluates which candidates directly serve the locked demo moment.
2. The mentor reads the raw candidate source from `candidates/`.
3. The mentor writes a **tailored copy** to `.claude/skills/<name>/SKILL.md` — trimmed, rewritten for this project's specifics, stripped of irrelevant sections.
4. At the end of the hackathon, tailored skills can stay in the repo (demonstrating what worked) or be removed. The untailored candidates in this folder never change.

## When to promote

Use the triage bar from the mentor's `CLAUDE.md`. A skill earns a promotion only if it:

- (a) saves the builder 30+ minutes of boilerplate at a hackathon, **OR**
- (b) gives the mentor a concrete heuristic not already in `CLAUDE.md`, **OR**
- (c) gives the verifier a new dimension worth enforcing, **OR**
- (d) is required for the demo day itself (pitch deck, demo video).

Max 3–5 tailored skills active per hackathon. Less is more.

## Source

Candidates pulled from [affaan-m/everything-claude-code](https://github.com/affaan-m/everything-claude-code) — a large public collection. Only hackathon-relevant skills were included here; the full repo has ~180 skills, most irrelevant (enterprise ops, healthcare compliance, language-specific patterns for stacks we don't use). Re-clone that repo if you need something not in this library.

## Files

- `INDEX.md` — ranked shortlist with "when to tailor" notes
- `candidates/skills/` — 13 raw skill directories
- `candidates/agents/` — 1 raw agent markdown file
