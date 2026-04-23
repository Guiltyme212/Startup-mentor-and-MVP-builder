# The demo-path doctrine

Everything a judge sees between "opens the app" and "gasps" is the **demo path**. Everything else is **off-path**.

## The rule

> **100% real on the demo path. 0% real off the demo path.**

Real on the demo path means: the DB write actually happens, the API call actually fires, the AI actually generates, the response is inspected live. No stubs, no mocks, no "this would show X here in production."

Off the demo path can be anything: empty screens, hardcoded rows, broken buttons, dev-only shortcuts. Judges never see it. The builder spends zero minutes on it.

## Why

Judges can smell theater. A working MVP that's 20% of the eventual product beats a slick prototype that mocks the 80%. Authenticity *is* the differentiator at hackathons — almost nobody does it, and the ones who do win disproportionately.

## Classifying at planning time

For every feature the user mentions, ask: *does the demo path touch this?*

- If yes → it must be real. Schedule as a slice.
- If no → it's off-path. Default to not building it. Put it on the DO NOT BUILD list (see `05-hackathon-non-goals.md`).

Example — Kokoro demo moment: *"Sam tells it he's anxious about tomorrow's Series A pitch. 12 hours later, his phone plays a 90-second audio at 6:45am that names the pitch, the investor, and the specific fear."*

- On path: input form, LLM generation of script, audio synthesis, playback UI.
- Off path: account creation, payment, history screen, settings, notification delivery at 6:45am tomorrow (see simulation rule below).

## Just-in-time fakes — the only permitted shortcut on the demo path

Some demo-path things can't be real in 3 days (future time, mass users, external infra). For these, you fake the *mechanism* while keeping the *outcome* real.

- **Time-delayed delivery.** Can't wait until 6:45am tomorrow. Add a *"Jump to 6:45am"* button. The ritual is real — generated, personalized, audible. Only the clock is fake.
- **Other real users.** Can't get 1000 users to join. Seed a known-good partner account with real data. The interaction is real; the partner is scripted.
- **Push notifications / SMS / email.** Don't wire twilio/SendGrid/APNs. Show the notification arrival inside the app UI.
- **Payment rails.** Don't wire Stripe. Show the "paid" state directly.

The rule for just-in-time fakes: **the judge can see it's a shortcut and still feel the gasp.** The *"Jump to 6:45am"* button is a time-machine, not a sleight of hand. Judges don't mind time-machines — they mind theater.

## Common demo-path mistakes

- **Stubbing the AI.** "Pretend this is what GPT would say." No. Call GPT. If you don't have a key, stop and get one before proceeding (see builder agent's rule on missing API keys).
- **Hardcoding the demo input.** The text is pre-filled when the judge sits down. No. The judge types it live. If the judge types something unexpected, the app still works.
- **Skipping the DB write.** "It would save this to the database." No. Save it. Read it back. Show the row. The verifier's point 3 enforces this.
- **Fake third-party data.** Returning mocked LLM output is theater even if formatted to look real. Always the real call.

## Verifier's role on the demo path

The verifier's 5-point contract exists specifically to police the demo path:

1. Dev server clean — demo can't crash mid-pitch.
2. Routes real — the server actually responds.
3. DB writes real — data survives.
4. UI click-tested — the flow works end-to-end.
5. Third-party APIs live — the AI/audio/external service actually fires.

If any point fails *on a demo-path slice*, the slice isn't done. Off-path failures can be deferred indefinitely or ignored.
