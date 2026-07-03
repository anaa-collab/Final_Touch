# Final Touch Cleaning — Work / Portfolio Page Guide

Builds the **/work** page on Squarespace 7.1, matching your source design
(`Final Touch Cleaning - Work.html`, decoded from the Claude Design export).
Uses the shared kit plus the Work components in **§7c** of the CSS, the `ic-star`
icon added to `site-header.html`, and the before/after slider JS in
`site-footer.html`.

> Prereqs: re-paste the updated **Header injection** (`site-header.html` — now
> includes `ic-star`) and **Footer injection** (`site-footer.html` — now includes
> the slider script). Then hard-refresh.

## Page structure (top → bottom) — mirrors the source

| # | Section (theme) | Paste this Code Block | Notes |
|---|---|---|---|
| 1 | **Hero + stat ribbon** (Dark/navy) | `work-page/01-hero.html` | Text + 4-stat ribbon, no image |
| 2 | **Before & after** (Light/bone) | `work-page/02-before-after.html` | Two drag-to-reveal sliders + project meta. **Add your images** (see below). |
| 3 | **Project grid** (bone-2) | `work-page/03-project-grid.html` | 6 cards; add a photo URL per card, or use a native Gallery |
| 4 | **Testimonials** (Dark/navy) | `work-page/04-testimonials.html` | Star icons kept; optional avatar photos |
| 5 | **Sign-off artifact** (Dark/navy) | `work-page/05-signoff.html` | Text + the report card (a brand artifact, not a photo — kept as-is) |
| 6 | **Logo strip + CTA** (bone / bone-2) | `work-page/06-logos-cta.html` | Split into two sections if you prefer |

Below the page, the graphite link footer (`footer.html`) shows as usual.

## Adding your images (this is the "make space for images" part)
All the big placeholder graphics are now **real `<img>` slots** — the text and
icons are untouched. Fill each slot with your own photo:

**Getting a Squarespace image URL:** upload the photo to any Image Block (or
Squarespace's image manager), view the live image, right-click → **Copy image
address**, and paste that into the matching `src=""`.

- **Before & after (section 2):** each slider has two images — the **first `<img>`
  is the AFTER** (move-in ready), the **second is the BEFORE** (post-construction).
  The handle wipes between them. *No-code alternative:* delete a slider and drop a
  native before/after plugin or two Image Blocks, keeping the meta text.
- **Project grid (section 3):** replace each card's `<img src="">` with the project
  photo. The type pill (Custom home / Multi-family…) and stats stay. *No-code
  alternative:* use a native **Gallery Section** with the names + cities as captions.
- **Testimonials (section 4):** optional headshot per card; leave `src=""` empty to
  show the plain navy circle.

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
