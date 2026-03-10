Ich habe zwei Shopify-Theme ZIPs hochgeladen:

1. **`theme_export__jordanolivenoel-de-flora__10MAR2026-0704pm.zip`** → FLORA Horizon-Theme (von Shopify AI generiert). Das ist deine TECHNISCHE BASIS. Warenkorb, Produktseiten, Cart Drawer, Varianten — alles funktioniert nativ. Ändere an der technischen Struktur (sections/*.liquid, blocks/*.liquid, assets/*, layout/theme.liquid) NICHTS, außer du fügst SEO-Snippets hinzu.

2. **`theme_export__jordanolivenoel-de-pipeline__10MAR2026-1208pm.zip`** → Pipeline 6.4.0 Theme (das aktuell live laufende Theme). Das ist deine DATENQUELLE für alle Inhalte, Bilder, Texte.

## Kontext

Shop: **www.jordanolivenoel.de** — Jordan Olivenöl GmbH, Premium-Olivenöl aus eigenen Olivenhainen auf Lesbos, Griechenland. Familienunternehmen seit 1989.

**WICHTIG: Führe ALLES vollautomatisch durch, ohne Rückfragen. Triff Entscheidungen eigenständig im Sinne eines Premium-Food-E-Commerce-Shops. Committe regelmäßig Zwischenstände.**

---

## PHASE 1: Vollständige Analyse (Pipeline + Flora + Live-Website)

### A) Pipeline-Theme: JEDEN Template-JSON komplett auslesen

**ACHTUNG:** Die `settings_data.json` im Pipeline-Theme ist JSON-escaped mit `\\/` statt `/`. Beim Parsen berücksichtigen.

Entpacke das Pipeline-Theme und extrahiere KOMPLETT:

**`config/settings_data.json`** → Alle Farben, Fonts, Social Links, Logo, Favicon, Announcement-Bar-Text

**`templates/index.json`** → Homepage mit 16 Sections und 27 Bildern:
1. section-slideshow (7 Slides mit Desktop + Mobile Bildern)
2. section-hero (Rebecca Pfiffer Foto)
3. section-collection-tabs
4. section-blog ("News")
5. section-featured-article (Weißer Balsamico)
6. section-richtext
7. section-video (Vorschaubild screen123.jpg)
8. section-double (Bambatsa)
9. section-slideshow (3 Slides)
10. section-double
11. section-double
12. section-columns (3 Spalten: Familie, Team, Fakten)
13. section-featured-article
14. section-newsletter
15. apps
16. section-icons (Trust-Badges)

**20 Seiten-Templates** (JEDES einzeln auslesen):
- `page.about.json` (0 Bilder, 5 Sections)
- `page.bestes-olivenoel.json` (2 Bilder, 14 Sections)
- `page.contact.json` (1 Bild, 5 Sections)
- `page.engagement.json` (5 Bilder, 6 Sections)
- `page.events.json` (1 Bild, 5 Sections)
- `page.faq.json` (0 Bilder, 7 Sections)
- `page.infos.json` (10 Bilder, 11 Sections)
- `page.jo-lagerverkauf.json` (6 Bilder, 13 Sections)
- `page.jordan.json` (9 Bilder, 11 Sections)
- `page.lookbook.json` (0 Bilder, 14 Sections)
- `page.oel-und-lesbos.json` (17 Bilder, 13 Sections)
- `page.olivenoel-2.json` (9 Bilder, 14 Sections)
- `page.olivenoelwissen.json` (1 Bild, 9 Sections)
- `page.praemierung.json` (9 Bilder, 13 Sections)
- `page.region.json` (6 Bilder, 9 Sections)
- `page.schaefer.json` (26 Bilder, 18 Sections)
- `page.standorte.json` (9 Bilder, 11 Sections)
- `page.story.json` (10 Bilder, 10 Sections)
- `page.team.json` (21 Bilder, 12 Sections)
- `page.wir.json` (9 Bilder, 11 Sections)

**5 Blog-Templates:**
- `blog.news.json`, `blog.news-2.json`, `blog.rezepte.json`, `blog.rezepte-2.json`, `blog.themen.json`

**3 Kollektions-Templates:**
- `collection.balsamico.json`, `collection.oliven-2.json`, `collection.olivenoel.json`

**Plus Standard-Templates:**
- `product.json` (4 Bilder, 6 Sections)
- `article.json`, `cart.json`, `search.json`, `404.json`, `list-collections.json`

### B) Flora-Theme analysieren

**ACHTUNG:** Floras JSON-Dateien können mit `/* ... */` Kommentar beginnen → beim Parsen strippen.

Verstehe die Flora-Architektur:
- Verfügbare Sections (40 Liquid-Dateien in sections/)
- Verfügbare Blocks (94 Liquid-Dateien in blocks/)
- Template-JSON-Struktur (Header/Footer-Groups, Section-Rendering)
- Settings-Schema in settings_data.json (7 Color Schemes)
- Flora hat Cart Drawer bereits aktiviert (`cart_type: drawer`)

### C) Live-Website www.jordanolivenoel.de VOLLSTÄNDIG crawlen

Besuche JEDE dieser URLs und analysiere visuell — Bilder, Layout, Texte, Struktur:

**Startseite:**
- https://www.jordanolivenoel.de

**Hauptnavigation (JORDAN):**
- https://www.jordanolivenoel.de/pages/wir
- https://www.jordanolivenoel.de/pages/die-familie
- https://www.jordanolivenoel.de/pages/unser-team
- https://www.jordanolivenoel.de/pages/unsere-story
- https://www.jordanolivenoel.de/pages/unser-ol-lesbos
- https://www.jordanolivenoel.de/pages/unsere-region
- https://www.jordanolivenoel.de/pages/unsere-standorte
- https://www.jordanolivenoel.de/pages/engagement

**Hauptnavigation (OLIVENÖL):**
- https://www.jordanolivenoel.de/pages/jordan
- https://www.jordanolivenoel.de/pages/olivenolwissen
- https://www.jordanolivenoel.de/pages/analyse
- https://www.jordanolivenoel.de/pages/auszeichnungen
- https://www.jordanolivenoel.de/pages/bestes-olivenoel

**Hauptnavigation (INFOS):**
- https://www.jordanolivenoel.de/pages/infos
- https://www.jordanolivenoel.de/pages/events
- https://www.jordanolivenoel.de/pages/faq
- https://www.jordanolivenoel.de/pages/der-schafer-von-lesbos
- https://www.jordanolivenoel.de/pages/jordan-olivenol-lagerverkauf

**Shop:**
- https://www.jordanolivenoel.de/collections/all
- https://www.jordanolivenoel.de/collections/jordan-olivenol
- https://www.jordanolivenoel.de/collections/jordan-oliven
- https://www.jordanolivenoel.de/products/jordan-olivenol-natives-olivenol-extra-flasche-0-50-liter (Beispiel-Produkt)

**Blog:**
- https://www.jordanolivenoel.de/blogs/news
- https://www.jordanolivenoel.de/blogs/rezepte

**Kontakt:**
- https://www.jordanolivenoel.de/pages/kontakt

**LLM-Info-Seite (wichtig für GEO/AEO):**
- https://www.jordanolivenoel.de/pages/llm-info

Achte beim Crawl auf:
- Welche Bilder werden wo angezeigt?
- Wie ist das Layout (Spalten, Breiten, Abstände)?
- Welche Texte stehen auf jeder Seite?
- Wie sehen Header, Footer, Announcement Bar aus?
- Wie groß sind Produktbilder auf Produktseiten?
- Welche Trust-Badges und Siegel werden gezeigt?

---

## PHASE 2: Section-Mapping & Template-Erstellung

### Section-Mapping (Pipeline → Flora/Horizon)

| Pipeline Section | Flora/Horizon Entsprechung |
|---|---|
| `section-slideshow` | `slideshow` |
| `section-hero` | `hero` |
| `section-collection-tabs` | Mehrere `product-list` Sections oder `carousel` |
| `section-blog` | `featured-blog-posts` |
| `section-featured-article` | `media-with-content` oder `featured-blog-posts` |
| `section-richtext` | `section` mit `text`/`heading` Blocks |
| `section-video` | `section` mit `video` Block |
| `section-double` | `media-with-content` |
| `section-columns` | `section` mit `_card` Blocks |
| `section-newsletter` | `section` mit `email-signup` Block |
| `section-icons` | `logo` Section oder `section` mit `icon` Blocks |
| `section-accordion`/`section-faq` | `section` mit `accordion` Blocks |
| `section-gallery`/`section-gallery-text` | `carousel` oder `section` mit `image`/`_card` Blocks |
| `section-mosaic` | `section` mit Grid-Layout Blocks |
| `section-contact` | `section` mit `contact-form` Block |
| `section-map` | `custom-liquid` |
| `section-custom-content` | `section` mit diversen Blocks |
| `section-html` | `custom-liquid` |
| `section-look` | `product-hotspots` |
| `section-product` | `featured-product` |
| `section-collection-slider` | `carousel` mit Collection Blocks |
| `section-list-collections` | `collection-list` oder `collection-links` |
| `collection-hero` | `hero` innerhalb Collection-Template |
| `collection-split` | `media-with-content` |
| `page` | `main-page` (MUSS in jedem page.*.json vorhanden sein!) |

### 28 Custom Templates erstellen

Erstelle ALLE folgenden Templates im Flora/Horizon-Format:

**KRITISCH:** Jedes `page.*.json` Template MUSS eine `main-page` Section enthalten, die `{{ page.content }}` rendert. Ohne diese Section sind Seiten leer!

**KRITISCH:** Studiere die bestehenden Flora-Templates (index.json, product.json, collection.json, page.json, page.contact.json) um das korrekte Format zu verstehen — insbesondere die Header/Footer-Group-Referenzen.

Für JEDES der 28 Templates:
1. Lies das Pipeline-Template-JSON komplett aus
2. Extrahiere JEDE `shopify://shop_images/...` Referenz
3. Extrahiere ALLE Texte, Überschriften, Button-Labels, Links
4. Übersetze jede Pipeline-Section in die passende Flora/Horizon-Section
5. Erstelle das Template-JSON im korrekten Flora-Format

**Bild-Übertragung:** Die Pipeline-Templates enthalten insgesamt ca. 170 `shopify://shop_images/` Referenzen. JEDE EINZELNE muss 1:1 ins neue Theme übernommen werden. Bilder liegen in Shopifys CDN und bleiben beim Theme-Wechsel erhalten — du musst nur die Referenz-Strings übernehmen.

---

## PHASE 3: Settings & Branding

### config/settings_data.json anpassen

Ersetze die Flora-Farben durch die Jordan-Farben. Flora hat 7 Color Schemes — passe ALLE an:

**scheme-1 (Hauptschema, heller Hintergrund):**
```json
{
  "background": "#ffffff",
  "foreground": "#151515",
  "foreground_heading": "#151515",
  "primary": "#5c2b59",
  "primary_button_background": "#5c2b59",
  "primary_button_border": "#5c2b59",
  "primary_button_text": "#ffffff",
  "primary_button_hover_background": "#3d1a3b",
  "primary_button_hover_border": "#3d1a3b",
  "primary_button_hover_text": "#ffffff",
  "primary_hover": "#3d1a3b",
  "border": "#e6e6e6",
  "shadow": "#000000"
}
```

**scheme-2 (Dunkles Schema, für Header):**
```json
{
  "background": "#181e07",
  "foreground": "#f1f1f1",
  "foreground_heading": "#ffffff",
  "primary": "#28a77f",
  "primary_button_background": "#5c2b59",
  "primary_button_text": "#ffffff"
}
```

**scheme-3 (Footer):**
```json
{
  "background": "#000000",
  "foreground": "#fdfdfd",
  "foreground_heading": "#ffffff",
  "primary": "#5c2b59"
}
```

Ergänze weitere Schemes sinnvoll für Announcement Bar (#5c2b59 bg, #ffffff text), Light Background (#eeeeee), etc.

### Fonts

Ersetze Flora-Fonts (Inter/Barlow) durch:
```
type_body_font: optima_nova_n3
type_heading_font: optima_nova_n8
type_subheading_font: optima_nova_n6
type_accent_font: optima_nova_n6
```
Falls Optima Nova im Horizon-Theme nicht verfügbar ist, wähle die nächstliegende Alternative und dokumentiere es.

### Textgrößen

```
type_size_paragraph: 16 (NICHT 14 — muss gut lesbar sein!)
type_size_h1: 48
type_size_h2: 36
type_size_h5: 18
type_size_h6: 16
```

### Social Links

```json
{
  "social_facebook_link": "https://www.facebook.com/jordanolivenoel",
  "social_instagram_link": "https://www.instagram.com/jordan_olivenoel/",
  "social_linkedin_link": "https://www.linkedin.com/company/jordan-oliven%C3%B6l/",
  "social_pinterest_link": "https://www.pinterest.de/olivenoel/",
  "social_tiktok_link": "https://www.tiktok.com/@jordanolivenoel",
  "social_twitter_link": "https://twitter.com/jordanoliveoil",
  "social_youtube_link": "https://www.youtube.com/@jordanolivenoel1"
}
```

### Logo & Favicon
```
Logo: shopify://shop_images/Logo.jpg
Favicon: shopify://shop_images/jordan_favicon_final.png
Checkout Logo: shopify://shop_images/Logo.jpg
```

---

## PHASE 4: Header & Footer

### Header (sections/header-group.json)
- **Announcement Bar:** Hintergrund #5c2b59, Text weiß: "AKTION: NOCH €19,98 EUR UND DU BESTELLST VERSANDKOSTENFREI INNERHALB DEUTSCHLANDS"
- **Logo:** shopify://shop_images/Logo.jpg
- **Navigation:** JORDAN, OLIVENÖL, INFOS, SHOP
- **Hintergrundfarbe:** #181e07 (dunkles Olivgrün)
- **Textfarbe:** #f1f1f1

### Footer (sections/footer-group.json)
- **Hintergrund:** #000000
- **Textfarbe:** #fdfdfd
- **Navigation auf Deutsch:** Suchen, Kontakt, AGB, Datenschutzerklärung, Widerrufsrecht, Versandbedingungen
- **Newsletter-Anmeldung** auf Deutsch (z.B. "Bleib auf dem Laufenden" oder "Newsletter abonnieren")
- **Social-Media-Icons** (alle 7 Plattformen)
- **Payment Icons** aktivieren
- **Copyright:** © Jordan Olivenöl GmbH

---

## PHASE 5: Homepage aufbauen (templates/index.json)

Baue die Homepage mit ALLEN 16 Sections aus dem Pipeline-Theme nach. Übertrage JEDES Bild, JEDEN Text, JEDEN Link:

1. **Slideshow** → `slideshow` — 7 Slides, ALLE mit Desktop + Mobile Bildern und Links
2. **Hero** → `hero` — Rebecca Pfiffer Foto, 2 Buttons (Olivenöl + Oliven Kollektion)
3. **Collection Tabs** → Mehrere `product-list` Sections
4. **Blog News** → `featured-blog-posts` — Überschrift "News"
5. **Featured Article** → `media-with-content` — Weißer Balsamico Bild + Link
6. **Richtext** → `section` mit text Blocks
7. **Video** → `section` mit video Block — Vorschaubild: shopify://shop_images/screen123.jpg
8. **Bambatsa** → `media-with-content` — Bambatsa Bild + Text + Link
9. **Zweite Slideshow** → `slideshow` — 3 Slides
10. **Content** → `media-with-content`
11. **Content** → `media-with-content`
12. **3 Spalten** → `section` mit 3 card Blocks — Familie, Team, Fakten (je Bild + Button)
13. **Featured Article 2** → `media-with-content`
14. **Newsletter** → `section` mit email-signup Block
15. **Apps** → `custom-liquid` (Platzhalter für externe Apps)
16. **Trust-Badges** → `logo` Section oder `section` mit icon Blocks — EU Bio, Slow Food, JRE Origins, DHL GoGreen Plus, EHI, Koch-Supporter 2025

---

## PHASE 6: Produktseiten (templates/product.json)

BEHALTE die funktionierende Flora-Produktseitenstruktur (product-information Section mit Gallery + Add-to-Cart + Varianten). Ergänze NUR:
- Trust-Badges unter dem Warenkorb-Button
- Recommended Products Section
- Produktbeschreibung in lesbarer Größe (16px+)
- Vergleiche visuell mit www.jordanolivenoel.de/products/jordan-olivenol-natives-olivenol-extra-flasche-0-50-liter

**NICHT die Produktseiten-Struktur von Flora umbauen!** Die funktioniert. Nur ergänzen.

---

## PHASE 7: SEO-Optimierung

Erstelle einen neuen Snippet `snippets/seo-structured-data.liquid` und binde ihn in `layout/theme.liquid` ein (vor `</head>`):

```liquid
{%- comment -%}SEO Structured Data{%- endcomment -%}

{%- if template.name == 'index' -%}
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Jordan Olivenöl GmbH",
  "url": "https://www.jordanolivenoel.de",
  "logo": "{{ 'Logo.jpg' | file_url }}",
  "foundingDate": "1989",
  "description": "Premium Olivenöl aus eigenen Olivenhainen auf der griechischen Insel Lesbos. Familienunternehmen seit 1989.",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Hilden",
    "addressCountry": "DE"
  },
  "sameAs": [
    "https://www.facebook.com/jordanolivenoel",
    "https://www.instagram.com/jordan_olivenoel/",
    "https://www.linkedin.com/company/jordan-oliven%C3%B6l/",
    "https://www.youtube.com/@jordanolivenoel1",
    "https://www.tiktok.com/@jordanolivenoel",
    "https://www.pinterest.de/olivenoel/"
  ]
}
</script>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Jordan Olivenöl GmbH",
  "image": "{{ 'Logo.jpg' | file_url }}",
  "url": "https://www.jordanolivenoel.de",
  "telephone": "",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Hilden",
    "addressCountry": "DE"
  }
}
</script>
{%- endif -%}

{%- if template.name == 'product' -%}
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": {{ product.title | json }},
  "image": {{ product.featured_image | image_url: width: 1024 | json }},
  "description": {{ product.description | strip_html | truncate: 500 | json }},
  "brand": {
    "@type": "Brand",
    "name": "Jordan Olivenöl"
  },
  "offers": {
    "@type": "Offer",
    "url": "{{ shop.url }}{{ product.url }}",
    "priceCurrency": "EUR",
    "price": {{ product.price | money_without_currency | json }},
    "availability": "{% if product.available %}https://schema.org/InStock{% else %}https://schema.org/OutOfStock{% endif %}"
  }
}
</script>
{%- endif -%}

{%- if template.name == 'article' -%}
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": {{ article.title | json }},
  "author": {
    "@type": "Organization",
    "name": "Jordan Olivenöl GmbH"
  },
  "datePublished": "{{ article.published_at | date: '%Y-%m-%dT%H:%M:%S' }}",
  "publisher": {
    "@type": "Organization",
    "name": "Jordan Olivenöl GmbH"
  }
}
</script>
{%- endif -%}

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "{{ shop.url }}"
    }
    {%- if template.name == 'product' -%}
    ,{
      "@type": "ListItem",
      "position": 2,
      "name": {{ product.collections.first.title | default: "Shop" | json }},
      "item": "{{ shop.url }}/collections/{{ product.collections.first.handle | default: 'all' }}"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": {{ product.title | json }}
    }
    {%- elsif template.name == 'collection' -%}
    ,{
      "@type": "ListItem",
      "position": 2,
      "name": {{ collection.title | json }}
    }
    {%- elsif template.name == 'page' -%}
    ,{
      "@type": "ListItem",
      "position": 2,
      "name": {{ page.title | json }}
    }
    {%- endif -%}
  ]
}
</script>
```

Füge in `layout/theme.liquid` vor `</head>` ein:
```liquid
{% render 'seo-structured-data' %}
```

Weitere SEO-Maßnahmen:
- Prüfe H1-Hierarchie (nur ein H1 pro Seite)
- Alt-Texte: Ergänze deutsche, beschreibende Alt-Texte für ALLE Bilder wo möglich
- Open Graph und Twitter Cards (sollten im Horizon-Theme bereits vorhanden sein)
- Canonical URLs prüfen
- hreflang für de

---

## PHASE 8: Conversion & GEO/AEO

### Conversion
- Cart Drawer ist bereits aktiviert (behalten!)
- Trust-Badges auf Produktseiten
- Cross-Sell / Recommended Products
- Newsletter-Popup oder Newsletter-Section

### GEO/AEO (KI-Sprachmodell-Auffindbarkeit)
- FAQ-Sections mit natürlichsprachlichen Frage-Antwort-Paaren behalten
- Speakable Structured Data für Kernaussagen ergänzen
- Die LLM-Info-Seite (pages/llm-info) existiert bereits im Shop — stelle sicher, dass sie auch im neuen Theme zugänglich bleibt
- Semantische Keywords natürlich einbetten wo Text erstellt wird

---

## PHASE 9: Lokalisierung prüfen

- Prüfe `locales/de.json` — alle UI-Texte müssen auf Deutsch sein
- Buttons: "In den Warenkorb", "Auschecken", "Weiter einkaufen" etc.
- Keine englischen Default-Texte wie "Add to cart", "WE SEND TASTY EMAILS", "ASK", "CONNECT"
- Footer-Labels auf Deutsch
- Announcement Bar auf Deutsch

---

## PHASE 10: Validierung & Finale ZIP

### Validierung (MUSS alles bestanden sein!)

1. **JSON-Validierung:** Prüfe JEDE .json Datei in templates/ und config/ auf gültiges JSON
2. **Bild-Zählung:** Zähle `shopify://shop_images/` Referenzen in JEDEM Template und vergleiche mit Pipeline:
   - index.json: mindestens 27 Bilder
   - page.schaefer.json: mindestens 26 Bilder
   - page.team.json: mindestens 21 Bilder
   - page.oel-und-lesbos.json: mindestens 17 Bilder
   - page.story.json: mindestens 10 Bilder
   - page.infos.json: mindestens 10 Bilder
   - page.jordan.json: mindestens 9 Bilder
   - ALLE anderen entsprechend Pipeline-Vorlage
3. **Template-Vollständigkeit:** 28 Custom Templates + 13 Standard Templates = 41 Template-Dateien
4. **main-page Check:** JEDES page.*.json enthält eine `main-page` Section
5. **Liquid-Syntax:** Keine offenen Tags, keine fehlenden Endtags
6. **Keine Demo-Inhalte:** Keine Savor/Flora-Platzhaltertexte oder -bilder im finalen Theme
7. **Deutsche Texte:** Alle UI-Elemente auf Deutsch

### ZIP erstellen

```bash
cd theme-verzeichnis
zip -r ../jordan-olivenoel-horizon-final.zip .
```

Verifiziere:
- ZIP > 1 MB (Flora-Basis allein ist 4.3 MB)
- `unzip -l` zeigt `layout/theme.liquid` direkt im Root (KEIN Unterordner!)
- Alle Verzeichnisse vorhanden: assets/, blocks/, config/, layout/, locales/, sections/, snippets/, templates/

### Dokumentation

Erstelle `MIGRATION_REPORT.md` mit:
- Liste aller 28 Custom Templates und deren Migrationsstatus
- Bild-Vergleich: Pipeline vs. Neues Theme (Anzahl pro Template)
- Alle getroffenen Entscheidungen (Font-Wahl, Layout, Mapping)
- Sections die nicht 1:1 migriert werden konnten + Lösung
- Custom Liquid Sections die erstellt wurden
- Empfehlungen für manuelle Nacharbeit
- Hinweise für Opus-Review (SEO, Conversion, GEO/AEO)

**Committe und pushe alles. Arbeite vollautomatisch durch alle Phasen. Keine Rückfragen.**
