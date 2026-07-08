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
- **Preferred date** (date) — "When would you like us on site?" *(this is the
  "book online" mechanism — a desired-date field, not a live calendar)*
- **How soon?** (radio or dropdown): This week (rush) · 2–4 weeks (planned) ·
  Just pricing (flexible)
- **Anything else** (textarea) — "Punch-list status, closing date, access notes…"

**Submit button:** `Get my free quote`
**Storage:** connect Email + Google Sheets, add a phone/email notification.
**After submit:** redirect to `/thank-you` (reuse `code-blocks/thank-you.html`),
or an inline message: "Got it — we're on it. We'll send your firm quote shortly.
Approve it and we'll lock in your date. Need it faster? Call or text
(407) 984-8024."

> **The booking model:** request → we send a firm quote → you approve → we
> schedule the date you asked for. It's fully online and phone-tag-free, but it's
> *not* a self-service calendar — the "Preferred date" field is how the customer
> tells you the date; you confirm it when you send/approve the quote. All the
> site copy is written to match this exactly (no "pick your date online" that
> implies a live booking widget).

> **Clean native skin (current approach).** The CSS styles the native Form Block
> cosmetically but does NOT lay out the columns — Squarespace's own Form Block
> does. This avoids the custom CSS fighting the newer Form Block's layout engine.
>
> **You control the field layout in the Form Block editor:**
> - Click each field and set its **width** (Full / ½ / ⅓). For the design's
>   pairing: Name ½, Phone ½ · Company ½, Email ½ · Project type ½, Size ½ ·
>   Project location Full · When-do-you-need-it Full · Anything else Full.
> - Set every field to **Full width** first if you just want a clean single
>   column — it always looks tidy.
> - If you added a **newsletter "Sign up" checkbox**, set it to Full width (or
>   remove it) so its label doesn't get squeezed.
>
> **What the CSS still does for you (cosmetic, no layout):**
> - Skins the card, inputs, focus states, and the brass submit button.
> - Turns the **"When do you need it done?" radio field** into stacked bordered
>   cards (selected = navy) with **Rush / Planned / Flexible** sub-labels. Add
>   the options in this order: `This week` · `2–4 weeks` · `Just pricing`. (Sub-
>   labels follow position; if they land wrong, see the `nth-of-type` note in
>   the CSS.)
> - Injects the **✓ trust row** ("No obligation · No spam · We never sell your
>   info") under the submit button.
>
> **The "Request your estimate" heading + "24h · quote turnaround" badge** are
> NOT drawn by CSS anymore (as pseudo-elements they landed unreliably on the new
> Form Block). Add them as a small **Text Block directly above the Form Block**:
> a bold line "Request your estimate", a muted line "Two required fields — the
> rest just sharpens your quote.", and (optional) a navy "24h" chip.
>
> If you later want a **pixel-exact** version (badge + chips locked in, identical
> in every browser), that's the coded-form route on a free endpoint
> (Formspree/Basin) — say the word and I'll build it.

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
