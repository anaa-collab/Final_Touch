# Final Touch Cleaning — Contact / Request-an-Estimate Page Guide

Builds the **/contact** (Request an Estimate) page on Squarespace 7.1, matching
your source design. Uses the shared kit plus the Contact components in **§7d** of
the CSS. Icons are inlined in the blocks (no sprite dependency).

This is the page that actually captures leads, so the estimate form is a **native
Squarespace Form Block** (real submissions, storage, notifications) — styled by
the CSS to look like the bone card in the design.

## Page structure (top → bottom)

| # | Section (theme) | Left / content | Right / content |
|---|---|---|---|
| 1 | **Hero + estimate form** (Dark/navy) | `contact-page/01-hero-copy.html` (headline, reassurance checklist, Call/Text/Email cards) | A native **Form Block** — the estimate form (setup below). Styled as the bone card via the `.ft-contact-form` marker already in the left block. |
| 2 | **What happens next** (Light/bone) | `contact-page/02-what-next.html` — 3-step timeline | — |
| 3 | **Service area + hours** (Dark/navy) | `contact-page/03-area-hours.html` — cities + hours table | — |
| 4 | **Social proof** (bone-2) | `contact-page/04-proof.html` — 4.9 rating + quote | — |
| 5 | **FAQ** (Light/bone) | `contact-page/05-faq.html` — accordion | — |

Below the page, the graphite link footer (`footer.html`) shows as usual.

## The estimate form (native Form Block)
In section 1, drop a **Form Block** to the right of the copy block (same Fluid-
Engine section — the `.ft-contact-form` marker in the left block makes the CSS
style it as the light/bone card automatically).

**Fields, in order** (mark Name + Phone required):
- **Name** * (text)
- **Phone** * (tel)
- **Company** (text) — "Builder / GC / PM"
- **Email** (email)
- **Project type** (dropdown): Custom home — final clean · Multi-family turnover ·
  Rough clean (mid-build) · Remodel / final detail · Commercial build-out · Not sure yet
- **Size — sq ft / units** (text) — "e.g. 6,400 or 88 units"
- **Project location** (text) — "Winter Park, FL"
- **When do you need it?** (radio or dropdown): This week (rush) · 2–4 weeks
  (planned) · Just pricing (flexible)
- **Anything else** (textarea) — "Punch-list status, closing date, access notes…"

**Submit button:** `Get my free estimate`
**Storage:** connect Email + Google Sheets, add a phone/email notification.
**After submit:** redirect to `/thank-you` (reuse `code-blocks/thank-you.html`),
or an inline message: "Request received. We'll call or text within one business
day to set up your walkthrough. Need it sooner? Call (407) 984-8024."

> The design's extra flourishes (the "48h" badge, the segmented urgency chips,
> the fineprint row) aren't native Form Block features. The urgency chips become
> the "When do you need it?" radio/dropdown; the reassurance already lives in the
> left column's checklist. If you want the exact chip UI, it needs a custom coded
> form wired to a form endpoint (Formspree, etc.) — tell me and I'll build that
> variant, but the native Form Block is the reliable lead-capture path.

## Anchors & nav
Add **Contact** (or "Request an estimate") to the header nav → `/contact`. The
`#estimate` scroll target isn't needed since the form is at the top; point homepage
CTAs that go to `/#contact` at this page instead if you make this the primary form.

## SEO (Page → Settings → SEO) — from the source
- **Title:** `Request a Free Estimate | Final Touch Cleaning — Central Florida`
- **Description:** `Free, no-obligation post-construction cleaning estimate for
  Central Florida builders and GCs. We walk the site this week and send a firm,
  itemized quote within 48 hours. Call (407) 984-8024.`
- Keep the `LocalBusiness` schema (site-header) accurate; this page reinforces
  hours + service area, which helps local SEO.

## Note on fidelity
Everything matches the source — hero copy, reassurance checklist, direct-contact
cards, the three-step timeline, service area + hours, the rating strip, and the
FAQ. The one intentional swap is the form: a native Form Block (for real lead
capture) styled to match, instead of the design's demo-only coded form.
