# Portfolio Brief — Noah Schilling (v2)

Read this at the start of every session. This is the active brief for `2026-portfolio v2`.

---

## Critical Workflow Rule

**Always `git push origin main` immediately after every `git commit`.** Chain them with `&&` in the same command. The site is hosted on GitHub Pages — commits that aren't pushed don't exist.

**Preview:** `python3 -m http.server 3000` from project directory. Check localhost:3000 before any push.

---

## Status as of 2026-06-14

**index.html — complete and looking good. Sitting with it before next move.**

The editorial/nav/hero direction is fully dead. The page has been rebuilt from scratch as a radical minimalist design: white page, name fixed top-left, all content in the right half, SF Pro Display throughout. No nav, no hero, no capabilities section. Content fades up once on load, nothing else moves.

---

## Current state of index.html

Single page, single pass. No sections, no scroll.

- **Name** — "Noah Schilling" fixed top-left, small, italic, SF Pro Display Regular Italic, color: var(--mid)
- **Intro** — "Hi, I'm Noah. A product designer based in Milwaukee, Wisconsin." SF Pro Display, ~19px, max-width 30ch
- **Two columns below intro:**
  - Successes: "Legacy turned modern website" (cs-acro.html), "How we find anything now" (cs-sharepoint.html), "The Taylor Swift problem" (no href, muted, signals in-progress)
  - Contact: Resume (PDF direct link), Info (triggers popup)
- **Info popup** — small white card, border + soft shadow, fades in, shows email + LinkedIn, click outside or Escape dismisses
- **Animation** — single staggered fade-up on load (two steps: intro first, columns 120ms later). Nothing else.

**Font:** SF Pro Display — Light (300), Regular (400), Regular Italic (400i), Medium (500). OTF files in assets/fonts/. Loaded via @font-face, no Google Fonts.

**Color palette:**
- --ink: #111113
- --mid: #6e6e73
- --soft: #b9b9be
- --faint: #d6d6db
- --hair: #ececf0
- Background: #ffffff

**Layout:** CSS Grid, 1fr 1fr, content in grid-column: 2. Collapses to full width at 860px.

---

## Decisions made — do not revisit unless asked

- **No dropdown/reveal animation on the columns.** Considered and declined. Page has six lines of content total. Hiding them behind interaction creates friction before the visitor has decided to engage. The muted Taylor Swift line also works specifically because it sits visibly next to the other two. The one load fade-up is the only motion moment.
- **No "Available now" dot.** Rejected with the previous design. Keep out.
- **No pulsing anything.** Same.
- **No Google Fonts.** SF Pro Display OTF files are local.
- **RegularItalic copied in addition to plan.** Name is set italic. Browser-synthesized slant on SF Pro looks bad vs the real face.
- **No shared CSS file.** All styles are inline per-page. Keep it that way unless explicitly asked to extract.

---

## What to try next (when resuming)

**Hover behavior on the work links.** The page currently feels slightly inert at rest after the load animation completes. The suggestion: a subtle color shift on the Successes link rows on hover. Currently they transition from --mid to --ink (0.18s ease), which is fine but minimal. Options to explore:

1. **Keep as-is** — color shift only. Simple, invisible, gets out of the way.
2. **Slight x-translate** — shift the hovered link 3-4px right on hover. Directional, implies the link is going somewhere. Very subtle.
3. **Underline on hover** — thin 1px underline, fades in, could match --faint or --soft. Familiar but honest about being a link.

No decision made. Resume here and try option 2 or 3 in browser before committing.

---

## Hard rules

- **No em dashes. Anywhere. Ever.** Use periods or rephrase. Middle dot (·) for UI separators if needed.
- Do not add features, sections, or flourishes beyond what is asked.
- Do not invent content or personality copy — wait for direction.

---

## File structure

```
2026-portfolio/
  index.html          — complete, active
  cs-acro.html        — old v1 build, not yet rebuilt in new language
  cs-sharepoint.html  — old v1 build, not yet rebuilt
  cs-lincoln.html     — stub
  cs-homelab.html     — stub
  assets/fonts/       — SF-Pro-Display OTF files (Light, Regular, RegularItalic, Medium)
  assets/acro/        — ACRO case study images and videos
  resources/          — resume PDF, SharePoint screenshots
  FABLE_BRIEF.md      — duplicate of CLAUDE.md, can be deleted
  CLAUDE.md           — this file, active brief
```

**Repo:** https://github.com/FaintKomorebi/2026-portfolio
**Hosting:** GitHub Pages

---

## Portfolio strategy

**Targeting:** Mid-to-senior and senior product design / UX roles
**Approach:** Apply to senior postings aggressively — fewer applicants, and a strong candidate willing to grow is often more appealing than a safe mid-level hire.

**Where ACRO works well:** Agencies and studios, small to mid-size companies hiring first or second designer, industrial/manufacturing/B2B SaaS.

**Where ACRO needs backup (Lincoln's job):** Big tech or growth-stage product companies, senior roles expecting product complexity and systems thinking.

---

## cs-acro.html — ACRO Automation Systems

### Project facts
- Family-owned industrial automation company (90+ year history)
- Site went from 29 pages to 17 pages
- Built in WordPress, managed by ACRO's in-house SEO team post-launch
- Timeline: 6 months | Role: Lead Designer
- Brief was officially "UI refresh" but stated goals were fewer steps + solutions as main focus

### Key outcomes
- +28% average session duration (proxy signal — engagement, not navigation)
- 1.4x CRM inquiry volume in 90 days post-launch vs. prior baseline
- Sales confirmed inquiry quality improved — prospects referencing specific solution pages

### Known remaining items
- "Next project" link still points to href="#" — update when second case study is ready
- Page not yet rebuilt in v2 design language

---

## cs-sharepoint.html — SharePoint case study

Old v1 build. Not yet rebuilt in v2 design language.

---

## cs-lincoln.html — Lincoln Nautilus (stub)

Redesign critique of the 2024 Lincoln Nautilus infotainment / interior UI. Noah drove the car regularly and found the UI genuinely frustrating. Documentation session planned when sister visits (she owns the car).

This should not be a visual redesign. Needs to tell a systems story: broken interface, why it breaks at the component and flow level, how to fix it.
