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
cs-homelab.html     — Command Center case study (draft copy finalized 2026-07-23, ready to build)
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

## cs-homelab.html — The Command Center (Draft Copy Finalized, Ready to Build)

### The Project
A from-scratch replacement for the status dashboard on a self-hosted homelab
running 15+ services (Proxmox, Immich, Jellyfin, the arr media stack,
Paperless, Healthchecks, Tailscale, and more). The old dashboard was a
generic bookmark-grid tool. It worked, but it wasn't tailored to Noah: no
real status awareness, no design language of his own, no accommodation for
what he actually wanted day to day. Noah evaluated the popular self-hosted
alternatives directly (ran them, lived with them) before concluding none of
them would ever become genuinely his without fighting their defaults the
whole way, and directed a full custom replacement instead, built to his own
spec in roughly a weekend. Internally called "the Command Center."

Working title for the case study: **The Command Center**.

### Method (framing corrected 2026-07-23, see below)
Directed end to end using Claude Code as the builder, with Noah owning every
decision that outlives the build itself: visual design, what data/systems
each credential is allowed to touch, and the standing rule that the AI's
judgment layer never gets to decide its own color or copy, only the
interface does. The standout feature isn't just that AI helped build it,
it's that an AI judgment layer is a permanent, shipped part of the finished
product, something off-the-shelf homelab dashboards (Homepage, Glance, and
the rest Noah evaluated first) don't have out of the box.

**Framing correction, important, read before touching the copy below:**
An earlier planning pass (preserved in "Supporting Evidence" below) framed
this as a multi-week epic and leaned on a "didn't write every line myself"
angle. Noah corrected both after reading the first full draft: this was a
weekend build, not a multi-week saga, and the "didn't type every line"
framing read as a hedge, not a strength. The corrected, approved angle:
he evaluated the market, decided nothing else would ever be truly his, and
directed a custom build to his own spec, with AI as the builder and the
judgment layer as a real shipped feature, not a build-process footnote. The
final draft copy below reflects the corrected framing and is the one to
build from, not the older "Thesis/Three Principles" language further down.

