# Final Touch Cleaning — Services Page Guide

Builds the **/services** page on Squarespace 7.1 using the same kit as the
homepage (`final-touch.css`, the `ft-` classes, section markers, and CTAs).
Reconstructed from the brand system — if you paste your exact
`Final Touch Cleaning - Services.html`, I'll reconcile the copy; the structure
and styling below already match the system.

> Prereqs: the Custom CSS and Code Injection from the main
> `IMPLEMENTATION-GUIDE.md` are already installed site-wide. That's all this page
> needs — no new CSS to paste.

## Page structure (top → bottom)

| # | Section (theme) | Paste this Code Block | Notes |
|---|---|---|---|
| 1 | **Hero** (Dark/navy) | `services-page/01-hero.html` | Optional background photo (interior/detail). CTAs built in. |
| 2 | **The three passes** (Light/bone) | `services-page/02-service-rows.html` | Alternating text/photo rows. Drag a native Image Block over each `.ft-media` placeholder. |
| 3 | **What's included** (bone-2) | `services-page/03-included-table.html` | Add `<span id="included"></span>` at the top so the hero button jumps here. Table scrolls on mobile. |
| 4 | **Specialty / add-ons** (Light/bone) | `services-page/04-addons.html` | Trim rows to match what you actually offer. |
| 5 | **Process recap** (Dark/navy) | reuse `code-blocks/process.html` | Same 4-step protocol as the homepage — reinforces the method. |
| 6 | **Services FAQ** (Light/bone) | `services-page/05-faq.html` | Accordion uses the toggle JS already in `site-footer.html`. |
| 7 | **Closing CTA** (Dark/navy) | `services-page/06-cta.html` | Add `<span id="quote"></span>` at the top. Or reuse `footer-cta.html` + a Form Block for a full form here. |

Below the page, the site's graphite link footer (`footer.html`) shows as usual.

## CTAs & anchors
- Buttons on this page point to `#quote` (the closing CTA on this page) and
  `#included`. Add the matching `<span id="…"></span>` markers at the tops of
  those sections.
- The closing CTA's primary button links to `/#contact` — the homepage footer
  contact band with the full form. Change it to this page's own form if you add
  one.

## Nav
Add **Services** to the header nav → link to `/services`. If you break services
into their own pages later (`/rough-clean`, `/multi-family-turnover`), make this
a folder — good for SEO (see `SEO-AEO-CHECKLIST.md`).

## SEO (Page → Settings → SEO)
- **Title:** `Post-Construction Cleaning Services for Florida Builders | Final Touch`
- **Description:** `Rough clean, detail pass, and documented final touch-up for
  custom homes and multi-family builds in Central Florida. Licensed & insured,
  firm quote in 48 hours. (407) 984-8024.`
- Give the three service photos descriptive alt text (see `IMAGES-GUIDE.md`).
- Optional: add a `Service`-type schema block for this page, or extend the
  `OfferCatalog` already in `site-header.html`.

## Images
Each of the three passes has a `.ft-media` placeholder — replace with a native
Image Block. Best fits from your uploads: rough → the concrete room with
shoring props; detail → the arched-window interior; touch-up → a finished,
styled interior once you have one. Full guidance in `IMAGES-GUIDE.md`.
