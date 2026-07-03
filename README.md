# Final Touch Cleaning — Squarespace Build Kit

Everything needed to build the **Final Touch Cleaning** website (Direction 04.2)
on **Squarespace 7.1** while keeping every section editable in the Squarespace
editor. The design system stays intact — Archivo + Spline Sans Mono, the
graphite / navy / bone / brass palette, 60-30-10 discipline — and the content
stays yours to change without touching code.

## Approach in one line
Global **Custom CSS** restyles Squarespace's native blocks (type, buttons,
forms, accordion, nav); a handful of **Code Blocks** carry the few highly-
designed components; **Code Injection** adds fonts, SEO/AEO schema, and light
JS. Nothing here is a rip-out of Squarespace — it's a skin on top of it.

## Start here
👉 **`docs/IMPLEMENTATION-GUIDE.md`** — the step-by-step build (60–90 min).

## What's in the box
```
squarespace/
  custom-css/final-touch.css        The master stylesheet → Design → Custom CSS
  code-injection/
    site-header.html                Fonts, theme-color, SVG symbols, LocalBusiness schema
    site-footer.html                Scroll-reveal + FAQ toggle JS
    homepage-header.html            FAQPage schema (homepage only)
  code-blocks/                      HTML for each section's Code Block
    hero.html  trust-strip.html  services.html  who-we-serve.html
    why-us-stats.html  process.html  testimonial.html  faq.html
    final-cta.html  footer.html  sticky-mobile-cta.html
    buttons.html                    Copy library of every CTA button variant
assets/final-touch-logo.svg         Upload as your Squarespace logo
docs/
  IMPLEMENTATION-GUIDE.md           Build it, section by section
  COPY-BANK.md                      Humanized, conversion-tuned copy + the "why"
  SEO-AEO-CHECKLIST.md              Titles, schema, local SEO, AEO, GBP
```

## Requirements
- **Squarespace 7.1** (7.0 notes are in the guide).
- **Business plan or higher** for Code Blocks + Code Injection. The Custom CSS
  alone (typography, colors, buttons, forms) works on any plan.

## Positioning baked in
Premium enough for a luxury GC, approachable enough for a homeowner — carried by
**restraint and transparency**, not discount language. Copy is plain trade
English; CTAs are verbs; every FAQ doubles as a search query and an AI-answer
surface.

## Before launch
Replace all placeholders with real details: phone, email, license #, service
area, hours, client names, photos, and a real testimonial. Then run the
homepage through Google's Rich Results Test and connect Google Business Profile +
Search Console (all in the SEO checklist).
