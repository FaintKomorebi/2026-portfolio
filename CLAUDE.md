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

---

## Design System

### Colors
```
--bg: #f0ece6        warm off-white background
--ink: #131313       primary text
--mid: #6e6b65       muted text / secondary
--faint: #e2ddd7     borders, dividers
--dim-bg: #e8e4de    slightly darker bg tint (case study pages)
#4ade80              green status dot (index footer)
```

### Typography
```
--serif: 'Instrument Serif'   headlines, display, italic accents
--sans:  'IBM Plex Sans' 300  body, descriptions
--mono:  'IBM Plex Mono'      labels, tags, metadata, CTAs
```

### Spacing Scale
```
--s1: 8px   --s2: 16px   --s3: 24px   --s4: 40px
--s5: 64px  --s6: 96px   --s7: 140px  --s8: 200px
--pad: 60px (desktop) → 28px (960px) → 20px (768px) → 18px (640px) → 14px (480px)
```

### Grid
- All sections: `repeat(12, 1fr)` with `gap: var(--s3)`
- Col 1: vertical section index labels
- Cols 2–7: main content
- Cols 8–12: aside / options / metadata
- Mobile (960px): all columns collapse to `1 / 13`

### Tone
Calm, editorial, mature. Muted by default. Interactions are subtle — opacity dims, soft transitions. No loud colors or aggressive animations.

---

## File Structure

```
index.html          — Portfolio homepage
cs-acro.html        — ACRO case study (complete, shipped)
cs-lincoln.html     — Lincoln case study (stub, not started)
cs-homelab.html     — Homelab case study (stub, not started)
resources/          — Images and videos
  acro-robot-index.webm
  acro-solutions-index.webm
  acro-dispensing-before.webp
  acro-dispensing-after.webp
  acro-solutions.webp
  acro-services.webp
  acro-aboutus.webp
```

---

## index.html — Current State

- Hero: "Diagnosis before design." — live CST time + experience counter (updates every minute)
- 3 case study slots: ACRO (complete), Lincoln (TBD), Homelab (TBD)
- Case study hover: siblings dim to 0.3 opacity, hovered gets rainbow glow (`conic-gradient`, `filter: blur(28px)`, `opacity: 0.18`)
- Sections: Work, Thinking (empty), Capabilities, Contact
- Contact headline: "Open to the right opportunity."
- Footer: © 2026 Noah Schilling | Available Now [green pulse dot]
- Nav: fixed, active section highlight with sliding underline via `getBoundingClientRect`
- Mobile breakpoints: 960px, 640px, 480px

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

### Reading Mode Toggle
- Default: `<body data-view="full">`
- Nav control: TLDR (30s) / Full (3m)
- `.full-only` hidden in TLDR, `.tldr-only` hidden in Full
- Body opacity fade (150ms) on switch

### Layout
- `.section-content` / `.decision-content` / `.impact-numbers`: `grid-column: 2 / 7`
- `.section-aside` / `.decision-options` / `.impact-reflection`: `grid-column: 8 / 12`
- `.fs-featured`: `grid-template-columns: 3fr 2fr` (video / annotations)
- TLDR impact numbers: `grid-column: 3 / 11` (centered)
- Impact stats: side-by-side `1fr 1fr` grid within left column
- TLDR Final Solution: `grid-template-columns: 1fr` (full width video, annotations removed)

### Sections
- Hero: tag, title, summary, metadata (My Role, Timeline, Outcome)
- Fig. 1: hero video (acro-robot-index.webm)
- TLDR block: 5-sentence summary (tldr-only)
- Overview: h2, body, aside (The brief / The real problem / Constraints)
- Site Architecture: before/after sitemap tree comparison — warm amber path highlight on Before (Solutions Overview → Dispensing Systems), same highlight on After (Index + Solutions ↓)
- Decision: pull quote, 3 body paragraphs (full-only), options considered block
- Final Solution: featured video with 3 annotations (full-only)
- Before/After: dispensing-before.webp + dispensing-after.webp with descriptive labels
- Impact: +28% and 1.4× stats side by side, "What I'd do differently" reflection (full-only)
- Next project: placeholder (href="#", "Your Second Project")
- Footer: back to all work link

### Mobile Breakpoints (cs-acro.html)
```
960px: grid collapses, hero single column, --pad: 28px
768px: --pad: 20px, hero-image padded, hero-video full width
640px: fs-featured single column, impact-numbers single column
480px: --pad: 14px, nav name hidden, typography bumped up:
  .hero-title: clamp(46px, 12vw, 64px)
  .section-hed: clamp(30px, 7vw, 40px)
  .decision-pull: clamp(22px, 5.5vw, 30px)
  .impact-num: clamp(48px, 12vw, 64px)
  .next-title: clamp(30px, 7vw, 44px)
```

### Known Remaining Items
- "Next project" link still points to `href="#"` — update when Lincoln is ready
- 3 secondary screen slots in Final Solution still needed (real screenshots)
- TLDR text references the decision section but Decision pull quote is the only TLDR-visible element from that section

---

## cs-lincoln.html — Lincoln Nautilus (Not Started)

### Plan
Redesign critique of the 2024 Lincoln Nautilus infotainment / interior UI.

**Why:** Noah drove the car regularly and found the UI genuinely frustrating — specific, real reactions, not a contrived redesign exercise. Sister owns the car and visits every 2-3 weeks.

**Documentation session planned:** In-car recording session when sister visits (~2-3 weeks out). Record all screen flows, button layouts, physical control placement, every major task: navigation input, climate, audio, phone, driver settings.

### What to Capture
- Every interaction that requires eyes off road
- Every task that takes more than one tap
- Anything that gives no feedback or shows wrong state
- Physical relationship between touch controls and hardware buttons
- The moments of genuine frustration — those are the brief

### What This Case Study Needs to Show (that ACRO doesn't)
- **Product complexity** — multi-state interfaces, edge cases, error states
- **Design systems thinking** — components, states, scalability
- **Safety/constraint reasoning** — physical hardware limitations, eyes-off-road cost
- **User-centered framing** — real frustrated user (Noah), real task flows

### Pre-Session Prep
- Watch 2024 Nautilus infotainment walkthroughs on YouTube
- Write down the 3-5 specific interactions that frustrated you most (from memory)
- Check if Lincoln has updated the 2025 model — if so, frame as 2024 audit

### Framing Note
This should not be a "visual redesign." It needs to tell a systems story: broken interface, why it breaks (at the component and flow level), how to fix it. That's what gets this into senior product design conversations.

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

---

## Decisions Made (Don't Revisit Unless Asked)

- No shared CSS file — all styles are inline per-page. Keep it that way unless explicitly asked to extract.
- TLDR Final Solution annotations removed — they were generic ("Getting There Quickly", "Ease of Use"). Video is full-width in TLDR.
- "Tools" row removed from hero metadata — Figma/Adobe Suite adds nothing to the story.
- Aside block: The brief / The real problem / Constraints — these replaced a second body paragraph that was repeating the same content in prose form.
- Before/after labels are descriptive: "Detail page — Before (nested three levels deep)" and "Detail page — After (directly accessible, industry context visible)"
- Sitemap path highlight: warm amber `rgba(185, 115, 45, 0.13)` / `#a06830` — class `.tree-path`
- Hero tag: "2025 · Industrial" (not "Shipped · Industrial · 2025")
