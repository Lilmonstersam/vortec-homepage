# Design Notes - Vortec Global Homepage Redesign

The brief: **keep the branding, fix the structure, and improve product-category navigation** for hydroseeders, hydro-mulchers and erosion control. Layout mirrors the DTE Equipment homepage redesign mock-up.

## Branding fidelity

Sampled from the live site so the mock-up reads as "Vortec", not a generic template.

| Token | Value | Source |
|---|---|---|
| Primary orange | `#F26522` | Sampled from the live Vortec Orange logo |
| Ink / near-black | `#15191C` | Logo + nav charcoal |
| Theme background | `#F4F6F7` | Light section background |
| Display type | Oswald (condensed, uppercase) | Matches the live heavy condensed headings |
| Body type | Inter | Clean neutral body face |
| Logo | Live `VORTEC-ORANGE_new.png` | Hotlinked from WordPress |

British English spelling used throughout (minimise, optimise, colour). Em dashes avoided in copy.

## Navigation & product-category improvements (the core brief)

**Products mega-menu: grouped, not a deep nested list.** The live site buries products in a single multi-level dropdown. This mock-up replaces it with a 5-column mega-menu grouped by category, with **Hydroseeders & Hydro-Mulchers placed first** and each group heading linking to its category page:

- Hydroseeders & Hydro-Mulchers (VR600, VR1200, VR2000, VX2000 + trailer)
- Polymer Sprayers (P1000–P10000)
- Flocculant Sprayers + Landfill Cover (LR2000 / LX2000)
- Ground Preparation (Rippa-Rake S200 / X140 / X230)
- Agriculture (VX2000 Agri Hydroviner)

**New Applications mega-menu, led by Erosion Control.** A second parent tab lets buyers navigate by use-case: Erosion Control, Revegetation, Mine Site Rehab, Dust Suppression, Landfill Daily Cover, Commercial Landscapes, Agriculture and Sediment Control, drawn directly from the live site's own application filter facets.

**About and Media dropdowns match the live site.** About now exposes Mission, Innovation, Support and FAQ. Media now exposes Articles, Videos and Downloads. The contractor finder has been removed from Products and remains only as its own top-level nav item.

**Pathway Finder.** A 3-way tabbed finder mirrors how buyers actually shop and the live filter system:
- **By Application** (Erosion Control first)
- **By Product Range** (Hydroseeders, Hydro-Mulchers, Polymer, Flocculant)
- **By Capacity** (400–600 L, 1000–1500 L, 1500–2500 L, the live capacity facets)

**All internal links resolve to real, live URLs** on vortecglobal.com (product, category, blog, about, contact, downloads, contractor finder).

## Section-by-section

1. **Promo + utility bar**: keeps the live "Free Delivery" promo and adds a slim contact/social utility bar.
2. **Hero, pathway-led.** States the categories plainly (hydroseeders, hydro-mulchers, polymer, erosion control) and pushes to "Find Your Machine" + phone. Slow 20s Ken-Burns zoom; respects `prefers-reduced-motion`.
3. **Pathway Finder**: the core navigation fix (see above).
4. **Product-category hubs**: six category cards with the headline categories first.
5. **Applications**: six use-case cards led by Erosion Control and Revegetation.
6. **The Vortec Advantage**: the live Safety / Durability / Productivity / Support pillars as scannable cards, with text badges instead of emoji icons.
7. **About + stats**: condensed Vortec story with SEO/CRO strategy proof points: up to 75% savings versus contracting, 50+ years' combined experience and VX2000 productivity around 1500 m²/hour.
8. **Testimonials**: credibility cards (placeholder contractor quotes, swap for real reviews before launch).
9. **Lead band, phone-first**: leads with the phone number, backed by a short segment-aware quote/callback form (vs. the live 16-field form).
10. **Resources**: live cost, in-house equipment and case-study articles reframed as buyer resources.
11. **Footer**: products / applications / company, real URLs.

## Technical / on-page fixes baked in

- `lang="en-AU"` and `og:locale = en_AU` (fixes the live sitewide en_US locale).
- Single `<h1>`, clean heading hierarchy.
- Commercial, keyword-aligned title tag and meta description (hydroseeders, hydro-mulchers, erosion control).
- Descriptive `alt` text on images.
- Lightweight: one HTML file, two web fonts, no page-builder bloat.
- **Nation selector removed** per brief.

## Deliberately out of scope for this mock-up

- Functional forms / live search filtering (review prototype only).
- Product / Organisation schema markup (separate deliverable).
- Final production photography: hotlinked live media should be self-hosted, compressed and served as WebP before launch.
- Placeholder testimonials: replace with verified customer reviews.
