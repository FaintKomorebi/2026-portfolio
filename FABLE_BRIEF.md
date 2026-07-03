# Portfolio Brief — Noah Schilling (v3)

Read this at the start of every session. Active brief for `2026-portfolio v2 /`.
Design direction as of 2026-07-02. Everything before this date — the v1 editorial
system in CLAUDE.md and the v2 radical-minimalism direction — is dead. Do not
carry forward colors, type, or layout habits from either.

---

## The Goal

Get hired. Mid-level UX / product design roles. The case studies are the audition —
they need to prove Noah can diagnose a real problem, make and defend a decision,
and show outcome. The homepage is the handshake, not the pitch. Don't let homepage
polish outweigh case study substance — if something has to be simpler to keep the
schedule sane, simplify the homepage, not the case studies.

**The bar:** stand out without making a mess or a statement. A hiring manager
skimming 40 portfolios should feel "this person is careful" before they feel
"this person is different." Confidence, not noise.

---

## The Design Thesis

Two things are being fused that don't normally sit together:

1. **Editorial restraint** (Ferrari, old-era Apple, Anthropic) — huge whitespace,
   one idea per screen, restrained chrome, type doing the heavy lifting, slow
   confident pacing. This is the macro structure.

2. **Engineered micro-detail** (Marathon) — not grit, not sci-fi, not dark-mode
   HUD cosplay. What's worth taking is the *instrumentation habit*: small
   monospace labels, hairline rules, coordinate/tag-style annotations, tight
   tracking on small caps, precise alignment that reads as considered rather
   than decorative. Marathon's actual game imagery, video, and dark palette are
   explicitly NOT the reference — only the typographic/graphic craft.

**The bet:** whitespace and calm carry the page; the instrumentation layer is
where the craft signal lives, used sparingly and only where it does real work
(case study annotations, metadata, state labels) — never as homepage decoration.
This is not a compromise between the two references, it's a hierarchy: 90%
editorial calm, 10% engineered precision, applied where it earns its place.

**Explicitly rejected:**
- Anthropic's cream/oat palette — go cooler and more neutral instead
  (true white/black/grey, one accent color at most, tbd)
- Marathon's dark UI, grain, glitch, sci-fi texture, or imagery style
- Anything that reads as a "look at this portfolio" statement piece over a
  "look at this thinking" case study

---

## References

Live links for Fable to look at directly. These are inspiration for the thesis
above, not a checklist to copy from — pull the sensibility, not the components.

- https://www.marathonthegame.com/ — typographic/graphic instrumentation only
  (small labels, hairline rules, tag-style annotations, tight tracking). Ignore
  the game imagery, video, and dark palette entirely.
- https://www.ferrari.com/en-US — editorial pacing, whitespace, restrained
  chrome, type-led hierarchy.
- https://www.anthropic.com — editorial confidence, calm structure. Take the
  layout sensibility, leave the cream/oat color palette behind.
- Old-era Apple (roughly 2013-2016 marketing pages, pre-lifestyle-photography
  era) — no single live URL, described from memory: massive whitespace,
  confident large type, one sentence + one image pacing, cool and clinical
  rather than warm and family-focused. Use as a general sensibility reference.

---

## Content and structure — open

Content, IA, and page structure are NOT locked this round. Design from scratch,
including whether the current skeleton (name top-left / intro line / Successes
and Contact two-column index) survives. What IS fixed is the material available
to work with:

**People/facts:**
- Noah Schilling, product designer, Milwaukee WI, remote open
- Targeting mid-level UX / product design roles (senior opportunistically)

**Case studies (real, in this priority order):**
- **ACRO** (cs-acro.html) — complete case study, richest material. Industrial
  automation company site redesign, 29→17 pages, +28% session duration, 1.4x
  CRM inquiry volume. Has before/after imagery, hero video, decision narrative.
  This is the flagship — it needs to look the best.