### Final Draft Copy (approved 2026-07-23, ready to build into the HTML)
Reviewed once already by an independent design-hiring-manager-persona
critique (dispatched as a background agent, not a build agent, mirroring the
project's own "commission a second opinion, inspect the real thing" habit).
Its main findings, already applied below: promote the strongest evidence
(the dual-AI-critique story) so its headline survives the page's TL;DR
toggle instead of hiding behind it; state the AI/Noah division of labor once
instead of three times and let the evidence carry it after that; cut the
vague "accessibility" claim down to the one concrete thing that's actually
true (the verdict is always plain language, never color alone); and drop
the outcomes-are-later hedge in the close for something concrete instead.

Section markers below (`full-only` / `survives TL;DR`) describe how each
section should behave under the site's existing TL;DR reading-mode toggle,
same mechanism cs-sharepoint.html already uses: `full-only` content
disappears entirely in TL;DR mode, everything else keeps its heading visible
and only its body/asides collapse.

---

**HERO**
> Case Study 03 · Homelab Command Center · 2026 · Live
> **H1:** I ran the homelab dashboards worth running. None of them would ever be mine, so I built the one that was.
> **Lead:** A weekend build, directed end to end, in my own design language, nothing extra. It doesn't just show status, it tells me in plain English what actually needs my attention.

**SPEC STRIP**
- Role: Product Direction
- Timeline: 2026 · one weekend
- Scope: 15+ services, one interface
- Status: Live · daily use

**01 · Context** *(full-only, hidden in TL;DR)*
> **H2:** The dashboard I had worked. It just wasn't mine.
>
> I was already running a full homelab dashboard, a clean bookmark grid with a few basic status widgets. It worked fine. But it was a stock layout built for a version of a homelab that wasn't mine. Before touching a single line, I actually ran the popular alternatives myself, lived with them for a while, and judged what each one got right and where each one fell short. None of them were ever going to become genuinely mine without fighting their defaults the whole way. So instead of settling on the next off-the-shelf option, I directed a full custom replacement built to my own spec from day one.
>
> **Aside, "The Bar":** Everything the old dashboard did, plus a layer that actually tells me what matters, plus my own design language, minus every bit of bloat I never used.
>
> **Aside, "The Research":** Ran the popular self-hosted dashboard tools directly before deciding none of them were worth adapting instead of building.

**02 · What makes it different** *(headline survives TL;DR)*
> **H2:** Most dashboards show you data. Mine tells you what matters.
>
> Every homelab dashboard shows status: a green light, a red light, a wall of numbers. Mine watches everything running underneath it, servers, backups, containers, storage, and writes a plain-English verdict: calm, or exactly what needs a look and why. When everything's fine, it says so quietly and gets out of the way. Color only shows up when a problem has actually earned it, and the verdict is never color alone, always plain language too. That's a real accessibility call, not a style choice, nothing important here is readable by color vision alone. It's a permanent feature of the finished dashboard, running every day, not a build tool that disappears after launch, and it's the one thing none of the off-the-shelf options ship with.

**03 · How it was built** *(headline survives TL;DR)*
> **H2:** AI did the building. I owned everything that outlives it.
>
> AI did the building. I owned every decision that outlives the build: what it looks like, and what each credential is allowed to touch. Every credential starts locked to exactly what one piece needs, nothing more, widened only on a direct call, never by default.

**04 · I asked for a second opinion, on purpose. It caught a real mistake.** *(headline promoted to survive TL;DR, this is the strongest evidence in the piece per the outside critique, don't let it hide behind the toggle)*
> Partway through, I had two AI reviewers critique the live dashboard under different lenses: one purely visual, one purely how I actually use it day to day. Both had to actually go look at the running app, not just reason abstractly. Both came back with specific, uncomfortable findings, including one that caught the dashboard quietly breaking its own rule that color only shows up when it's earned. I didn't act on any of it automatically. Every recommendation went through the same question as everything else in this build: does this actually serve how I use it, or is it just noise.
>
> Same standard applied to the build itself. An early layout that looked clean in a screenshot was actually hiding real dead space, a grid stretching every panel to match its tallest neighbor. Caught on a live look, not a report, and fixed before anyone but me ever saw it.

**05 · Where it stands** *(headline survives TL;DR)*
> **H2:** Live, every day, since the weekend I shipped it.
>
> It replaced the old dashboard the weekend I shipped it, and I've opened it first every morning since. When it stays quiet, everything's fine. The only time it uses color, something actually needs me. That's the whole product.

---

### Supporting Evidence (raw material behind the copy above, historical, framing/timeline superseded)
The original planning pass below over-specified this as a multi-week build
and leaned on a "didn't write every line" framing that Noah rejected on
review (see "Framing correction" above). The underlying technical evidence
is still accurate and still useful as deeper raw material if the case study
ever needs to expand (e.g. a technical-detail hover state, an appendix, or
answering a follow-up question in an interview), it's just not the language
or timeline to build the live page from:
- Credential scoping: the dashboard's Proxmox token is read-only, kept
  deliberately separate from an unrelated bot's power-management token. A
  cross-host SSH bridge was locked to one fixed command and verified live by
  sending it an unrelated command and confirming it was silently refused.
  The same pattern got reused for four more bridges over the life of the
  project without ever inventing a new mechanism.
- The AI layer originally was going to use a paid API key. Caught live,
  mid-build, after asking "does this cost more than a plan already being
  paid for?", yes, so it was switched to reuse an already-authenticated
  session instead, tradeoffs written down rather than hidden.
- The dead-space layout bug (now the centerpiece of section 04 above): an
  early layout paired panels side by side, looked clean in a screenshot,
  and was live-reviewed to reveal a two-column grid stretching every panel
  to match its tallest neighbor. Fixed with a self-balancing column layout,
  verified against the same uneven real data that exposed the problem.
- Two independent AI critiques (a visual/UI persona and a product/UX
  persona) were commissioned specifically to inspect the live app and
  critique it, not build anything, catching (among other things) the
  dashboard quietly breaking its own "color only when earned" rule. Full
  critiques preserved in the project's own `PHASE2_PLAN.md`.
- A round of visual changes once shipped verified only by a passing build
  and a health-check ping, not a real look, and contained a real bug (a
  launcher grid had silently collapsed to single-column). The very next
  round shipped three more bugs the same way. The process was corrected
  after that: screenshot the actual result and inspect it before claiming
  anything is fixed, a rule that then caught all three bugs plus a further
  regression its own first pass introduced.

### What This Case Study Needs to Show (that ACRO and Lincoln don't)
- Real product taste and direction, evaluating what already exists before
  deciding to build something better, not just visual design in isolation.
- Real judgment about where AI belongs in a product and where it doesn't,
  directly relevant to how design roles are actually changing right now.
- Security and systems literacy (credential scoping, least privilege,
  verification over trust) that most design portfolios don't touch at all.
- Real, verifiable iteration with a genuine before/after moment (the
  layout fix), not just a single polished final screenshot.

### Assets Needed
- Real screenshots already exist from the build itself: the layout
  before/after, the calm/watch/urgent color states, light and dark themes.
  Need to pull final clean versions from the build's own review artifacts.
- Redact real IPs, hostnames, and any other personally identifying
  homelab specifics before anything goes live, same discipline as
  Lincoln's note about the phone-pairing contact photo.
- No outcome/impact number for now, by deliberate choice (confirmed with
  Noah 2026-07-23). Revisit later if a real one turns up. Do not fabricate.

### Next Steps
- [x] Confirm/correct the framing with Noah before finalizing copy — done
      2026-07-23, see "Framing correction" above
- [x] Draft actual case study copy for cs-homelab.html — done 2026-07-23,
      independently reviewed once by a design-hiring-manager-persona
      critique, feedback applied, see "Final Draft Copy" above
- [ ] Gather and clean the real screenshots (layout before/after, color
      states, both themes)
- [ ] Build the approved copy above into cs-homelab.html (currently still
      the blank template scaffold, no case-study code written yet)
- [ ] Redact IPs/hostnames/personal homelab specifics before publishing
- [ ] Revisit an outcome/impact stat later, only if a real one shows up

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

