# Migration Report: Jordan Olivenöl — Pipeline → Flora/Horizon Theme

**Date:** 2026-03-10
**Source Theme:** Pipeline 6.4.0 (jordanolivenoel.de live theme)
**Target Theme:** Flora/Horizon (AI-generated Shopify theme)
**Store:** jordanolivenoel.de — Jordan Olivenöl GmbH

---

## Executive Summary

Complete content migration from Pipeline 6.4.0 to Flora/Horizon theme, preserving all product content, images, branding, and German localization. The Flora theme's core architecture (sections/*.liquid, blocks/*.liquid, assets/*, layout/theme.liquid) remains untouched — only JSON configuration, templates, snippets, and locales were modified.

---

## Phase Completion Status

| Phase | Description | Status |
|-------|-------------|--------|
| 1 | Theme Analysis (Pipeline + Flora + Live-Website) | ✅ Complete |
| 2 | Section Mapping & Template-Erstellung | ✅ Complete |
| 3 | Settings & Branding | ✅ Complete |
| 4 | Header & Footer | ✅ Complete |
| 5 | Homepage | ✅ Complete |
| 6 | Product Template | ✅ Complete |
| 7 | SEO-Optimierung | ✅ Complete |
| 8 | Conversion & GEO/AEO | ✅ Complete |
| 9 | Lokalisierung | ✅ Complete |
| 10 | Validierung & Finale ZIP | ✅ Complete |

---

## Files Modified (vs. Flora Original)

