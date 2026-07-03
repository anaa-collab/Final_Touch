# Final Touch Cleaning — Images Guide

How to add real photos so the site reads premium and loads fast. **Always upload
into Squarespace natively** (Image Blocks, Gallery Sections, Section Background
images) — Squarespace compresses and serves responsive sizes automatically,
which beats any hardcoded `<img>` URL for speed and SEO. Don't paste image URLs
into Code Blocks.

---

## Where each uploaded photo goes

| Photo | Use it as | Section | Why |
|---|---|---|---|
| **Night construction skyline** (crane, lit high-rise, storm sky) | **Hero background** | Hero | Dramatic, premium, "the last trade on a serious build." Best single image you have. |
| **Builder drawing plans** (KRA polo, ruler + pencil) | Accent image | Who we serve **or** a short About block | Humanizes the brand; signals you work alongside GCs/architects. |
| **Concrete room w/ shoring props, dusty floor** | "Before" shot | Recent Work gallery / Services (Rough) | Real rough-stage site — sells the transformation. |
| **Concrete room w/ arched windows + ladder/ductwork** | "Before / mid" shot | Recent Work gallery / Services (Detail) | Shows scope + light; good pairing with an "after." |
| **Yellow mop bucket** | ⚠️ **Skip** | — | Reads "maid service" — the one signal your brand rules tell us to avoid. Off-brand for a trade vendor. |

> The strongest gallery is **before → after pairs**. Your uploads are all
> "before/during" shots — get 3–4 **finished, styled interiors** (golden-hour,
> keys on the counter) and those become the hero-quality "after" images that
> actually close high-end clients.

---

## 1 · Hero background (do this first)

1. Hero section → **Edit Section → Background → Image** → upload the **night
   skyline**. Set focal point on the lit building.
2. Leave Squarespace's built-in **overlay at 0%** — the Custom CSS lays a navy
   gradient (dark on the left where the text is, lighter on the right) so copy
   stays legible. It's already wired to the `.ft-hero-bg` marker in `hero.html`.
3. Mobile: the gradient auto-switches to a top-to-bottom fade so the headline
   never fights the image. Check it in the mobile preview.

*Prefer a flat look instead of the gradient?* Set Squarespace's native overlay
to ~65% navy and ignore the gradient — either works.

---

## 2 · Recent Work gallery (native, no code)

1. Add a **Gallery Section** (not the old gallery block) → choose a **Grid**.
2. Upload the two concrete-interior shots now; add finished "after" photos as
   you get them.
3. Turn on captions and use them for local SEO: `Custom home · Winter Park` /
   `Multi-family turnover · Tampa`.

---

## 3 · Accent images in other sections (Fluid Engine)

In any Fluid-Engine section you can drag a native **Image Block** beside a Code
Block:
- **Who we serve:** drop the **builder-drawing-plans** photo next to the tag
  list for a human, on-site feel.
- **Testimonial:** a real headshot of the person quoted beats the logo mark.
- **Services:** optional — add a small Image Block above each of the three cards
  (rough / detail / finished). Keep them the same crop ratio (16:10) so the row
  stays even.

---

## Brand treatment (keep photos on-system)

Your palette is disciplined, so the photography has to match — otherwise stock
color casts fight the navy/bone/brass.

- **Lean cool + slightly desaturated.** Nudge saturation down ~10–15% and warmth
  toward neutral so images sit next to Site Navy without clashing.
- **Favor dark, moody frames for dark sections; bright, airy frames for bone
  sections.** (Design rule: bone on navy, graphite on bone.)
- **Brass is the only warm accent** — let it come from real light (golden-hour,
  work lights), not from an orange filter.
- **No heavy filters, no drop shadows, no gradients baked into the photo.** Flat
  and honest matches the brand's "we don't cut corners, including the brand."
- **Crops:** hero = wide/cinematic; gallery = consistent ratio; cards = 16:10.

---

## Alt text (paste these — SEO + accessibility)

Squarespace: click an image → **Design/Edit → Alt text**. Describe the image
honestly and let a city/service term appear naturally (don't keyword-stuff, and
don't name a city the photo isn't from).

| Image | Alt text |
|---|---|
| Hero skyline | `High-rise under construction at dusk — Final Touch Cleaning handles the final post-construction clean in Central Florida` |
| Builder w/ plans | `Builder reviewing construction plans before a Central Florida project handover` |
| Concrete room (props) | `Concrete interior at rough construction stage, before post-construction cleaning` |
| Arched-window room | `New building interior awaiting final detail cleaning` |
| Finished interior (when you have it) | `Move-in-ready custom home interior after post-construction cleaning in [city]` |

---

## Performance checklist

- [ ] Export photos at ~2000px on the long edge before upload (Squarespace scales
  down from there; don't upload 6000px originals).
- [ ] Hero image compressed (JPEG ~70–80%) — it's your Largest Contentful Paint.
- [ ] Every image has descriptive alt text + a real filename
  (`post-construction-clean-winter-park.jpg`, not `IMG_2381.jpg`).
- [ ] Don't stack more than a few large images above the fold.
