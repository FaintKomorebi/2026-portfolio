# Portfolio — CLAUDE.md

Project instructions and context for Claude Code. Read this at the start of every session.

---

## Critical Workflow Rule

**Always `git push origin main` immediately after every `git commit`.** Chain them with `&&` in the same Bash call. The site is hosted on GitHub Pages — commits that aren't pushed don't exist for the user.

---

## Project Overview

**Owner:** Noah Schilling — Product Designer, Milwaukee WI (remote open)
**Repo:** https://github.com/FaintKomorebi/2026-portfolio
**Stack:** Static HTML/CSS — no build tools, no frameworks. Everything lives in inline `<style>` blocks.
**Goal:** 2026 job search portfolio targeting mid-to-senior product design / UX roles. Strategy: apply to senior roles aggressively (fewer applicants, willing to grow into it) as well as mid-level.

**Copy direction:** See `VOICE.md` for how the site sounds. Read it before writing or editing any copy on any page. It is authoritative over any voice habit inferred from existing text.

**Design direction:** See `FABLE_BRIEF.md` — this is the active, authoritative design brief. It is rewritten from scratch each time the direction changes; do not infer design system, colors, or type from git history or old commits.

---

## File Structure

```
index.html          — Portfolio homepage
about.html          — About Me page (complete, live 2026-07-27)
cs-acro.html        — ACRO case study (complete, richest material)
cs-sharepoint.html  — SharePoint IA case study (active, in progress)
cs-lincoln.html     — Lincoln case study (generic unbuilt template stub, not linked from index with a real href yet)
cs-homelab.html     — Command Center case study (complete, live)
assets/fonts/       — SF Pro Display OTF (Light, Regular, RegularItalic, Medium)
resources/          — Images, video, resume
  acro-robot-index.webm
  acro-solutions-index.webm
  acro-prototype.webp        — Framer prototype (desktop/tablet/phone), Fig. 02 in cs-acro.html
  acro-dispensing-before.webp
  acro-dispensing-after.webp
  acro-solutions.webp
  acro-services.webp
  acro-aboutus.webp
  sp-homepage.png
  sp-it-site.png
  about-california.webp      — About Me evidence photo, B&W square crop
  about-autocross.webp       — About Me evidence photo, B&W square crop
  about-keyboard.webp        — About Me evidence photo, B&W square crop
  about-led.webp             — About Me evidence photo, B&W square crop
  Noah_Schilling_Product_Design.pdf
CLAUDE.md            — this file: workflow, project facts, case study material
VOICE.md             · copy/voice brief, read before writing any copy
FABLE_BRIEF.md        — active design brief, read this for direction
```

---

## cs-acro.html — ACRO Automation Systems (Complete)

### Project Facts
- ACRO is a family-owned industrial automation company (90+ year history)
- Site went from 29 pages → 17 pages
- Built in WordPress, managed by ACRO's in-house SEO team post-launch
- Timeline: 6 months | Role: Lead Designer
- Competitors had 17 and 21 pages — ACRO's 29 was an outlier
- Top pages on old site: Contact Us, Careers, Automated Welding, Robotics, Automated Assembly
- Those solution pages had **no call to action** — customers found content and hit dead ends
- Brief was officially "UI refresh" but stated goals were fewer steps + solutions as main focus

### Key Outcomes
- +28% average session duration (proxy signal — engagement, not navigation)
- 1.4× CRM inquiry volume in 90 days post-launch vs. prior baseline
- Sales confirmed inquiry quality improved — prospects referencing specific solution pages

### Update — 2026-07-27
- **Platform spec line** now reads "Figma, Framer, Adobe Suite · handed to ACRO's
  WordPress team post-launch" (was just "WordPress · handed to ACRO's SEO team
  post-launch") — corrected because WordPress was the handoff destination, not
  the design tool.