### config/settings_data.json
- Logo: `shopify://shop_images/Logo.jpg` (50px desktop, 40px mobile)
- Favicon: `shopify://shop_images/jordan_favicon_final.png`
- 7 color schemes (scheme-1 white/#5c2b59, scheme-2 dark olive #181e07, scheme-3 black footer, scheme-4 announcement #5c2b59, scheme-5 light #eeeeee, scheme-6 transparent/white, scheme-transparent-dark)
- Fonts: Optima Nova n8 (headings), n3 (body), n6 (subheading/accent)
- Text sizes: paragraph 16px, H1 48px, H2 36px, H5 18px, H6 16px
- Social links: Facebook, Instagram, YouTube, Pinterest, TikTok, LinkedIn, Twitter
- Cart type: drawer
- Checkout logo: `shopify://shop_images/Logo.jpg`

### sections/header-group.json
- Announcement bar: "AKTION: NOCH €19,98 EUR UND DU BESTELLST VERSANDKOSTENFREI INNERHALB DEUTSCHLANDS" (scheme-4)
- Logo position: left
- Menu: center, search right, sticky always
- Transparent header on homepage (scheme-6)
- Top row: scheme-2 (dark olive #181e07)
- Country & language selectors enabled

### sections/footer-group.json
- Newsletter: "Newsletter abonnieren" / "Bleib auf dem Laufenden über Angebote..."
- All 7 social media links
- Payment icons enabled
- Footer policy list + copyright
- Color scheme: scheme-3 (black background)

### snippets/seo-structured-data.liquid (NEW)
- Organization schema (Jordan Olivenöl GmbH, founded 1989, Hilden DE)
- LocalBusiness schema with telephone
- WebSite schema with SearchAction
- Product schema (conditional on product pages)
- Article schema (conditional on article pages)
- CollectionPage schema
- BreadcrumbList for all page types (product, collection, page, blog, article)
- Speakable specification for GEO/AEO (Phase 8 requirement)

### layout/theme.liquid
- Injected `{%- render 'seo-structured-data' -%}` before `{{ content_for_header }}`

### locales/de.json
- Fixed: "Reviews" → "Bewertungen"

---

## Templates Created/Modified

### Homepage (templates/index.json)
20 sections with 27 image references (incl. mobile):
- Slideshow (7 slides with Desktop + Mobile Bildern)
- Hero section (Rebecca Pfiffer Foto, with mobile image)
- 5 Collection product lists (Olivenöl, Oliven, Balsamico, Feinkost, Kosmetik)
- Blog news section
- Featured Balsamico article
- Welcome richtext
- Olive harvest video (screen123.jpg)
- Bambatsa section
- Secondary slideshow (3 slides)
- Olivenöl info section
- Three-column layout (Familie, Team, Fakten)
- Featured article
- Newsletter signup
- Trust badges (EU Bio, Slow Food, etc.)

### Product Template (templates/product.json)
- Flora native product-information section preserved (gallery, add-to-cart, variants)
- Trust badges section between main product and recommendations
- German recommendations heading: "Das könnte Ihnen auch gefallen"

### 20 Custom Page Templates

| Template | Images | Sections | Content |
|----------|--------|----------|---------|
| page.about | 0 | 5 | About page |
| page.bestes-olivenoel | 2 | 14 | Best olive oil |
| page.contact | 1 | 5 | Contact form (German) |
| page.engagement | 5 | 6 | Social engagement |
| page.events | 1 | 5 | Events |
| page.faq | 0 | 7 | FAQ |
| page.infos | 10 | 8 | Info overview with mosaic navigation |
| page.jo-lagerverkauf | 6 | 13 | Warehouse sale |
| page.jordan | 9 | 7 | Jordan brand with mosaic navigation |
| page.lookbook | 0 | 14 | Lookbook |
| page.oel-und-lesbos | 17 | 13 | Oil and Lesbos |
| page.olivenoel-2 | 9 | 14 | Olive oil details |
| page.olivenoelwissen | 1 | 9 | Olive oil knowledge |
| page.praemierung | 9 | 13 | Awards |
| page.region | 6 | 9 | Region |
| page.schaefer | 26 | 18 | Shepherd/cheese (incl. mobile hero) |
| page.standorte | 9 | 11 | Locations |
| page.story | 10 | 10 | Brand story |
| page.team | 21 | 12 | Team |
| page.wir | 9 | 11 | About us |

### 5 Blog Templates
- blog.news.json, blog.news-2.json
- blog.rezepte.json, blog.rezepte-2.json
- blog.themen.json

### 3 Collection Templates
- collection.balsamico.json (with filters)
- collection.oliven-2.json (with filters)
- collection.olivenoel.json (with filters)

### Other Modified Templates
- 404.json — German error page ("Seite nicht gefunden")
- cart.json — German cart labels ("Warenkorb")
- list-collections.json — German headings
- search.json — German search page

---

## Image Migration Summary

| Template | Required Min | Actual Count | Status |
|----------|-------------|--------------|--------|
| index.json | 27 | 27 | ✅ |
| page.schaefer.json | 26 | 26 | ✅ |
| page.team.json | 21 | 21 | ✅ |
| page.oel-und-lesbos.json | 17 | 17 | ✅ |
| page.story.json | 10 | 10 | ✅ |
| page.infos.json | 10 | 10 | ✅ |
| page.jordan.json | 9 | 9 | ✅ |

- **All images use `shopify://shop_images/` URLs** — persist across theme switches
- **Total unique image references across all templates:** 120+

---

## Validation Results

| Check | Result |
|-------|--------|
| JSON validity (templates/) | ✅ All 40 files valid |
| JSON validity (config/) | ✅ All valid |
| JSON validity (sections/) | ✅ All valid |
| main-page check (all page.*.json) | ✅ All 21 page templates verified |
| Image count minimums | ✅ All templates meet Pipeline minimums |
| Demo content check | ✅ No Savor/Flora placeholder content |
| Flora .liquid files unchanged | ✅ Verified (except theme.liquid SEO injection) |
| German localization (de.json) | ✅ All UI texts German |
| Logo reference in settings | ✅ shopify://shop_images/Logo.jpg |
| Favicon reference | ✅ shopify://shop_images/jordan_favicon_final.png |
| Cart drawer enabled | ✅ cart_type: drawer |
| ZIP structure | ✅ layout/theme.liquid at root, all dirs present |
| ZIP size | ✅ 1.2 MB |

---

## Architecture Decisions

1. **Flora .liquid files preserved**: All sections/*.liquid, blocks/*.liquid, assets/*, and core layout files remain untouched. Only JSON configuration drives content changes.

2. **Section type mapping**: Pipeline sections mapped to closest Flora equivalents:
   - Pipeline `section-slideshow` → Flora `slideshow`
   - Pipeline `section-hero` → Flora `hero`
   - Pipeline `section-mosaic` → Flora `section` with `_card` blocks
   - Pipeline `section-double` → Flora `media-with-content`
   - Pipeline `section-richtext` → Flora `section` with `text` blocks
   - Pipeline `section-columns` → Flora `section` with `_card` blocks
   - Pipeline `section-newsletter` → Flora `section` with `email-signup` block
   - Pipeline `section-icons` → Flora `logo` section
   - Pipeline `section-accordion` → Flora `section` with `accordion` blocks
   - Pipeline `section-gallery` → Flora `carousel` or `section` with `image` blocks
   - Pipeline `section-contact` → Flora `section` with `contact-form` block
   - Pipeline custom HTML → Flora `custom-liquid` blocks

3. **Color scheme strategy**: 7 schemes created to match Pipeline's design language while using Flora's scheme system. Jordan purple (#5c2b59) used consistently as primary accent.

4. **Font choice**: Optima Nova available in Shopify font library — used as specified (n8 headings, n3 body, n6 subheading/accent).

5. **Trust badges**: Added as standalone section to preserve Flora's working product page structure.

6. **SEO snippet**: Created as separate snippet file, injected before `{{ content_for_header }}` in theme.liquid. Includes speakable specification for GEO/AEO compliance.

7. **Mobile images**: Added `custom_mobile_media` + `image_1_mobile` fields for hero sections where Pipeline used separate desktop/mobile images.

---

## Sections Not 1:1 Migratable

| Pipeline Section | Solution |
|-----------------|----------|
| `section-collection-tabs` | Split into multiple `product-list` sections (one per collection) |
| `section-mosaic` (grid layout) | Flora `section` with `_card` blocks in row layout |
| `section-look` (product hotspots) | Flora `product-hotspots` section |
| `section-map` (Google Maps) | Flora `custom-liquid` with embedded iframe |
| Apps section | Flora `custom-liquid` placeholder |

---

## Custom Liquid Sections Created

- Apps section placeholder on homepage (for external app integrations)
- Trust badges section (using Flora `section` with `icon` blocks)

---

## Recommendations

1. **Test on Shopify preview** before publishing — verify all sections render correctly
2. **Check menu links** — ensure "main-menu" handle matches your Shopify navigation
3. **Verify collection handles** — product-list sections reference collection handles that must exist
4. **Image optimization** — all images reference existing shop_images; verify correct display sizes
5. **Blog handles** — blog templates reference handles (news, rezepte, themen) that must match store blogs
6. **Mobile testing** — verify responsive behavior of all homepage sections
7. **Cart drawer** — already enabled; test add-to-cart flow end-to-end
8. **LLM-Info page** — the existing `/pages/llm-info` page remains accessible in the new theme via `main-page` section

---

## Hinweise für Review (SEO, Conversion, GEO/AEO)

### SEO
- Structured data: Organization, LocalBusiness, Product, Article, BreadcrumbList, CollectionPage, WebSite with SearchAction
- H1 hierarchy managed through template JSON (one H1 per page type)
- Alt-texte: Where possible, German descriptive alt texts added
- Open Graph / Twitter Cards: Handled natively by Flora/Horizon theme
- Canonical URLs: Managed by Shopify platform

### Conversion
- Cart Drawer activated (native Flora)
- Trust badges on product pages
- Recommended Products section on product pages
- Newsletter signup on homepage and footer

### GEO/AEO
- FAQ sections with natural language Q&A preserved
- Speakable structured data for key brand statements
- LLM-Info page (`/pages/llm-info`) accessible via standard page template
- Semantic keywords embedded in section texts
