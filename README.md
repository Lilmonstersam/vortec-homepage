# Vortec Global - Homepage Redesign Mock-up

Static HTML mock-up of a rebuilt Vortec Global homepage, prepared by **Digilari** for client review (June 2026).

**Live reference site:** https://vortecglobal.com/
**Deploy target:** https://github.com/Lilmonstersam/vortec-homepage

## What this is

A single-file HTML mock-up that keeps Vortec's existing branding (orange/black palette, logo, condensed Oswald-style display type) but restructures the homepage around **buyer pathways** and dramatically improves **product-category navigation** for the headline categories: **hydroseeders, hydro-mulchers and erosion control**.

This is a review prototype, not production code. The quote form is non-functional, and product images are hotlinked from the live WordPress media library so the client sees a realistic page immediately. The nation selector on the live site has been deliberately omitted per brief.

## Quick start

Open `index.html` in any browser. No build step, no dependencies (fonts load from Google Fonts CDN).

## Repo structure

```
homepage-redesign/
├── index.html                 # the mock-up (self-contained: HTML + CSS + JS)
├── README.md                  # this file
├── design-notes.md            # section-by-section rationale
├── .nojekyll                  # tells GitHub Pages to skip Jekyll processing
├── .gitignore
└── .github/workflows/
    └── deploy.yml             # GitHub Actions → GitHub Pages deployment
```

## Key changes vs. the current homepage

| Current homepage | This mock-up |
|---|---|
| Single "Products" dropdown, deep nested list | **Grouped Products mega-menu** (Hydroseeders & Hydro-Mulchers / Polymer / Flocculant / Landfill / Ground Prep / Agriculture) + a new **Applications mega-menu** led by Erosion Control. The contractor finder is kept as its own top-level tab, matching the live site. |
| Plain About / Media links | **About and Media dropdowns** matching the live site: Mission / Innovation / Support / FAQ, plus Articles / Videos / Downloads |
| No use-case navigation | Prominent 3-way **Pathway Finder** (By Application · By Product Range · By Capacity) mirroring the live filter facets |
| Products surfaced as flat tiles | **Product-category hubs** with the headline categories first: Hydroseeders, Hydro-Mulchers, Polymer, Flocculant, Landfill, Ground Prep |
| Brand-slogan hero | **Pathway hero** (slow zoom bg, left-aligned) + "Find Your Machine", phone CTA and ROI proof from the SEO/CRO strategy |
| One long 16-field quote form as only CTA | **Phone-first CTA** + short, segment-aware 4-field quote/callback form |
| Nation selector (AU/NZ/EU/UK/US) | **Omitted per brief** |
| `og:locale = en_US` | `en_AU` + AU intent signals |

All nav, finder, card and footer links point to **real, live URLs** on vortecglobal.com.

## Deploying to GitHub Pages

The repo is configured for automatic deployment via GitHub Actions (`.github/workflows/deploy.yml`).

```bash
cd seo/mockups/homepage-redesign
git init
git add .
git commit -m "Vortec homepage redesign mock-up v1"
git branch -M main
git remote add origin https://github.com/Lilmonstersam/vortec-homepage.git
git push -u origin main
```

Then in the GitHub repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**. The workflow runs on every push to `main` and publishes the site. The deployed URL appears in the Actions run and under Settings → Pages.

> Note: the workflow uploads the whole folder as the Pages artifact, so `index.html` is served at the site root. `.nojekyll` is included so GitHub Pages serves files as-is without Jekyll processing.

## Status

- [x] v1 mock-up matching brand + improved product-category navigation
- [x] GitHub Actions Pages deployment ready
- [ ] Client review / feedback round
- [ ] Production images swapped (self-host, compress, WebP)
- [ ] Handoff for WordPress build
