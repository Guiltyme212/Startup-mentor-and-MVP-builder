# Startup Mentor — Drop Kit

A personal Claude Code configuration that turns a fresh session into a YC-tradition startup mentor — one who also shifts into MVP builder and web designer modes when the work calls for it.

**Drop the whole folder into a new hackathon project. Open Claude Code. Paste a 3-line idea. Go.**

## What's inside

- `CLAUDE.md` — mentor persona, workflow, and the living document for the current hackathon. Top half is static. Bottom half fills in as you work.
- `.claude/agents/builder.md` — builds slices end-to-end. Real code, never stubs.
- `.claude/agents/designer.md` — polishes working screens after the verifier signs off.
- `.claude/agents/verifier.md` — adversarial 5-point contract. Blocks demo theater.
- `.claude/skills/` — cherry-picked skills from public Claude Code repos (tailored, not adopted wholesale).

## How to use

1. Clone (or copy) this folder into your hackathon target.
2. Optionally `rm -rf .git && git init` for a clean hackathon history.
3. Open Claude Code inside the folder.
4. Paste a 3-line project description.
5. Let the mentor drive the workflow.

## What it refuses to do

- Start a slice before the demo moment is locked in `CLAUDE.md`.
- Ship stubs or fake data on the demo path.
- Let the designer run before the verifier passes.
- Adopt any external persona — all imported skills are tailored to this kit.
