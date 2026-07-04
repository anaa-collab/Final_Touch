# Final Touch Cleaning — Work / Portfolio Page Guide

Builds the **/work** page on Squarespace 7.1, matching your source design
(`Final Touch Cleaning - Work.html`, decoded from the Claude Design export).
Uses the shared kit plus the Work components in **§7c** of the CSS, the `ic-star`
icon added to `site-header.html`, and the before/after slider JS in
`site-footer.html`.

> Prereqs: re-paste the updated **Footer injection** (`site-footer.html` — now
> includes the before/after slider script), then hard-refresh.
>
> **Icons are now inlined** directly in every code block (no shared sprite to
> keep in sync), so they render regardless of your header injection — this fixes
> the earlier "blank icons" issue for good.

## Page structure (top → bottom) — mirrors the source

| # | Section (theme) | Paste this Code Block | Notes |
|---|---|---|---|
| 1 | **Hero + stat ribbon** (Dark/navy) | `work-page/01-hero.html` | Text + 4-stat ribbon, no image |
| 2 | **Before & after** (Light/bone) | `02-before-after-intro.html`, then `02a-before-after-lakeside.html` + `02b-before-after-bayshore.html` | **Text only.** Put each project's text block in one half of a Fluid-Engine row and add your before/after image(s) in the other half (native Image Block or a before/after comparison plugin). Alternate the image side per row. |
| 3 | **Recent turnovers** (bone-2) | `03-turnovers-intro.html`, then `03-turnovers-cards.html` | **Text only.** 6 cards with type/name/city/stats. Add photos separately — a native **Gallery Section** above/below, or an Image Block above each card. |
| 4 | **Testimonials** (Dark/navy) | `work-page/04-testimonials.html` | Star icons kept; optional avatar photos |
| 5 | **Sign-off artifact** (Dark/navy) | `work-page/05-signoff.html` | Digital-handover copy ("close out from your phone" — photos, e-sign, pay online) + the sign-off record card |
| 6 | **Logo strip + CTA** (bone / bone-2) | `work-page/06-logos-cta.html` | Split into two sections if you prefer |

Below the page, the graphite link footer (`footer.html`) shows as usual.

## Adding your images
The **Before & after** and **Recent turnovers** sections are now **text-only** —
no image elements at all — so you add every photo natively in Squarespace:

- **Before & after (section 2):** each project is a text block. In a Fluid-Engine
  row, put the text in one column and your image(s) in the other — a native Image
  Block, or a before/after comparison plugin for the drag effect. Alternate the
  image side between the two projects.
- **Recent turnovers (section 3):** text-only cards. Add the project photos as a
  native **Gallery Section** placed above or below the cards, or drop an Image
  Block above each card.
- **Testimonials (section 4):** still uses a small optional avatar `<img src="">`
  per card; leave it empty to show the plain navy circle, or paste a headshot URL.

## CTAs & anchors
Buttons point to `#quote` (the CTA at the bottom of this page) and `/#contact`
(the homepage contact form). The CTA block already includes `<span id="quote">`.

## SEO (Page → Settings → SEO) — from the source
- **Title:** `Our Work — Post-Construction Cleaning Portfolio | Final Touch Cleaning`
- **Description:** `Before-and-after post-construction cleaning across Central
  Florida — custom homes and multi-family turnovers handed over move-in ready,
  with documented sign-off. See the work.`
- Give every project photo descriptive alt text with the city (already stubbed in
  the `alt=""` attributes — keep them accurate). Great for image SEO.

## Note on fidelity
Everything matches the source one-to-one — hero + ribbon, the before/after
sliders, project grid, star testimonials, the sign-off report artifact, logo
strip, and CTA — with the only change being that the placeholder graphics are now
image slots you fill with your own photos (text and icons unchanged), per your
request.
