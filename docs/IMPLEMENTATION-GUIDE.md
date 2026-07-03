# Final Touch Cleaning — Squarespace Implementation Guide

A step-by-step build for a **Squarespace 7.1** site that looks like Direction 04.2
while keeping everything editable in the Squarespace editor. Plan for **60–90
minutes** the first time.

> **Plan requirement:** Code Blocks and Code Injection require the **Business
> plan or higher**. The Custom CSS (typography, colors, buttons, forms,
> accordion) works on *any* plan — so even on Personal you get ~70% of the look.

---

## 0 · Before you start

| You'll need | Where |
|---|---|
| The four brand hexes | Graphite `#141517` · Navy `#16232F` · Bone `#E9E4D8` · Brass `#A8834A` |
| Your logo SVG | `assets/final-touch-logo.svg` (upload the bone version for a navy header) |
| Real photos | Completed interiors, golden-hour, keys-on-counter, crew on site |
| Real details | Phone, email, license #, service area, hours |

Decide your form tool first: **native Squarespace Form Block** (simplest, styled
for you) or an embed (Calendly / Typeform). This guide uses the native Form Block.

---

## 1 · Global setup (do these once)

### 1a. Fonts + colors in Site Styles
1. **Design → Fonts → Assign styles.** Set the **Heading** and **Paragraph**
   families to **Archivo**. (Squarespace includes Archivo in its Google Fonts
   list — no upload needed.) The Custom CSS also forces this, but setting it
   here keeps the editor preview accurate.
2. **Design → Colors.** Open the **theme editor**. You'll map two themes:
   - A **Dark** theme → set background to **Navy `#16232F`**, text to **Bone
     `#E9E4D8`**, button/accent to **Brass `#A8834A`**.
   - A **Light** theme → background **Bone `#E9E4D8`**, text **Graphite
     `#141517`**, accent **Brass**.
   Naming these now means every section you tag "Dark" or that light theme
   auto-matches the brand.

### 1b. Paste the Custom CSS
**Design → Custom CSS →** paste the entire contents of
`squarespace/custom-css/final-touch.css`. Save.

