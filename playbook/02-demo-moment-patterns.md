# The demo moment — patterns and anti-patterns

The demo moment is the single sentence that gets written into `CLAUDE.md` and lives there, unchanged, for the rest of the hackathon. Everything else — data model, slices, design, pitch — is a function of it.

## The format

> *"A **[specific user]** **[does one simple action]** and **[impossible-feeling thing]** happens."*

Each blank does real work:

- **Specific user** — named, not "a user." "Sam" not "people." (If the idea pressure-test was done, you already have this.)
- **One simple action** — a single gesture. Click, type one sentence, tap play, upload one file. Not a flow. Not a sequence. One input.
- **Impossible-feeling thing** — the gasp. The judge says "wait, really?" out loud.

## The three flavors of gasp

Pick exactly one. Never stack two.

**Magic gasp.** Something happens that feels impossible.
> *"Sam tells it he's anxious about tomorrow's Series A pitch. 12 hours later, his phone plays a 90-second audio at 6:45am that names the pitch, the investor, and the specific fear he mentioned."*

**Speed gasp.** Something that normally takes hours takes seconds.
> *"Maya pastes a job listing. In 8 seconds, the app has generated her tailored resume, cover letter, and three questions she should ask in the interview."*

**Intimacy gasp.** The product knows something uncomfortably specific about the user.
> *"A founder uploads 30 days of Whoop data. The app tells him, to the hour, when he's been lying to himself about how tired he is."*

If you can't place your idea in one of these buckets, the gasp isn't defined yet. Keep drafting.

## The 20-second test

Watch the demo in your head as silent video. In 20 seconds, is the gasp visible? If not, the demo is too long, or the gasp is too subtle. Simplify.

## Anti-patterns (each kills hackathon demos)

- **Settings-first.** Demo opens with "first, let me create an account and configure my preferences." No. Demo opens with the gasp-adjacent action.
- **Tutorial-first.** Demo opens with "let me walk you through how this works." No. The demo *is* how it works.
- **Category demo.** "This is a marketplace for X." Marketplaces need 1000 users to feel alive. Judges hate marketplace hackathon demos. Pick a product, not a platform.
- **Empty-state demo.** The demo requires seed data the user hasn't entered yet. No. One live input, live output.
- **Imaginary-user demo.** "Imagine a second user over here..." No. Either the app works for one user, or you script one partner account with real data. Never imaginary.
- **Feature-tour demo.** The demo is three disconnected features. No. The demo is one feature that produces the gasp, end to end.

## Build-the-end-first

Once the demo moment is locked, the slice plan runs backwards from it. Slice N is the gasp. Slice 1 is the smallest piece that *starts showing* something. Every slice in between must be independently demoable. (See `04-slice-sequencing.md`.)

## When the user resists locking

Common drift: user wants to "start with the data model" or "set up auth first." This is the biggest failure mode in hackathon week 1.

Push back, gently then firmly. Say out loud: *"We can't build until we know what the wow is. Two minutes locking this sentence saves six hours of drift later."*

If they still resist, offer to draft the sentence yourself and let them correct it. A written draft is easier to argue with than a blank.

**Do not start the builder until the sentence exists in `CLAUDE.md`.** This is the hardest-enforced rule in the kit.
