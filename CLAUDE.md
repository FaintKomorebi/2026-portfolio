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
cs-homelab.html     — Command Center case study (documentation done, ready to draft)
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

## cs-homelab.html — The Command Center (Documentation Done, Ready to Draft)

### The Project
A ground-up rebuild of the status dashboard for a self-hosted homelab running
roughly 15 VMs/containers across a dozen-plus services (Proxmox, Immich,
Jellyfin, the arr media stack, Paperless, Healthchecks, Tailscale, and more).
The old dashboard was a static bookmark grid with a few disconnected widgets.
The new one, internally called "the Command Center," unifies live status
across every service into one interface, adds an AI judgment layer on top of
the raw data, and is built for a household member who is not the operator to
eventually use too, not just the sysadmin who already knows where to look.

Working title for the case study: **The Command Center**.

### Method
Directed as a multi-week, staged build using Claude Code as the engineering
team, with Noah acting as product owner and design reviewer at every stage,
not as the person writing every line. This framing matters and needs careful
handling in the actual copy (see Open Questions below): it should read as
product/technical direction and design judgment applied to an AI-augmented
build, not as "didn't do the work." The strongest version of this case study
leans into that framing directly rather than hiding it, since directing
AI-driven engineering well is itself the differentiated skill.

### The Thesis
One question drove every real decision in this build: **how much authority
does an AI system get inside your own infrastructure, and how do you prove
it deserves that much before giving it more?**

Every interesting design choice in this project is really an answer to that
one question, applied at a different layer:
- Credentials start read-only and narrowly scoped, and only ever expand
  after the narrower version is proven to work.
- The AI proposes judgment (a structured verdict on what needs attention);
  the interface, not the AI, decides how that judgment gets shown. The AI
  never touches color, layout, or copy directly. It returns data. Code
  renders it.
- Nothing shipped as one big reveal. The build moved through explicit,
  reviewable checkpoints, and more than once a checkpoint caught a real
  problem before it reached the live interface.

This is a genuinely different pitch than "I added AI to a dashboard." It is
a case study about restraint as a design material, at a moment when most
portfolios are going to show the opposite instinct.

### Three Principles, Each With Real Evidence (structure mirrors Lincoln's
three-problem rhythm, reframed as three demonstrated principles rather than
three fixes)

**1. Access is earned, not assumed.**
- The dashboard's own Proxmox token is read-only, deliberately separate from
  a different, already-existing token that has power-management rights for
  an unrelated bot. Two credentials, two authority levels, kept apart on
  purpose.
- A cross-host bridge needed to reach one service was restricted at the SSH
  layer to run exactly one fixed command and nothing else. This was not
  taken on faith: it was tested live by sending the restricted key an
  unrelated command and confirming the system silently refused to run it.
  The same verification-by-attack pattern was reused later for a second,
  unrelated bridge built for the AI layer.
- When the AI layer needed a way to call Claude, the plan originally
  called for a paid API key. Reconsidered live, mid-build, after a direct
  cost question: does this cost more than a plan already being paid for?
  Yes. Switched to reusing an already-authenticated session instead, with
  the tradeoffs (shared rate limits, less structured output) written down
  and flagged for revisiting later rather than hidden.

**2. The AI proposes. The interface decides.**
- The AI layer returns one small, structured piece of judgment: is
  anything wrong, how urgent, and where. It never returns color, never
  returns layout, never writes prose that gets rendered as-is.
- A severity level maps to a color through code, not through the model's
  own words. Red is rare and earned. A calm homelab should look calm.
- If the AI call fails for any reason, the interface falls back to plain
  data with no fabricated judgment, automatically. Degradation was
  designed in from the first version of this layer, not patched on after
  something broke.

**3. Ship in checkpoints, not black boxes.**
- The build moved through clearly separated stages, and the riskiest ones
  (minting a new credential, wiring the AI's judgment into what the user
  actually sees) each stopped for review before the next stage started.
- The strongest evidence of this: an early layout paired panels side by
  side to reduce scrolling, and it shipped looking clean in a screenshot.
  Live review caught a real problem screenshots hadn't shown: mismatched
  panel heights left visible dead space, because a two-column grid
  stretches every panel in a row to match its tallest neighbor. Two fixes
  were weighed with real tradeoffs, a self-balancing column layout was
  chosen instead of the rigid grid, and it was verified against the same
  real, uneven data that exposed the problem in the first place. The
  before and after of this are both real screenshots, not mockups.
- A second layer of this same discipline: claims got independently
  rechecked rather than trusted at face value, more than once. A reference
  image that a build session reported as "broken" turned out to just be
  blocked by bot protection, and was a second, different image entirely
  once actually fetched correctly. A monitoring alert that looked like a
  broken backup turned out to be a misconfigured check expecting a daily
  ping from a job that only runs weekly, diagnosed by reading the actual
  scheduling config rather than accepting "it's down" as the full story.
