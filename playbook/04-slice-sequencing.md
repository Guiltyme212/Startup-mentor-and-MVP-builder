# Slice sequencing — plan backwards from the gasp

A hackathon slice plan isn't a project plan. It's a sequence of **demoable checkpoints**. Every slice has to be independently visible to a watching human — meaning if you stop there, *something* runs and *something* can be shown.

## The backwards-from-demo method

1. Write the demo moment sentence. (Already done in step 2 of the workflow.)
2. The *last* slice (N) is what produces the gasp.
3. Slice N−1 is the piece that makes slice N possible *and* independently shows something to the user.
4. Keep subtracting until slice 1 is the smallest piece that still shows a user-visible thing.

**Not allowed:** "foundation" slices, "scaffolding" slices, "setup" slices. If a slice has no user-visible outcome, collapse it into a real slice.

## The independent-demoability rule

At every slice boundary, the demo should work *for the slices that are done.* If you ship slice 1 and slice 2 and stop, the user can demo those two. Not the final gasp — but *something* on the path to it.

Example (Kokoro, 4 slices):

- **Slice 1** — user types what's on their mind; LLM parses it into a list of themes; list is displayed. Real input, real LLM, real output on screen.
- **Slice 2** — themes + goal prompt → 90-second script generated and displayed as text. Real GPT.
- **Slice 3** — script → audio file via ElevenLabs; play the audio in browser. Real playback.
- **Slice 4** — "tomorrow morning" ritual screen with *"Jump to 6:45am"* button; final audio plays in the ritual context. This is the gasp.

At each boundary, a judge could watch and understand what's happening. No "you can't demo until the last slice" trap.

## Sizing rule

Target **60–90 minutes per slice**.

- > 90 min → it's actually two slices. Find the split.
- < 30 min → it's probably a piece of another slice, or off-path work you shouldn't be doing at all.

90 min is the right size because the verifier's 5-point contract still has to run cleanly on it. Slices bigger than that collect too many changes for the verifier to police effectively.

## Vertical always, horizontal never

- **Vertical slice** — DB migration + server route + UI, wired end-to-end for one feature.
- **Horizontal slice** — all DB migrations first, then all routes, then all UI.

Always vertical. Horizontal slices can't be demoed until you're 100% done — which means you have nothing to show the judges if you run out of time.

## Risk-first ordering

If two slice orderings are close, do the *riskier* one first. The demo moment usually hinges on one hard thing — an API you haven't used, an AI call that might not do what you want, a timing constraint you can't fully test. Do that first.

If the risky thing breaks, you want to know on Day 1, not Day 3. This is the single biggest reason to break from naive backwards-from-demo sequencing.

## When to re-plan

Re-plan slices if:

- A slice takes > 150% of its estimate (the remaining plan needs re-sizing).
- The demo moment genuinely shifts. (Rare — it shouldn't, it's locked.)
- A dependency is worse than expected. (The AI doesn't do what you thought. The audio API is rate-limited. Re-plan around the discovery.)

Do *not* re-plan because you're bored of the current slice, or because a new idea showed up. That's drift. Quote the DO NOT BUILD list and move on.

## The end-of-day resume rule

At the end of a working session, update `Current state` in `CLAUDE.md` to include: which slice is in progress, what was the last passing verifier run, and what's blocking slice K+1. This is how you close the laptop and resume without losing 15 minutes re-orienting.
