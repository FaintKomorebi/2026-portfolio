# Voice Brief · Noah Schilling

How every word on this site sounds. `DESIGN.md` governs how it looks. Read both before
writing or editing any copy.

---

## The Target

Noah's own framing, kept verbatim:

> "I want to sound like I know my shit sure, but not shit covered with gold here
> and definitely not trying so hard to prove my work."
>
> "It should have some life and communicate what was done without fluff and
> without sounding like I'm 50 talking to other 50 year old product designers."

**The test for every line: read it out loud. If Noah would never say it to a coworker,
rewrite it.**

Two ways a line fails the test:

1. **Consultant register.** Performing authority. Deck vocabulary, brand-voice sentences,
   claiming more rigor than the work had.
2. **Computer voice.** Clever, dry statements about the situation. Fragment pairs,
   "not X but Y" reversals, a neat summary line closing every paragraph. Each one is
   harmless alone. Stacked, they read as machine-written.

---

## Headings

- **Name what's in the section, the way Noah would say it.** Short is good: "What I walked
  into."
- **First person when it's something he did:** "I started by asking people how they
  actually find things."
- **No observations or wit about the situation.** "Ten drives, and each one made sense to
  whoever built it" is the computer voice, however true it is.
- **Don't make a claim the section has to defend.** The heading names it. The body proves
  it.
- **Never two fragments.** "Survey first. Structure second." is out.

## Sentences

- **Explain it like talking to a coworker.** "Just," "actually," and "so" are how Noah
  talks. Keep them. Only thin them out when several land in one paragraph.
- **Say what he did, with "I," before saying what it meant.**
- **End a paragraph on its last fact,** not on a line that sums it up.
- **No runs of fragments** ("No root. No model."), no asides like "Nobody was lying," and
  no "not X, Y" when one is already on the page.
- **If a line would work on a poster, cut it.** Cutting beats rewriting.

## Facts and Claims

- **Confidence comes from specifics, not vocabulary.** "29 pages and two clicks" beats "a
  legacy brand experience." Numbers, page counts and click counts carry the authority.
- **Every data claim gets a source tag, and a measured number is stated flat.** Same format
  as the outcome stats (`Source · Google Analytics`). Never hedge a measured figure.
- **Never write the client's brand copy.** If a sentence would fit on the client's own
  About page, it is out.
- **Self-critique lives in one place per case study.** Nothing else on the page apologizes,
  hedges or pre-concedes.
- **Plain is not casual.** Direct, not informal. No profanity, no "folks." `about.html` is
  the ceiling for looseness.

## Banned

- **Words:** legacy brand, entry point, lens, closing the loop, holistic, strategic,
  leverage, elevate, seamless, journey, unlock, pain points, surface (as a verb meaning
  "show"), "change management as design."
- **Shapes:** "The mandate was X. The opportunity was Y." and any "it's not X, it's Y" when
  another is nearby.
- **Em dashes, anywhere.** Periods, commas, colons, or a middle dot (·).

**Allowed despite looking like hits:** "surfaced" meaning "emerged" ("Surfaced
independently in every department"). "Actually" in spoken rhythm.

---

## Tuning Fork

Lines that hit the voice. Match these.

- "I was asked to move ACRO's files off its old network drives and into SharePoint.
  Copying them over as-is would have just moved the mess, so the real job was building a
  structure everyone would actually use and benefit from." (`cs-sharepoint.html` lead)
- "I started by asking people how they actually find things." (heading)
- "I kept it to one rule everyone could follow." (heading)
- "Live, and moving over one department at a time." (heading)
- "If I built the structure for each department, it wouldn't match how they actually work,
  and it certainly wouldn't persuade anyone to break old habits." (Noah's own)
- "ACRO has built automation systems for 90 years. It took two clicks and a scroll to find
  that out." (`cs-acro.html` hero)
- "I ran the layouts past engineers and sales staff at ACRO, the people fielding buyer
  questions every day." (`cs-acro.html`)

How misses were fixed:

| Miss | Fix | Why |
|---|---|---|
| The mandate was a SharePoint migration. | I was asked to move ACRO's files off its old network drives and into SharePoint. | Banned shape. Says what he did. |
| Survey first. Structure second. | I started by asking people how they actually find things. | Fragment pair. Now first person. |
| Ten drives, and each one made sense to whoever built it. | What I walked into | Clever observation. Now a plain name. |
| Nobody was lying. Everyone had built their own working model of a system that had no real structure. | Every person gave a different answer, because everyone had worked out their own system. | Aside plus a dressed-up noun. |
| Industry-led entry point | Sorted by industry, not product | Deck vocabulary. |

---

## Page Status

| Page | Status |
|---|---|
| `index.html` | Scrub pending |
| `about.html` | Noah's own words. Scrub for typos only. |
| `cs-sharepoint.html` | Done. |
| `cs-acro.html` | Done. |
| `cs-ramyunzip.html` | Scrub pending |
| `cs-homelab.html` | Scrub pending. Its spoken rhythm is the model for sentences. |

## How a Rewrite Runs

1. Read the page against this file.
2. Show Noah a now-and-draft table in chat. Prefer cuts to rewrites.
3. Noah picks, rewrites or skips each line. His version wins.
4. Apply locally and preview the page.
5. Check it: `grep -n -i -E '—|leverage|holistic|seamless|elevate|unlock|pain point|closing the loop|entry point' <page>.html`
   (a hit means look, not fail).
6. Commit and push on Noah's OK. Update the Page Status row and the Craft mirror (see
   `CLAUDE.md`).
