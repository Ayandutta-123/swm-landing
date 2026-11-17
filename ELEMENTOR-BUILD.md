# Elementor Rebuild Guide — Smart Waste Management

Use this to rebuild [`index.html`](index.html) on WordPress with Elementor, matching [Smart Helmet](https://hyperthings.ai/smart-helmet/) patterns and HyperThings brand tokens.

**Target page:** edit existing `Smart Solid Waste Management`  
**Slug:** `smart-solid-wastemanagement`  
**Template:** Elementor Canvas or Theme Builder content area only (keep site header/footer)

---

## Global styles (Site Settings → Global / Custom CSS)

```css
:root {
  --ht-red: #C1262A;
  --ht-navy: #0A0349;
  --ht-body: #555555;
  --ht-soft: #F7F7FB;
  --ht-red-soft: #FCEEEE;
}
```

| Role | Color | Font |
|---|---|---|
| H1 | `#0A0349` | DM Sans / 900 / ~34px desktop |
| H2 | `#0A0349` | Roboto / 600 / ~28px |
| Eyebrow | `#C1262A` | Inter / 500 / ~17px |
| Body | `#555555` | Inter or Nunito / 16px |
| Primary button | BG `#C1262A`, text `#FFF` | Montserrat 600 |
| Secondary button | BG `#FFF`, border `#0A0349`, text `#0A0349` | Montserrat 600 |
| Navy button | BG `#0A0349`, text `#FFF` | Montserrat 600 |

**Content width:** 1140px  
**Section padding:** Desktop 70–90px · Tablet 50px · Mobile 40px  
**Card radius:** 12px · **Button radius:** 8px  
**Card shadow:** `0 10px 30px rgba(10,3,73,0.08)`

---

## Build order (do not skip)

### 0. Page SEO (before design)

1. Yoast/Rank Math: paste title + meta from [`SEO.md`](SEO.md)
2. Add FAQ/Product JSON-LD from SEO.md (Custom HTML in `<head>` or SEO plugin schema)
3. Upload PDF brochure to Media Library → copy URL for secondary CTA

### 1. Hero section

- **Layout:** 2 columns (55% / 45%) · Mobile: stack, copy first
- **Background:** white → soft gradient (optional Custom CSS from preview)
- **Left widgets:**
  1. Text / Badge: `SMART WASTE MANAGEMENT` — pill BG `#FCEEEE`, color `#C1262A`
  2. Heading H1 — copy from [`COPY-DECK.md`](COPY-DECK.md)
  3. Text Editor — subcopy
  4. Button group: `Get a Free Demo` (link `#demo` or demo form) + `Download Solution Brief` (Media PDF URL)
- **Right:** Image widget (product/sensor art) OR HTML widget with hero visual from preview
- **Motion:** Elementor entrance — fade/slide up on copy (stagger 100ms). Respect reduced motion.

### 2. Challenges

- Eyebrow + H2
- **Inner section:** 3 columns desktop · 2 tablet · 1 mobile
- 6 Icon Box / Icon + Heading + Text cards (copy from Challenges table)
- Icon circle BG `#FCEEEE`, icon color `#C1262A`

### 3. How We Help

- Eyebrow + H2
- 5 Icon Boxes in grid (3 + 2 on desktop, or carousel if matching Helmet carousel pattern)
- Card style: white, soft shadow, icon in circular lavender (`#EFEEF8`) with red stroke icons

### 4. How It Works

- Soft BG `#F7F7FB`
- Eyebrow + H2 + intro paragraph
- **Numbered list:** use Icon List with numbers 1–5 OR process widget
- Steps from COPY-DECK flow

### 5. Application Features

- White BG
- Icon List (check style) in 2 columns — 8 features from PDF/COPY-DECK

### 6. Hardware Options

- Soft BG
- 2-column Inner Section
- Each column: Heading H3 + Text + Icon List (Ultrasonic / Radar specs)
- Top border accent `#C1262A` (4px) via border settings

### 7. Architecture

- White BG
- Stacked boxes (or HTML widget from preview `.arch` block)
- Tags as text with border/pill style
- Keep accessible: include short text explanation under diagram for screen readers

### 8. Why HyperThings

- Soft BG
- Intro + 6 benefit items (Icon List or 2×3 grid)
- Red dots / check icons

### 9. FAQ

- Use **Elementor Accordion** or Nested Accordion
- Paste 7 Q&As from COPY-DECK
- Title color `#0A0349`, icon `#C1262A`
- Mobile: ensure summary min-height ≥ 44px

### 10. Demo / Contact

- Section ID: `demo`
- Dark gradient BG navy→red (match Helmet contact energy) OR reuse existing site demo section shortcode
- **Preferred:** keep current page Contact Form 7 / Elementor Form widgets already on `/smart-solid-wastemanagement/`
- Fields: Name, Phone, Email, Company Name, Comment
- Submit button: primary red
- Side text: phone +918043009796, email info@hyperthings.ai
- Internal links: Smart City, Waste Bin Sensor

---

## Mobile checklist in Elementor

| Breakpoint | Actions |
|---|---|
| Tablet &lt; 1024 | Feature cards → 2 col; hardware 1–2 col |
| Mobile &lt; 768 | All 1 col; CTAs full width; hide secondary header CTA if theme duplicates; increase section padding consistency |
| All | No horizontal scroll; images max-width 100%; FAQ tap targets large |

---

## Widget map (quick)

| Section | Elementor widgets |
|---|---|
| Hero | Heading, Text, Button ×2, Image/HTML |
| Challenges | Heading, Icon Box ×6 |
| How We Help | Heading, Icon Box ×5 |
| How It Works | Heading, Text, Icon List / Process |
| App Features | Heading, Icon List |
| Hardware | Heading, Inner Section ×2, Icon List |
| Architecture | HTML or nested boxes |
| Why | Heading, Text, Icon List |
| FAQ | Accordion |
| Demo | Heading, Text, Form / Shortcode |

---

## Publish steps

1. Rebuild sections above on the existing SWM page (or paste HTML widget sections carefully — prefer native widgets for Helmet parity)
2. Link brochure PDF on secondary CTA
3. Set SEO meta + schema
4. Preview desktop / tablet / mobile in Elementor
5. Publish → hard refresh → test form submission
6. Submit URL for indexing (Search Console) after go-live

---

## Optional: HTML Widget path (faster)

If you need speed, each major section in [`index.html`](index.html) can be copied into an Elementor **HTML** widget with [`assets/swm.css`](assets/swm.css) enqueued via Appearance → Customize → Additional CSS (or a small child-theme enqueue). Native widgets are preferred for long-term editability.
