# Deploy & Responsive — Design Spec
Date: 2026-05-29

## Goal
Make the site publicly accessible and fully responsive across desktop, tablet, and mobile.

## Part 1 — GitHub Pages Deployment

**What:** Enable GitHub Pages on the existing GitHub repo (`valentinasheshunova-spec/valentina-pm`) and push current code.

**How:**
- Enable Pages via `gh` CLI: source = `master` branch, root folder `/`
- Push `index.html` and assets to `master`
- Public URL: `https://valentinasheshunova-spec.github.io/valentina-pm/`
- Future updates: `git push` → auto-deploy in ~1 minute

**Out of scope:** custom domain, CI/CD pipelines, build step (site is plain HTML).

## Part 2 — Responsive Audit and Fix

**Breakpoints to test:**
| Viewport | Target device |
|---|---|
| 375px | Phone (iPhone SE, Android) |
| 768px | Tablet (iPad) |
| 1440px | Desktop (baseline, already works) |

**Existing breakpoints in CSS:** `640px`, `900px`, `1100px` — preserved as-is. Only fix broken sections, no full rewrite.

**Sections to audit:**
1. Hero (name, photo, CTAs)
2. Logo strip ("Работала с")
3. Cases / кейсы
4. Process / процесс
5. Experience / опыт
6. Artifacts — Roadmap Gantt + CJM (most complex, SVG/canvas)
7. Testimonials / отзывы
8. FAQ
9. Footer

**Done criteria:**
- No horizontal scroll at 375px or 768px
- All text readable (min 14px effective size)
- Tap targets ≥ 44px
- Tables and diagrams contained within viewport (scroll inside container if needed)
- No overlapping elements

**Approach:** Screenshot each section at 375px and 768px → identify issues → patch CSS in `index.html` `<style>` block → re-screenshot to confirm.