- **SharePoint IA** (cs-sharepoint.html) — active/in-progress, ~80-person
  company information architecture project. Has screenshots (sp-homepage.png,
  sp-it-site.png).
- **Lincoln Nautilus UX critique** (cs-lincoln.html) — not started. Real,
  personal frustration with the car's infotainment UI, documentation session
  pending. Stub for now; the brief for it exists in the old CLAUDE.md if needed.

**Assets available:** SF Pro Display OTF (Light/Regular/RegularItalic/Medium) in
assets/fonts — usable but not mandatory, Fable can propose different type if it
serves the thesis better. Resume PDF, ACRO images/video, SharePoint screenshots
all in resources/.

**Contact:** email + LinkedIn, resume link. Keep it findable, don't bury it
behind cleverness.

---

## Guardrails

- No em dashes. Anywhere. Ever. Periods or rephrase. Middle dot (·) if a
  separator is truly needed.
- Whole site in scope this round — homepage and both real case studies should
  feel like one system, not a redesigned homepage bolted onto old case study
  styling.
- Restraint is the design statement. If a choice feels like it's trying to
  impress, cut it. If it feels inevitable and quiet, keep it.
- Don't invent personality copy or claims not grounded in the facts above.
- Static HTML/CSS, no build tools, no frameworks — matches existing stack.

---

## Round one notes (2026-07-03)

- **TLDR/Full reading-mode toggle was dropped from cs-acro.html in round one** — it read as
  chrome fighting the editorial calm. Noah is fine with this for now, but flagged that it
  may come back as a system-level pattern (applied consistently across case studies, not
  a one-off) if the loss of a fast-skim path becomes a real problem in review.
- **Reviewed in browser, reaction positive.** Confirmed and closed, no action needed:
  survey quotes attributed by department not name, Lincoln shown as a muted unlinked
  homepage stub, contact links shown plainly instead of behind the old popup.
- **Not yet committed or pushed.** Round one exists only as uncommitted working tree
  changes. Needs explicit approval before `git commit && git push` per the workflow
  rule in CLAUDE.md.

---

## Next steps

- [ ] **About / personality page.** Separate page, not folded into the homepage.
  - Purpose: tonal counterweight to the case studies. Case studies prove competence
    through restraint and precision; this page proves Noah is a real person. Contrast
    is the point, not an inconsistency.
  - Tone: "the light page" — loose, wry, self-aware. Not childish, and not so serious
    it just restates how serious he is about the job (that's the opposite of the goal).
  - Content: real hobbies (homelab, keyboards, car) framed as evidence of the same
    instincts sold in the case studies — systems thinking, tactile obsession, chronic
    friction-noticing — not a flat list of trivia. Specific and dry beats a list of
    interests every time.
  - Visual treatment: black and white photography. Keeps the looser content controlled
    and editorial rather than tipping into lifestyle-blog territory.
  - System consistency: same fonts, hairlines, and mono-tag instrumentation as the rest
    of the site. The voice loosens here, the craft doesn't.
  - Page name/slug: undecided. Don't default to a literal "About Me" label without
    checking it against whatever tone the copy lands on.
  - Sequencing: Noah drafts the copy first. Do not build layout before copy exists —
    the tone of the actual sentences should drive how loose the structure gets, not
    the reverse.
  - Homepage needs a minimal call-to-action link added once the page exists. Not
    added yet since there's nothing to link to.
- [ ] **Verify contact email.** Visible contact links are approved, but
  nschillingdesign@gmail.com was carried over from the old page and hasn't been
  explicitly reconfirmed as current.
- [ ] **Commit and push round one** once the above is settled and Noah gives explicit
  go-ahead — homepage, cs-acro.html, cs-sharepoint.html are ready and waiting.

---

## Process

- Preview at localhost:3000 (`python3 -m http.server 3000`) before anything
  ships.
- Commit and push to GitHub Pages only after Noah approves what's on screen.
- This is round one: direction and system, not pixel-final. Expect iteration.