- **New Fig. 02** in Section 04 (The Solution): a real Framer screenshot showing
  the homepage prototype across desktop/tablet/phone breakpoints
  (`resources/acro-prototype.webp`), captioned as prototyping-before-build
  evidence. The final shipped-homepage scrolling video (previously Fig. 02) is
  now Fig. 03. This addresses a real gap — the case study previously showed
  only finished output, no prototyping/process evidence.
- Only one Framer screenshot was actually usable (a real in-editor capture,
  cropped to remove all browser chrome and the Framer side panels). Figma
  static exports (desktop/mobile) were discussed but never delivered — if
  Noah produces those later, they'd slot in alongside or replace this figure.

---

### Update · 2026-08-19 · Full voice overhaul APPLIED

Noah read the whole site and judged `cs-acro.html` the weakest copy on it:
"half claude and half of a buzz word book had a baby." `cs-homelab.html` is the
voice reference, `about.html` is his verbatim words, `cs-sharepoint.html` mostly
lands. See `VOICE.md` for the full brief, the rules, and the approved rewrites
already calibrated with him.

**Scope of the ACRO overhaul:**
- Full copy rewrite, structure and figures stay as they are. This is a voice
  problem, not an IA problem. The case study's bones are good.
- Strip brand-voice sentences (line 657 currently reads like ACRO's own About page).
- Replace deck subheads in Section 04 ("Industry-led entry point",
  "Consolidation over elimination", "Closing the loop").
- Cut "I treated it as an information architecture project", "tested against that
  lens", "Every structural decision was tested".
- Keep "The content didn't shrink. The distance to it did." Explicitly approved.
- Keep "What I'd Do Differently" as the ONLY self-critical moment on the page.
  Noah's note: "I don't want to admit too much fault here, we already do that in
  a few other places on ACRO."

**RESOLVED · no absolute dwell figures exist.** The SEO provider's report gives
April 2024 average session duration as 1 second, a tracking artifact. All three
unsourced behavioral claims were cut rather than hardened. See `VOICE.md`,
"The ACRO Dwell-Time Decision", including the open question about what the +28%
is measured against.

**Original blocker, kept for context.** Lines 615, 657, and 739 make
behavioral claims with no source and hedge wording ("maybe 90 seconds", "Most
didn't stay long enough", "Most closed the tab instead"). Noah confirmed these
came from the same Google Analytics property as the +28% and 1.4x outcome
figures, so they are real measurements being written as rhetorical guesses. The
fix is to harden them, not soften them: state the real figures flat and tag them
`Source · Google Analytics` the way Section 05 already does.

Still needed from Noah:
- [ ] Pre-launch average time on the solution landing pages
- [ ] Exit or bounce rate on those pages

Until those land, the rewrite can be drafted with the figures left as explicit
placeholders. Never fill them with an estimate.

**Also uncommitted in the working tree as of 2026-08-19** (approved in
conversation, not yet reviewed on screen or pushed):
- `index.html` intro line shortened to "Product designer in Milwaukee,
  Wisconsin, open to remote. I redesign the systems people rely on every day."
  The old trailing list named only 2 of the 4 case studies.
- Sticky nav on all four interior pages. `.top` was never sticky, but `.mode`
  (the TL:DR/Full bar) was sticky at `top: 0`, so on scroll the nav vanished and
  the reading-mode bar took the top edge. `.top` is now sticky at `top: 0`,
  `z-index: 70`, opaque paper background. `.mode` moved to `top: 62px` to sit
  under it, and its wide-screen fixed position moved from `top: 60px` to `96px`
  for header clearance.

---

## cs-lincoln.html — Lincoln Nautilus (Documentation Done, Ready to Draft)

### The Car
Confirmed: 2024+ Lincoln Nautilus, "Lincoln Digital Experience" — a 48" panoramic display replaces the gauge cluster/speedometer/fuel entirely, plus a separate lower touchscreen handles climate/media/nav. Sister's car, her daily driver.

### Method
Had sister (real owner, real daily use) list grievances while driving on 2026-07-05, filmed the specific screens and interactions as she hit them. Real-world usability testing, not a staged redesign exercise — that's the credibility of this piece.

### The Thesis
One argument ties all three problems together: physical controls survived a century of car design because they're operable blind. Every failure here is the same failure — a blind-operable analog control replaced by a touch/gesture interface that demands visual confirmation before it works.

### Three Problems (real evidence, independently confirmed by press/CR)
1. **Vents** — changing airflow direction takes 3 taps into a sub-menu, landing on a screen that also controls vent mode (face/feet), recirculate, on/off, sync temp, and Max AC; direction itself is set by a touch-and-hold-drag per vent on a small target. Previously a one-hand flick, done blind, mid-drive. Separately, temp (driver/passenger), heated/cooled seat and wheel, fan speed, and AC on/off live in a "persistent" bar elsewhere in the UI — still touchscreen, not physical. Consumer Reports flags the identical issue almost verbatim: "the automaker forcing the driver to adjust the direction of the air vents by way of the infotainment screen."
2. **Media/options menu** — a flat, undifferentiated grid mixes Google Maps, Play Store, texts, CarPlay, AM/FM, SiriusXM, Bluetooth with no hierarchy. Sister found it confusing to parse at a glance while driving.
3. **Steering wheel touchpads** — capacitive swipe pads, no labels, noticeable input lag, no tactile feedback. The dynamic-mapping concept (left = cruise/speed, right = media/volume) is undermined by having no confirmation you've hit the right zone without looking down. Consumer Reports calls this out by name and notes Lincoln carried over the same approach from recent Lexus models, where it was also disliked.

Bonus data point: a CR test unit had a 36-hour touchscreen failure where the *only* function that kept working was climate temperature — everything else, including the vents, went dark. Good illustration of the risk in centralizing every control into one screen with no physical fallback.

### Industry Context (why this lands now, not just "personal opinion")
- 97% of new cars sold since 2023 ship with at least one touchscreen. A federal bill (Driver Technology and Pedestrian Safety Act, Rep. Kevin Mullin, introduced Feb 2026) calls for an official study on touchscreen-driven distraction.
- Euro NCAP's 2026 protocol denies a 5-star safety rating to any car that puts turn signals, hazard lights, horn, wipers, or eCall behind a touchscreen instead of a physical control — citing research that 2 seconds of visual diversion doubles crash risk.
- VW's design chief announced in 2025 that buttons are returning to every future VW: "It's not a phone, it's a car." Broad trade coverage (Autoblog, CarsGuide, DesignNews) frames this as an industry-wide reversal already underway.
- Framing payoff: Lincoln built this exact interior at the moment the rest of the industry started walking this back.

### Structure Plan
1. Hook/method — real user, real drive, grievances logged live, not staged.
2. Industry context — establishes this as a systemic reckoning, not a nitpick.
3. The thesis — blind-operability as the constraint that got dropped.
4. Three problem/fix pairs, each: evidence photo → grievance in her words → why it fails (+ CR/journalist corroboration) → one focused high-fidelity redesign mockup of just that screen. Deliberately NOT a full ground-up OS redesign — a full rebuild risks reading as a generic concept-car Dribbble piece and dilutes the sharper point. Three precise fixes read as stronger design judgment.
   - Vents → physical control cluster (dial or buttons, tactile detents) for vent mode + direction, paired with a small status display. See Design Decisions below — this replaced the earlier "flatten the touchscreen menu" idea.
   - Media menu → grouped top-level categories (cite Hick's Law: more structure beats fewer taps when the choice set is this mixed)
   - Steering wheel → fixed, non-dynamic mapping + tactile detents + audio/haptic confirmation, no lag
5. Close — tie back to Euro NCAP/VW: this isn't nostalgia for buttons, it's re-applying the constraint touchscreens forgot.

### Design Decisions — Working Notes
Talked through problem framing and fix direction with Claude before touching Figma, one problem at a time. Status per problem:

- **Vents — decided (2026-07-16).** Rejected the original plan's fix ("keep it digital, just surface vent controls without the sub-menu") — a touch-and-hold-drag to aim airflow still requires visual confirmation no matter how few taps it takes to reach it, so flattening the menu doesn't solve blind-operability, only menu depth. Fix direction: physical control cluster with tactile detents for vent mode/direction (dial or buttons, TBD in Figma), paired with a small status display — same pattern as the Genesis G70 comparison (buttons for anything you'd want to operate blind, a small screen for status/discovery only). Also referenced: Dodge vehicles have the same 1-2 screen climate-control complaint, so this isn't Lincoln-specific. Open question before Figma: dial vs. individual buttons for vent mode/direction.
- **Media menu — not yet discussed.**
- **Steering wheel touchpads — not yet discussed.**

### What This Case Study Needs to Show (that ACRO doesn't)
- **Product complexity** — multi-state interfaces, edge cases, error states
- **Design systems thinking** — components, states, scalability
- **Safety/constraint reasoning** — physical hardware limitations, eyes-off-road cost
- **User-centered framing** — real frustrated user (sister), real task flows, corroborated by independent professional reviews

### Before Publishing — Redaction Needed
Source screenshots currently show identifying info: contact name/photo on the phone-pairing screen, a specific street-level map location. Crop/blur before any of these go into the live case study.

### Sources
- [Vehicle touchscreen frustration & safety concerns — Rep. Kevin Mullin](https://kevinmullin.house.gov/2026/02/03/vehicle-touchscreen-frustration-safety-concerns/)
- [Euro NCAP brings back car buttons by 2026 — Euro Weekly News](https://euroweeklynews.com/2025/11/14/europes-war-on-touchscreens-new-2026-rules-will-force-carmakers-to-bring-back-buttons/)
- [Cars will need buttons not just touchscreens for 5-star Euro NCAP rating — ETSC](https://etsc.eu/cars-will-need-buttons-not-just-touchscreens-to-get-a-5-star-euro-ncap-safety-rating/)
- [VW Design Boss Confirms Buttons Coming Back — InsideEVs](https://insideevs.com/news/752840/vw-brings-back-buttons-switches/)
- [2024 Lincoln Nautilus Road Test Report — Consumer Reports](https://www.consumerreports.org/cars/lincoln/nautilus/2024/road-test-report/)
- [2024 Lincoln Nautilus First Drive Review — The Drive](https://www.thedrive.com/car-reviews/2024-lincoln-nautilus-first-drive-review)
- [2024 Lincoln Nautilus First Drive Review — Autoblog](https://www.autoblog.com/reviews/2024-lincoln-nautilus-first-drive)
- [The Lincoln Nautilus Changed My Mind About Screens And Touch Controls — TopSpeed](https://www.topspeed.com/lincoln-nautilus-changed-my-mind-screens-touch-controls/)

### Next Steps
- [ ] Draft actual case study copy for cs-lincoln.html from this plan
- [ ] Produce the 3 high-fidelity redesign mockups (vents, media menu, steering wheel)
- [ ] Redact identifying info from source images/video before use
- [ ] Confirm final selection of which photos/video clips make the cut
- [ ] Check whether Lincoln updated the UI for 2025/2026 model years — if so, frame explicitly as a 2024-2025 audit

---

## cs-homelab.html — The Command Center (Complete, Live)

**Status:** Complete and live on the site as of 2026-07-25. All placeholder
screenshots have been replaced with real photography, and the copy has been
through several full revision passes since the initial 2026-07-23 build.
Read the file itself for the real copy, not this note.

**The one-line pitch:** a from-scratch replacement for an existing homelab
status dashboard, evaluated against the popular self-hosted alternatives
first, directed end to end in a weekend, with a built-in AI judgment layer
(plain-English verdict, color only when earned) and real text-based control
(start/stop VMs, monitoring alerts, update notifications) as shipped
features a distributed, built-for-everyone dashboard tool can't offer.

**Section 03, "How It Was Built," was cut entirely (2026-07-25).** It
originally covered the AI-assisted build process and credential scoping.
Noah's call: he wouldn't hide that AI built this if asked directly in an
interview, but he doesn't want it stated outright in the written case
study copy, and any honest version of that section has to say so. Rather
than force an oblique version, it was deleted. **Do not re-add a section
about the build process or AI's role in construction** — that's a
conversation topic, not page content. One consequence: the
credential-scoping/least-privilege angle (see below) no longer appears
anywhere in the shipped copy.

**Current section numbering:** 01 Context, 02 What Makes It Different,
03 Proof Not Just Process, 04 Screens, 05 Where It Stands.

**Section 03 ("I asked for a second opinion. Reviewers made real
upgrades.") is the strongest evidence in the piece, but mind a real
distinction inside it:** the two AI reviewers (visual persona + UX
persona) caught the dashboard quietly breaking its own "color only when
earned" rule — that catch has no screenshot. The before/after layout
images (`hl-layout-before.png` / `hl-layout-after.png`) illustrate a
*different* bug Noah caught himself on a live look, not something the
two reviewers found. The headline was rewritten specifically to stop
implying the screenshots are the reviewers' catch — preserve that
distinction if this section is touched again.

**Real screenshots, final mapping (2026-07-25):**
- `hl-home-calm.png` — hero + Fig. 04, a real calm-state verdict card
- `hl-vm-control.png` — Fig. 02, phone screenshot of the Telegram bot
  (`/vmstatus`, `/vmstart`, `/vmstop`, a live monitoring alert), capped at
  320px wide since a full-width phone screenshot dominated the page
- `hl-iteration-early.png` — Fig. 03, the actual pre-redesign UI (2026-07-17)
- `hl-home-watch.png` — Fig. 05, a real outage (arr stack down, homeai
  offline), cropped to the domain drill-down panels, not the top hero
- `hl-layout-before.png` / `hl-layout-after.png` — Media-panel crops
  showing the real dead-space bug and its fix
- `hl-old-dashboard.png` was cut after being wired in. It showed the
  actual old Homepage (the open-source project) instance, but Noah judged
  it added nothing to the study once he saw it in place. Don't re-add it.
- `hl-home-full.png` — Fig. 06, added 2026-07-25, closing shot of the
  Screens section. Full Home tab (status hero, Bookmarks, Calendar),
  cropped from a raw browser screenshot in `assets/dashboard/` with all
  browser chrome removed to match the other figures. A coworker's name
  was redacted (painted out) from the Calendar card before publishing.

### What This Case Study Needs to Show (that ACRO and Lincoln don't)
- Real product taste and direction, evaluating what already exists before
  deciding to build something better, not just visual design in isolation.
- Real, verifiable iteration with a genuine before/after moment (the
  layout fix), not just a single polished final screenshot.
- Security/systems literacy (credential scoping, least privilege) was
  originally meant to live here, but that material left with Section 03
  (see above) and isn't represented in the current copy. If it ever needs
  to come back, it needs a home that isn't a dedicated build-process
  section.

### Still Open
- [x] `index.html` links to this case study from the Selected Work list —
      confirmed live 2026-07-27, this item was stale.
- [ ] No outcome/impact number, by deliberate choice (confirmed with Noah
      2026-07-23). Revisit only if a real one turns up. Do not fabricate.

---

## about.html — About Me (Complete, Live 2026-07-27)

**Format:** intro paragraph (Noah's own words, verbatim, not written by Claude)
followed by a 2x2 grid of four black-and-white, square-cropped photos, each
with a plain two-part mono label (no wry/caption-style copy — that tone was
tried first and explicitly rejected as "not going to fly at all, super
casual"). B&W treatment follows the standing FABLE_BRIEF.md spec for this page.

**The four photos, in order:**
1. California coastline · San Diego — Torrey Pines bluffs, camera raised
2. Autocross · Milwaukee — mid-corner action shot, Genesis G70
3. Keyboard Build · MODE — mid-teardown, switches pulled, not a styled finished shot
4. LED Wall · Music-Reactive, MP3 jack — the room's audio-reactive light
   install, monitor visibly showing the FastLED/Arduino code driving it

**Selected from a 20-photo pool, cut and why:**
- Both mini-ITX PC build photos and the homelab rack — same "builds his own
  gear" trait as the LED wall and keyboard, a third repeat added nothing
- Golf — decent photo, didn't clearly earn a distinct trait
- A second Korea/lanterns camera photo — duplicated the California shot's
  "observation" beat
- **Wedding photo and a Korea/palace couple photo were deliberately left
  out** — flagged to Noah as a judgment call (spouse photos shift the page
  from "evidence of how I think" to "personal life," closer to the
  oversharing risk he was trying to avoid), and he agreed to leave both out.
- The LED-wall video was shot but not used — "let's do those without the
  video then, just easier for now." Stills only for this round.

**Nav wiring:**
- Homepage (`index.html`) contact row: email · LinkedIn · Resume · About Me
- Top nav of `cs-acro.html`, `cs-sharepoint.html`, `cs-homelab.html`: now
  Index · About Me · Resume
- **`cs-lincoln.html` was deliberately skipped** — it's still the generic
  unbuilt template stub (different fonts/colors entirely, not even reachable
  from the homepage with a real link), so there was no real nav to add to.
- The About Me page's own nav is Index · Resume only (no self-link), per
  explicit instruction, matching how case studies never link to themselves.

**Source photos:** originals (color, full-res) live locally in
`assets/about me/` (note the space in the folder name — untracked,
not pushed to the public repo). Superseded by the cropped B&W webps in
`resources/`, kept only as Noah's local backup.

---

## Resume Conversions

**No Microsoft Word, Pages, or LibreOffice on this Mac.** When the resume
needs updating from a `.docx` source and only that format is available:
1. `textutil -convert html` (built-in) to get the docx content out losing
   minimal formatting for a simple single-column resume.
2. Print that HTML to PDF via headless Brave (`--headless --disable-gpu
   --print-to-pdf=...`). Brave/Chromium's `--print-to-pdf-no-header` flag did
   **not** suppress the browser's auto-inserted date/URL header and page-count
   footer in practice — instead, crop them out afterward with `pypdf` by
   shrinking the page's MediaBox/CropBox a fixed amount off the top and
   bottom (measured by rendering to PNG and checking for non-white rows).
3. **Watch the resulting font sizes.** A plain Word doc export can carry much
   smaller point sizes than a designed resume — the 2026-07-27 update came in
   at 10-11pt body / 20pt name against the previous (Illustrator-designed)
   resume's 14.6-24pt, and looked "super tiny" by comparison once live, even
   though nothing was technically broken. Fixed by scaling every `px` value
   in the intermediate HTML by ~1.35x before printing to PDF. Sanity-check
   new conversions against the old file's embedded font sizes (`pikepdf`,
   look for `Tf` operators in the content stream) before shipping.
4. If a live change looks stale after pushing, check the CDN response
   directly (`curl -sI https://noahschilling.com/...`) before assuming the
   deploy failed — GitHub Pages/Fastly served the fresh file within seconds
   both times this came up; the stale copy was the browser's own cache.

---

## Portfolio Strategy

**Targeting:** Mid-to-senior and senior product design / UX roles
**Approach:** Apply to senior postings aggressively — fewer applicants, and a strong candidate willing to grow is often more appealing than a safe mid-level hire

**Where ACRO works well:**
- Agencies and studios doing brand/web/marketing work
- Small to mid-size companies hiring first or second designer
- Industrial, manufacturing, B2B SaaS companies

**Where ACRO needs backup (Lincoln's job):**
- Big tech or growth-stage product companies
- Senior roles expecting product complexity, systems thinking, multi-case breadth

**Recommendation:** Start applying now to the first category while building Lincoln. Use applications as research — signal on how the portfolio lands informs what Lincoln needs to say.

