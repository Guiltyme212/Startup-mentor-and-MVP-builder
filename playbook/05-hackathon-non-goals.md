# The DO NOT BUILD list — defaults and reasoning

`CLAUDE.md` has the short list. This is the expanded version with rationale for each item. Use this file when populating the **Non-goals** section during planning. Copy relevant items into the project doc. Quote them verbatim when pushing back on scope creep.

## The filter: "is this on the demo path?"

If no → defaults onto the DO NOT BUILD list. The burden of proof sits on *building*, not on *not building*. See `03-demo-path-doctrine.md` for what "demo path" means.

## Standard items (each with why)

### Authentication / login
Unless the demo moment requires a logged-in user (social features, cross-session history visible *in the demo*), skip auth entirely. Hardcode `user_id = 1`. Judges don't ask about auth. A real login flow burns 3–4 hours and adds zero wow.

### Settings pages
Every minute on preferences is a minute off the gasp. If a setting matters, hardcode the good default.

### Onboarding flows
The demo IS the onboarding. Judges see the app work in 20 seconds. A guided tour is a distraction.

### Admin dashboards
You're the admin. Use Prisma Studio, `sqlite3` CLI, or a SQL client. No admin UI.

### Mobile responsiveness beyond "doesn't explode"
Demo on laptop or one phone. If you're demoing mobile, test *on your phone*. That's the responsiveness bar.

### Loading states beyond spinner or skeleton
Shimmer effects, branded loaders, progress animations — all off-path. A single `<Spinner />` is enough.

### Error handling beyond a toast
If it fails, show a toast. Don't build error recovery, retry UX, per-field validation. If the demo path fails, the verifier would have caught it — that's a different class of problem.

### Empty states beyond hardcoded text
*"You haven't added anything yet"* as a flat string. No illustrated empty state. No CTA with 3 onboarding steps.

### Rate limiting, retries, idempotency
Production concerns. Your app has one user for two minutes.

### Accessibility audits
Contrast should be readable — that's taste, not a11y compliance. WCAG AA audits are production work.

### Dark mode
Unless the product *is* about night (rare), every minute on dark mode is a minute lost.

### Analytics
You don't need to know how often the demo is used. You'll watch it happen.

### Landing / marketing site
Judges are already at your app. Skip.

### Paywall / pricing page
Mention pricing in the pitch if it matters. Don't build Stripe.

### Email verification
Even if you have auth (you don't), skip this.

### Cookie banner / GDPR / privacy policy
Not a production system.

### Mobile app / PWA install / native wrapper
Web only unless the demo moment is inherently mobile (Siri-style voice input, camera-driven, etc.).

### i18n / translations
English only. Judges speak English.

### Analytics dashboard for end users
You are the analytics team.

## When to remove something from the default list

You only remove an item if **the demo moment literally cannot happen without it.**

Example: if the demo moment requires the user to save a ritual and come back to it after closing the browser, you need a user concept. But even then, a single hardcoded user is enough. Don't build registration.

## The planning-phase procedure

1. Copy this list into the `Non-goals` section of `CLAUDE.md` (or link to this file directly).
2. For each item, ask: *does the demo moment need this?*
3. If yes, remove from the list and add the minimum version to the slice plan (e.g. "hardcoded user_id = 1").
4. If no, leave it on the list. You will quote it verbatim later when the user says *"should we add..."*.

The list is a weapon against drift. Read it out loud at the start of every day of the hackathon. Judge everything against it.
