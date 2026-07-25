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

**Design direction:** See `FABLE_BRIEF.md` — this is the active, authoritative design brief. It is rewritten from scratch each time the direction changes; do not infer design system, colors, or type from git history or old commits.

---

## File Structure

```
index.html          — Portfolio homepage
cs-acro.html        — ACRO case study (complete, richest material)
cs-sharepoint.html  — SharePoint IA case study (active, in progress)
cs-lincoln.html     — Lincoln case study (stub, not started)
cs-homelab.html     — Command Center case study (built 2026-07-23, placeholder screenshots pending)
assets/fonts/       — SF Pro Display OTF (Light, Regular, RegularItalic, Medium)
resources/          — Images, video, resume
  acro-robot-index.webm
  acro-solutions-index.webm
  acro-dispensing-before.webp
  acro-dispensing-after.webp
  acro-solutions.webp
  acro-services.webp
  acro-aboutus.webp
  sp-homepage.png
  sp-it-site.png
  Noah_Schilling_Product_Design.pdf
CLAUDE.md            — this file: workflow, project facts, case study material
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
- [ ] `index.html` doesn't link to this case study yet — it's not in the
      homepage's Successes list. Needs its own decision on where it slots
      in and what the index copy says, not assumed here.
- [ ] No outcome/impact number, by deliberate choice (confirmed with Noah
      2026-07-23). Revisit only if a real one turns up. Do not fabricate.

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

