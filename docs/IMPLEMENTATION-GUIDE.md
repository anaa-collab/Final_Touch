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
  (fonts, `theme-color`, the reusable SVG icon sprite, and `LocalBusiness` schema).
  → If you keep the `<link>` fonts here, **delete the `@import` line** at the top
  of the Custom CSS (don't load fonts twice).
  → **If you ever change the icon set, RE-PASTE this whole block.** The SVG
  sprite defines every `#ic-…` symbol the pages draw with `<use>`; a code block
  can only show an icon whose symbol is present here. (The Services page added 8
  specialty icons — building, window, floor, drop, broom-power, shield, calendar,
  chat — so re-paste if your icons render blank.)

> **Icons rendering blank?** The symbol isn't on the page. 99% of the time the
> header injection is an older copy — re-paste `site-header.html` and hard-refresh
> (Cmd/Ctrl+Shift+R). To confirm: view page source and search for `ic-building`;
> if it's missing, the injection is stale. Fallback if your template strips SVG
> from `<head>`: move just the `<svg …><defs>…</defs></svg>` sprite out of the
> header block and paste it into the **Footer** injection instead (it renders in
> `<body>`, which is bulletproof).
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
| 1 | **Hero** (Dark/navy) | `code-blocks/hero.html` | Set the **section Background → Image** to the night-skyline photo (the CSS overlays a navy gradient). Copy + buttons sit on top — no image box beside the text. See `IMAGES-GUIDE.md`. |
| 2 | **Trust strip** (Dark/graphite, thin) | `code-blocks/trust-strip.html` | Optional: small Image Blocks of real client logos |
| 3 | **Services** (Light/bone) | `code-blocks/services.html` | Optional Image Blocks above each card |
| 4 | **Who we serve** (bone-2) | `code-blocks/who-we-serve.html` | — |
| 5 | **Why us** (Dark/navy) | `code-blocks/why-us-stats.html` | — |
| 6 | **Process** (Dark/navy) | `code-blocks/process.html` | — |
| 6b | **Get a quote** (Dark/navy) — *mid-page form #1* | Left: a short Text Block headline (Copy Bank §10) | Right: native **Form Block** (navy card styling needs a Dark section). Add `<span id="quote"></span>` at the top. This is the form all the section CTAs point to. |
| 7 | **Recent work** (Light/bone) | — | **Gallery Section** (native) — set to a grid; upload before/after project photos (see `IMAGES-GUIDE.md`) |
| 8 | **Testimonial** (Dark/navy) | `code-blocks/testimonial.html` | Replace with a real quote ASAP |
| 9 | **FAQ** (Light/bone) | `code-blocks/faq.html` *or* native **Accordion block** | — |
| 10 | **Footer contact band** (Dark/navy) | Left: `code-blocks/footer-cta.html` | Right: a native **Form Block** — auto-styles into the navy quote card. Add `<span id="contact"></span>` at the top (keep `#quote` for the mid-page form — see "Running BOTH forms"). |
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

### Running BOTH forms (mid-page + footer band)
Keeping two quote forms is fine — just don't let them fight:
1. **Unique anchors.** An `id` can only exist once per page, or the browser
   jumps to the first match only. Use:
   - mid-page **Get a quote** section → `<span id="quote"></span>`
   - **footer contact band** → `<span id="contact"></span>`
2. **Point CTAs at one target.** All the section CTAs currently link to
   `#quote` (the mid-page form) — leave them, so buttons scroll to the nearer
   form and the footer band catches everyone who reaches the bottom. (Prefer
   sending them to the bottom band instead? Find-and-replace `#quote` → `#contact`
   in the Code Blocks.)
3. **Keep leads attributable.** Give each Form Block a different **storage label
   / form name** (e.g. "Homepage – mid" vs "Homepage – footer") and the same
   notifications, so you can see which one converts and no lead is missed.
4. **Same fields, same success message** on both, so the experience is
   consistent wherever someone submits.

---

## 3 · The footer contact band + quote form (conversion centerpiece)

This is the bottom-of-page **navy band: copy on the left, form on the right**,
sitting just above the graphite link footer.

- **Left half:** paste `code-blocks/footer-cta.html` (headline, copy, direct
  call/text/email, trust line — all editable).
- **Right half:** add a native **Form Block**. Because the section theme is Dark
  (or it carries the `.ft-footer-cta` marker), the Custom CSS turns the form into
  the navy quote card automatically — navy inputs, brass focus ring, full-width
  brass submit button. No form styling work on your end.
- In Fluid Engine, just drop the two blocks side by side; Squarespace handles the
  two columns and stacks them on mobile.

**Form Block fields, in order:**
   **Name** · **Company** · **Phone** (required) · **Email** ·
   **Project type** (dropdown: Custom home – final clean / Multi-family turnover /
   Rough clean (mid-build) / Remodel – final detail) · **Approx. sq ft** ·
   **Notes**.
2. **Two columns + micro text — automatic.** The Custom CSS grids the field list
   (Name | Company, Phone | Email, Project type | Sq ft; Notes spans full width)
   and injects the micro-line under the submit button ("We call within one
   business day · We walk the site · Firm quote in 48 hours"). Change that line
   in the CSS `.form-button-wrapper::after` rule. Stacks to one column on mobile.
3. **Storage:** connect to email + Google Sheets (Form Block → Storage). Add a
   notification to your phone/email so no lead sits.
4. **After submit → redirect to a Thank-You page.** Squarespace's inline message
   won't take custom HTML, so set the Form Block → *After submit → Redirect to
   URL → `/thank-you`* and build that page from `code-blocks/thank-you.html`
   (hide it from nav). That page is also the reliable place to fire a Google Ads
   / GA4 conversion tag (Thank-You page → Page Header Code Injection). Prefer no
   extra page? Inline message: "Got it — we're on it. We'll call within one
   business day to schedule your walkthrough. Need it faster? Call or text
   (407) 984-8024."
5. The `.form-wrapper` CSS already makes inputs navy with a brass focus ring and
   a full-width brass submit button — no extra work.

> **Faster alternative:** embed **Calendly** (a "Walkthrough" event type) so
> builders self-book. Add it as an Embed Block in the same section.

---

## 3b · Images
Add real photos natively so they load fast and rank. Full mapping (which photo
goes where), alt text, and the brand treatment are in **`docs/IMAGES-GUIDE.md`**.
The short version: **hero = night-skyline as a section background image**
(gradient is automatic); **Recent Work = native Gallery Section**; drag native
**Image Blocks** into other sections as accents. Skip the mop-bucket shot — it
reads "maid service," which is off-brand.

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
