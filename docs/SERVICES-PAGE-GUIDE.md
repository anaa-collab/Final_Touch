# Final Touch Cleaning — Services Page Guide

Builds the **/services** page on Squarespace 7.1, matching your source design
(`Final Touch Cleaning - Services.html`, decoded from the Claude Design export).
Uses the same kit as the homepage (`final-touch.css`, the `ft-` classes, section
markers, CTAs) plus the Services-page components in **§7b** of the CSS and the
specialty icons added to `site-header.html`.

> Prereqs: the Custom CSS and Code Injection from the main
> `IMPLEMENTATION-GUIDE.md` are installed site-wide (the header injection now
> includes the extra specialty icons — re-paste it if you added it before).

## Page structure (top → bottom) — mirrors the source

| # | Section (theme) | Paste this Code Block | Notes |
|---|---|---|---|
| 1 | **Hero** (Dark/navy) | `01-hero.html` | Breadcrumb, eyebrow, headline, intro, 2 CTAs, faint FL-map watermark |
| 2 | **Scope jump bar** (Dark/graphite, thin) | `02-scopebar.html` | Pill sub-nav; jumps to the sections below |
| 3 | **Core intro** (Light/bone) | `03-core-intro.html` | Section heading + `#core` anchor |
| 3a–c | **The three passes** (same bone section) | `03a-core-rough.html`, `03b-core-detail.html`, `03c-core-touchup.html` | **Text only.** Put each block in one half of a Fluid-Engine row and drag your **own Image Block** into the other half. Alternate the image side (R, L, R). Each has a "What's included" checklist + a "Best for / You receive" pill. |
| 4 | **Specialty work** (bone-2) | `04-specialty.html` | 6 cards with the source's dedicated icons (building, window, floor, broom-power, drop, calendar) |
| 5 | **Packages** (Dark/navy) | `05-packages.html` | 3 tiers; middle = brass "Most booked" |
| 6 | **What always comes with it** (Light/bone) | `06-assurances.html` | Shield / clipboard / chat |
| 7 | **How it works** (bone-2) | `07-how-it-works.html` | 4 steps: Walkthrough → Firm quote → Schedule → Sign-off |
| 8 | **CTA callout** (Light/bone) | `08-cta.html` | Brass callout + `#quote` anchor |

Below the page, the site's graphite link footer (`footer.html`) shows as usual.

## Anchors (add a tiny Code Block `<span id="…"></span>` at each section top)
The three-pass intro, specialty, packages, assurances, how-it-works, and CTA
blocks already include their `id` spans. The scope bar links to
`#core #specialty #packages #addons #how` and the CTAs to `#quote`. The CTA's
"Request a walkthrough" points to `/#contact` (the homepage contact form) —
change it to a Services-page form if you add one.

## Images
The three core passes are **text only** so you place your own photos — drag a
native **Image Block** beside each. Best fits from your uploads: rough → the
concrete room with shoring props; detail → the arched-window interior; touch-up
→ a finished, styled interior once you have one. See `IMAGES-GUIDE.md`.

## SEO (Page → Settings → SEO) — from the source file
- **Title:** `Post-Construction Cleaning Services | Final Touch Cleaning`
- **Description:** `Rough clean, detail pass, and documented final touch-up —
  plus multi-family turnovers, window & glass restoration, floor care, and
  pressure washing for Central Florida builders and GCs. Licensed & insured.`
- The source page carries `Service` + `OfferCatalog` schema. Add it to this
  page's **Page Header Code Injection** if you want the rich result (the JSON is
  in the decoded source, or extend the `OfferCatalog` in `site-header.html`).

## Note on fidelity
The source page shows a photo beside each core pass (with an overlapping icon
badge). Per your request, the three core blocks here are **text only** so you
supply images directly in Squarespace — everything else (copy, checklists,
pills, specialty icons, packages, assurances, how-it-works, CTA) matches the
source one-to-one.