### 1c. Code Injection
- **Settings → Advanced → Code Injection → HEADER:** paste
  `squarespace/code-injection/site-header.html`
  (fonts, `theme-color`, the reusable SVG symbols, and `LocalBusiness` schema).
  → If you keep the `<link>` fonts here, **delete the `@import` line** at the top
  of the Custom CSS (don't load fonts twice).
- **Settings → Advanced → Code Injection → FOOTER:** paste
  `squarespace/code-injection/site-footer.html` (scroll-reveal + FAQ toggle JS),
  then paste `squarespace/code-blocks/sticky-mobile-cta.html` right below it so
  the Call/Text/Quote bar shows site-wide on phones.

### 1d. Logo + header
1. **Design → Logo & Title:** upload `assets/final-touch-logo.svg` (bone version).
2. **Edit header → add a button** labeled **"Request a walkthrough"** (style:
   Primary → renders brass). Add your phone as a secondary nav link
   `tel:+14079848024` — the CSS turns it brass and mono.

---

## 2 · Build the homepage, section by section

Add each section with **+ Add Section → Blank**, set its **color theme** in the
section toolbar, then drop in the Code Block and/or native blocks. Each Code
Block already carries a hidden **band marker** (e.g. `.ft-band-navy`) so the CSS
paints the section even if you skip the theme step — but setting the theme keeps
the editor preview honest.

> **How to add a Code Block:** inside a section, **+ → Code** → paste the file's
> contents → **Apply**. Leave "Display Source" **off**.

| # | Section (theme) | Paste this Code Block | Add these native blocks |
|---|---|---|---|
| 1 | **Hero** (Dark/navy) | `code-blocks/hero.html` | Buttons are **already in the block** (Request a walkthrough / See our process) — just edit labels + links. Optionally swap the visual placeholder for an **Image Block**. |
| 2 | **Trust strip** (Dark/graphite, thin) | `code-blocks/trust-strip.html` | Optional: small Image Blocks of real client logos |
| 3 | **Services** (Light/bone) | `code-blocks/services.html` | Optional Image Blocks above each card |
| 4 | **Who we serve** (bone-2) | `code-blocks/who-we-serve.html` | — |
| 5 | **Why us** (Dark/navy) | `code-blocks/why-us-stats.html` | — |
| 6 | **Process** (Dark/navy) | `code-blocks/process.html` | — |
| 7 | **Recent work** (Light/bone) | — | **Gallery Section** (native) — set to a grid; upload before/after project photos |
| 8 | **Testimonial** (Dark/navy) | `code-blocks/testimonial.html` | Replace with a real quote ASAP |
| 9 | **FAQ** (Light/bone) | `code-blocks/faq.html` *or* native **Accordion block** | — |
| 10 | **Get a quote** (Dark/navy) | Left: a Text Block headline (see Copy Bank). Right: **Form Block** | The CSS styles the Form Block into the navy quote card |
| 11 | **Final CTA** (Light/bone) | `code-blocks/final-cta.html` | — |

**Footer:** Edit Footer → add a Code Block → paste `code-blocks/footer.html`
(or rebuild with native blocks; the `.ft-footer` CSS styles either).

> **CTAs are built into every content block.** Hero, Services, Who-we-serve,
> Why-us, Process, Testimonial, FAQ, and the Final CTA each ship with their own
> section-appropriate button(s) — edit the label and `href` in the block. Two
> deliberate exceptions: the **Trust strip** stays CTA-free (it's a credibility
> bar right under the hero's buttons — a second button there competes and reads
> pushy), and the **Recent-work Gallery** is native, so drop a pair from
> `code-blocks/buttons.html` beneath it if you want a CTA there. The **Get-a-
> quote** section's CTA is the form's own submit button.

### Buttons & CTAs
You have two ways to place calls-to-action — mix them freely:
1. **Baked into the Code Blocks** (already done for the Hero and Final CTA).
   They're live, styled `.ft-btn` links — edit the label between the tags and
   the `href`. `code-blocks/buttons.html` is a copy library of every variant
   (primary / ghost / navy / large / pairs) you can drop into any section.
2. **Native Button Blocks** — `+ → Button`, set **Style: Primary** (brass) or
   **Secondary** (ghost); the Custom CSS (§2) styles them to match. Best when a
   non-technical editor will maintain the page. Place them above/below a Code
   Block, not inside it.

**Rule of thumb:** one **brass primary** button per screen (that's the 10% in
60-30-10); everything else is ghost or navy. Labels are verbs — "Request a
walkthrough," "Get a same-week quote," "Call (407) 984-8024" — never "Submit."

### Section anchors (for the buttons + nav to jump)
Give sections an anchor so `#services`, `#process`, `#quote`, `#faq` work:
in the section settings there's no native "anchor" field in 7.1, so add a tiny
Code Block at the top of each target section, e.g. `<span id="quote"></span>`.
Then your buttons/links to `#quote` scroll there.

---

## 3 · The quote form (conversion centerpiece)

1. In section 10, add a **Form Block**. Fields, in order:
   **Name** · **Company** · **Phone** (required) · **Email** ·
   **Project type** (dropdown: Custom home – final clean / Multi-family turnover /
   Rough clean (mid-build) / Remodel – final detail) · **Approx. sq ft** ·
   **Notes**.
2. **Storage:** connect to email + Google Sheets (Form Block → Storage). Add a
   notification to your phone/email so no lead sits.
3. **Post-submit message:** "Got it — we're on it. We'll call within one
   business day to schedule your walkthrough. Need it faster? Call or text
   (407) 984-8024."
4. The `.form-wrapper` CSS already makes inputs navy with a brass focus ring and
   a full-width brass submit button — no extra work.

> **Faster alternative:** embed **Calendly** (a "Walkthrough" event type) so
> builders self-book. Add it as an Embed Block in the same section.

---

## 4 · Mobile + accessibility pass

- Preview on mobile (editor's device toggle). Confirm the **sticky Call/Text/
  Quote bar** appears and the body has bottom clearance (CSS handles it).
- Tap targets ≥ 44px, body text ≥ 16px — already enforced.
- Check color contrast stays on the approved pairs (bone-on-navy, graphite-on-
  bone). Never put brass text on bone (fails contrast — brand rule 07).
- Buttons are **verbs** ("Request a walkthrough"), never "Submit/Learn more."

---

## 5 · Launch checklist

- [ ] Real phone, email, license #, hours, service area everywhere
- [ ] Real photos replace every placeholder
- [ ] `LocalBusiness` schema: update address, `sameAs` links, hours
- [ ] `FAQPage` schema answers match the on-page FAQ word-for-word
- [ ] Test the form end-to-end (submit → you get the lead)
- [ ] Run the page through Google's **Rich Results Test** (see SEO checklist)
- [ ] Set SEO title/description per page (see `SEO-AEO-CHECKLIST.md`)
- [ ] Connect Google Business Profile + Google Search Console

---

## 7.0 vs 7.1 notes

This guide targets **7.1**. On **7.0** (Brine family): sections are "index
sections," button classes differ slightly (`.sqs-block-button-element--*` still
apply), and `:has()` section theming is less reliable — instead give each index
section a **URL slug/ID** and target `#sectionID` in CSS. The Custom CSS
typography/button/form rules still work. If you're unsure which version you're
on: 7.1 sites let you add sections with color themes per section — 7.0 does not.

---

## File map

```
squarespace/
  custom-css/final-touch.css          → Design → Custom CSS
  code-injection/
    site-header.html                  → Settings → Advanced → Code Injection → Header
    site-footer.html                  → Settings → Advanced → Code Injection → Footer
    homepage-header.html              → Home page → Settings → Advanced → Page Header
  code-blocks/*.html                  → paste into Code Blocks per the table above
assets/final-touch-logo.svg           → Design → Logo & Title
docs/
  COPY-BANK.md                        → humanized copy for every section
  SEO-AEO-CHECKLIST.md                → titles, schema, local SEO, AEO
```
