# Homepage Redesign — Implementation To-Do

What is left to build/fix on vortecglobal.com before the new homepage mock-up can go live. Compiled by cross-checking every link in the mock-up against the live sitemaps (page, post and product) and the live homepage, July 2026.

**Link audit result:** all 17 product URLs, all 4 category URLs and all 3 featured blog articles in the mock-up resolve to real pages. The gaps below are missing hub/landing pages, functional build work and content decisions.

## 1. Missing landing pages (blockers for the new navigation)

1. **Applications hub page.** "Browse equipment by application →" currently points at `/hydroseeder-hydromulchers/` because no applications page exists. Build `/applications/` as a hub.
2. **Individual application landing pages (x8).** Every application link in the mega-menu, Pathway Finder and Shop by Application section falls back to a product category page. Needed: Erosion Control, Revegetation, Mine Site Rehab, Dust Suppression, Landfill Daily Cover, Commercial Landscapes, Agriculture and Sediment Control. These are also the biggest SEO win in the redesign (application-intent keywords currently have no dedicated URLs). Mine Site Rehab and Commercial Landscapes have no live page of any kind.
3. **All-products page.** "View all products →" points at the hydroseeders category. A live `/products/` page exists but was last touched Jan 2024 and uses placeholder product images; either rebuild it to the new category-hub pattern or retire it and pick a canonical destination. `/shop/` (WooCommerce archive) also exists — decide which one survives and 301 the other.
4. **Ground Preparation Tools category page.** No category URL exists — the live nav uses a dead `#` link and the mock-up borrows the hydroseeders URL. Build `/ground-preparation-tools/` housing the Rippa-Rake S200 / X140 / X230.
5. **Agriculture category page.** Same problem — live nav uses `#`, mock-up links the group heading to the single VX2000 Agri Hydroviner product. Either build `/agriculture-hydroseeders/` or agree the group head links straight to the product.
6. **Capacity-filtered views.** The "By Capacity" finder tabs link to individual products (VR600, VR1200, VR2000). If capacity is meant to be a real browse path, build filtered category views (WooCommerce attribute filters with crawlable URLs) or keep the product-link shortcut and note it.

## 2. Navigation and content gaps in the mock-up itself

7. ~~Two live products missing from the mega-menu~~ **Done in mock-up:** VR600 Trailer and VR2000 Trailer added to the Hydroseeders group (mega-menu + mobile drawer).
8. **Fi-series product pages still to build.** The mock-up now shows Fi600 / Fi1200 / Fi1500 in the Flocculant group with "Page TBC" markers, linking to the category page until the product pages exist. Building those three pages remains an open task.
9. **About anchors.** `/about-the-vortec-story/` confirmed as the canonical About URL. Remaining: 301 `/about/` (used by the live nav and footer) to it, and verify the `#mission` / `#innovation` / `#support` / `#faq` anchor IDs exist on the page.
10. **Pages on the live site absent from the mock-up nav/footer** — Careers now added to the mock-up footer. Still to decide in or out: Second Hand Hydroseeders (commercial page), the 2.99% finance offer (promo-bar candidate alongside/instead of Free Delivery), newsletter signup (in live footer, dropped in mock-up), footer email address (live has one, mock-up is phone-only).
11. **Nation selector.** Deliberately omitted per brief, but the live site has AU/NZ/EU/UK/US variants. Confirm the removal decision and what happens to the country content.
12. **Phone number.** Mock-up uses 1800 867 832 throughout; the live footer also shows 07 3184 8442. Confirm the primary number for header, sticky bar and lead band.

## 3. Functional build (theme/CMS work)

13. **Mega-menu with grouped columns + product thumbnails** — the live theme runs a standard nested dropdown; the grouped layout needs theme or nav-plugin development, including keyboard/touch accessibility.
14. **Short segmented quote form.** The mock-up form is static (submit button links to `/contact/`). Build the 4-field callback/quote form (name, phone, email, application), wire to the existing form handler/CRM, route to `/thank-you-quote/` (exists), and tag conversion events in GTM (two containers live: GTM-PMZKB279, GTM-TJNM3BM4) plus the Facebook and LinkedIn pixels.
15. **Pathway Finder tabs** — JS is in the mock-up but needs porting into the theme, with the panels crawlable (all links are plain anchors, keep it that way).
16. **Mobile sticky CTA bar** (Find Your Machine + call) — new component, needs building with the same z-index care around the mobile drawer.
17. **Mobile drawer nav** — replaces the current hamburger menu; port from mock-up.
18. **Promo bar as text.** Live uses a Free Delivery PNG banner (1200×75 / 768×100); rebuild as the text bar so it is accessible, translatable and doesn't ship two images.

## 4. Content and assets

19. **Real testimonials.** The three review cards are placeholders — collect verified customer quotes with names/companies and permission.
20. **Verify claims:** "up to 75% cheaper than contracting", "50+ years combined experience", "1500 m²/h" — client sign-off before launch (also used in hero trust row and About stats).
21. **Photography.** Several cards reuse wrong-product images because nothing better exists in the media library: LR2000/LX2000 use VR2000/VX2000 trailer renders, the Fulton Hogan case-study card uses a P10000 photo, Agriculture reuses the revegetation shot, and Mine Site Rehab / Commercial Landscapes have no imagery at all. Commission or source photos per category/application.
22. **Self-host and optimise images.** Mock-up hotlinks the WP media library; production needs compressed WebP with proper srcset, and the hero/lead/about images re-cropped for their new containers.

## 5. SEO/technical carry-over (CMS-side)

23. Locale fix: sitewide `og:locale` is `en_US` and there's no `lang="en-AU"`; correct in theme + Rank Math.
24. New title tag and meta description (mock-up versions are keyword-aligned; live homepage title is "Vortec Global | Erosion Control Solutions").
25. Heading hierarchy: live homepage has multiple H2s acting as H1s and an H1 buried in the contractor modal; enforce the single-H1 structure from the mock-up.
26. **Duplicate/legacy URL cleanup** (pre-launch hygiene so the new nav doesn't compound it): `/hydroseeders/`, `/hydromulchers/` and `/hydroseeder-hydromulchers/` all live simultaneously; plus `/hydroseeders-duplicate/`, `/downloads-duplicate/`, `/hydromulching-contractors-2/`, `/test/`, `/test-inner-page/`, `/advantages-test/`, `/404-2/` are indexed in the sitemap. Consolidate with 301s and prune the sitemap.
27. Organisation/Product/Breadcrumb schema (already scoped as a separate deliverable).
28. WCAG contrast decisions from round 2 (AA orange `#C94F12` vs brand `#F26522` on buttons) need a final client call before the dev build bakes in tokens.

## Suggested build order

Phase 1 (unblocks nav): items 1–5, 9, 26.
Phase 2 (homepage build): items 13–18, 7–8, 22.
Phase 3 (content): items 19–21, plus decisions 10–12.
Phase 4 (polish/launch): items 6, 23–25, 27–28.
