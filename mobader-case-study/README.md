# Mobader × Brandology · Case Study Page

Two language versions of the same long-form web case study, sharing one CSS file.

## Files

```
page/
├── en.html      ← English version (LTR)
├── ar.html      ← Arabic version (RTL native, Saudi-comfortable register)
├── styles.css   ← Shared design system
├── assets/      ← (for real screenshots when captured)
└── README.md
```

## How to view

Open either `en.html` or `ar.html` in any modern browser. They link to each other via the language switcher in the top-right.

For the best preview of mobile responsiveness, open Chrome/Safari DevTools and toggle device emulation. Test specifically at:
- **360 × 640** (small Android, the realistic minimum for KSA)
- **390 × 844** (iPhone 14)
- **768 × 1024** (iPad portrait)
- **1280 × 800** (small desktop)
- **1920 × 1080** (full desktop)

## Design notes

- **Direction 3 (Cinematic) realised in long-form web format.** Dark mode is reserved for high-impact moments (hero, act dividers, charts, lesson, footer); body reading sections are on a light surface to protect readability across 3,000+ words.
- **Brandology palette only.** Red `#E30613`, yellow `#F5C32C`, black `#0A0A0A`, off-white `#FAFAF7`. Mobader purple does not appear (will appear only inside actual Mobader screenshots once captured).
- **Mobile-first CSS.** Built starting from a 360px viewport. All typography uses `clamp()` for fluid scaling.
- **Real-data charts.** Both line charts (SEO traffic + revenue) are inline SVG drawn from the actual GSC monthly trajectory. No chart libraries; no external requests beyond Google Fonts.
- **Screenshot placeholders.** Three frames are clearly marked "Screenshot needed" with the right aspect ratio and a description of what should be captured. Drop real images in `assets/` and replace the placeholder markup when ready.

## Accessibility

- WCAG AA contrast ratios on all text
- Semantic HTML5 landmarks (`<section>`, `<nav>`, `<aside>`, `<footer>`)
- Real heading hierarchy (one `<h1>`, sequential `<h2>`/`<h3>`)
- SVG charts have `<title>` and `role="img"` for screen readers
- `:focus-visible` states with brand-yellow outline
- Respects `prefers-reduced-motion`
- Print stylesheet (so browser-print produces a clean PDF)
- `lang` and `dir` attributes correctly set on `<html>`

## What still needs to happen

1. **Capture real screenshots** for the three placeholder frames:
   - Mobader.sa, August 2024 (via Wayback Machine)
   - Top organic landing pages (GSC export)
   - Google Ads dashboard (Phase 2 spend + conversions)
2. **Verify the revenue chart's intermediate months** against `Mobader Sales Data.csv` (anchor points are confirmed; intermediate months are smoothed for legibility).
3. **Replace the `#` CTA links** in the lesson and footer with real Brandology contact URLs.
4. **Optional:** add OpenGraph image (`og:image`) · a 1200×630 PNG of the hero treatment.
5. **Optional:** add `<link rel="canonical">` and a `hreflang` pair pointing en ↔ ar once hosted at real URLs.

## Technical specs

- No build step. Pure HTML + CSS. Works opened directly from disk.
- One stylesheet, one HTML file per language. Total page weight: under 50KB excluding the Google Fonts request.
- Tested target browsers: Safari 16+, Chrome 110+, Firefox 110+, Edge 110+.