- The sharpest instance of this discipline (2026-07-19): a round of visual
  layout changes was verified only by a passing build and a health-check
  ping, not by looking at the actual result, and shipped with a real bug
  still in it (a launcher grid had silently collapsed into single-column
  vertical stacks). Caught on direct review, fixed properly that time — and
  then the very next round of changes shipped three more visual bugs at
  once. At that point the work was deliberately escalated: taken away from
  being done directly and handed to a more capable model, with one
  non-negotiable rule attached — screenshot the actual result and inspect
  it before claiming anything is fixed. That stricter process then caught
  and fixed all three bugs, and a further regression it introduced in its
  own first pass, entirely through that same screenshot-and-verify
  discipline. This is the single most concrete evidence in the whole
  project for the thesis question itself: a system's output was trusted
  exactly as far as it had been proven reliable, and no further, and when
  it wasn't reliable enough the response was to change what was trusted
  with it, not to keep hoping the next attempt would be different.

### What This Case Study Needs to Show (that ACRO and Lincoln don't)
- Comfort directing a large, multi-stage technical build without writing
  every line personally: product and technical leadership, not just visual
  design.
- Real judgment about where AI belongs in a system and where it doesn't,
  directly relevant to how design roles are actually changing right now.
- Security and systems literacy (credential scoping, least privilege,
  verification over trust) that most design portfolios don't touch at all.
  This is the piece's sharpest differentiator.
- Real, verifiable iteration with genuine before/after evidence (the
  layout fix), not just a single polished final screenshot.

### Structure Plan
1. Hook: what a status dashboard usually is (a mirror that just reflects
   raw data back at you) versus what this one had to be (a colleague with
   judgment) and the real design question underneath: how much authority
   does it get.
2. The old state: a static bookmark grid, a dozen-plus services with no
   unified view, no judgment layer, you had to already know what mattered
   to know where to look.
3. The design philosophy, stated plainly: two surfaces (a calm daily-use
   view and a deep operational one), color as an earned signal rather than
   decoration, the AI proposes / the interface decides split.
4. The three principles above, each grounded in one specific, evidenced
   moment, not abstract claims.
5. Close: tie back to the thesis. What this proves about working with AI
   as real design material at the point where that judgment actually
   matters for how a team hires, not as a buzzword on a resume.

### Assets Needed
- Real screenshots already exist from the build itself: the masonry
  layout before/after, the healthy/watch/urgent color states, the light
  and dark themes. Need to pull final clean versions from the build's own
  review artifacts.
- Redact real IPs, hostnames, and any other personally identifying
  homelab specifics before anything goes live, same discipline as
  Lincoln's note about the phone-pairing contact photo.
- An outcome/impact number would strengthen the close (services unified
  into one view, a measurable reduction in "how many tabs did I have to
  check" is the natural candidate) but do not fabricate one. Flag as open
  if nothing solid exists by draft time.

### Open Questions Before Drafting
- Confirm the thesis framing above actually lands the way it's intended,
  or adjust it, before any live copy gets written.
- Decide deliberately how the "directed AI-driven engineering" angle gets
  framed. Handled well, this is the piece's biggest differentiator for
  2026 hiring. Handled poorly, it could read the wrong way to the wrong
  reviewer. Worth a real conversation, not a default assumption either
  way.
  - **New concrete evidence for this (2026-07-19):** before continuing the
    build's polish stage, two separate AI reviewers were deliberately
    commissioned — not to build anything, purely to critique the live app,
    each briefed with a distinct expert lens (one a visual/UI design
    persona, one a product-design persona briefed on how the app is
    actually used day to day) and required to inspect the real running app
    rather than reason abstractly. Both came back with real, sometimes
    pointed findings — including flagging that the app was breaking its
    own stated design rule about when color is allowed to appear. Nothing
    from either critique gets built automatically; every recommendation
    still goes through the same human product-owner judgment as everything
    else in this project before anything is actioned. This is arguably the
    single clearest piece of evidence for the whole "directed AI-driven
    engineering" framing: using AI as a critique instrument, not only a
    construction one, with a human deciding what's worth acting on. Full
    critiques preserved in the project's own `PHASE2_PLAN.md`.
- How much real technical/architecture detail to show versus abstract
  into pure design-decision language. ACRO and Lincoln are both readable
  by a fully non-technical reviewer; this one could lean slightly more
  technical given what it's trying to prove, which is itself a case-study
  strategy decision worth making on purpose.
- The two open items from the 2026-07-18 build review: the Home surface
  rebuild is **done** as of 2026-07-19 (hero, weather, bookmarks all
  reworked, see PHASE2_PLAN.md). The mobile layout bug is **still open** —
  independently reconfirmed as of 2026-07-19 on both Home and Cockpit (not
  fixed, not new, pre-existing). Should be resolved before this ships live
  so the case study reflects a genuinely finished v1, not a mid-build
  snapshot. Tracked in the project's own `PHASE2_PLAN.md`, not duplicated
  here.

### Next Steps
- [ ] Confirm/adjust the thesis framing with Noah before drafting copy
- [ ] Decide, on purpose, how to frame "directed AI-driven engineering"
- [x] Home surface rebuild (one of the two open build items) — done 2026-07-19
- [ ] Fix the remaining open build item (mobile layout overflow bug, still
      unresolved as of 2026-07-19) so the underlying product matches what
      the case study will claim
- [ ] Gather and clean the real screenshots (layout before/after, color
      states, both themes)
- [ ] Draft actual case study copy for cs-homelab.html from this plan
- [ ] Decide on a real outcome/impact stat, or deliberately omit one
- [ ] Redact IPs/hostnames/personal homelab specifics before publishing

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

