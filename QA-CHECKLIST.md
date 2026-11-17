# QA Checklist — Smart Waste Management Landing Preview

**Preview URL tested:** `http://localhost:5173/`  
**Date:** 2026-11-17  
**Source files:** `index.html`, `assets/swm.css`

## Desktop (~1440 CSS px / browser canvas)

| Check | Result | Notes |
|---|---|---|
| Page loads with correct title | Pass | `Smart Waste Management Solution \| IoT Bin Sensors \| HyperThings` |
| Single H1 | Pass | 1 H1 only |
| Brand colors | Pass | Navy `#0A0349`, red `#C1262A` on CTAs/eyebrows |
| Hero composition | Pass | Pill + H1 + lead + dual CTAs + visual |
| No horizontal overflow | Pass | `scrollWidth <= clientWidth` |
| Button tap heights ≥ 44px | Pass | All `.btn` = 44px |
| FAQ accordion opens | Pass | `details.open` toggles; body visible |
| Form fields present | Pass | Name, Phone, Email, Company, Comment, Submit |
| Internal links | Pass | Smart City, Waste Bin Sensor, demo anchors |
| JSON-LD present | Pass | WebPage + SoftwareApplication + FAQPage in `<head>` |

## Mobile (390×844 emulation)

| Check | Result | Notes |
|---|---|---|
| Nav links hidden | Pass | Primary nav not shown; logo + Request Demo remain |
| Contact Sales hidden in header | Pass | Per CSS mobile rule |
| Hero CTAs full width | Pass | Both ~358px (~full content width) |
| Cards stack single column | Pass | Challenges / features stack |
| No horizontal overflow | Pass | No `h_overflow` |
| Hero chips not clipped | Pass | All chip bounds inside viewport |
| FAQ tap targets ≥ 44px | Pass | Summary heights 63–64px |
| Form usable | Pass | Inputs min-height 44px; stacked layout |

## Style match pass (vs live smart-helmet)

Verified computed styles against hyperthings.ai/smart-helmet/:

| Token | Live | Our page |
|---|---|---|
| H1 | DM Sans 900 / 34px / #0A0349 / ls 1px | Match |
| H2 | Roboto 600 / 28px / #0A0349 / ls 1px | Match |
| Eyebrow | Inter 500 / 17px / #C1262A / ls 1px | Match |
| Lead | DM Sans 16px / #4A4A6D | Match |
| Feature card | 10px radius, 20px pad, `0 0 10px rgba(0,0,0,.2)` | Match |
| Card title | DM Sans 600 / 18px / #0A0349 | Match |
| Card body | DM Sans 15px / #4A5565 | Match |
| Hero CTA | DM Sans 15px / 12px radius / 50px tall | Match |
| Header pills | Nunito 12px / 40px radius / #C3252D & #232156 | Match |
| Soft section | #F9FAFB | Match |
| Logo | live PNG 170×45 | Match |

## Fixes applied during QA

1. Full brand/token rewrite to match live Elementor computed styles (fonts, colors, cards, buttons).
2. Real HyperThings logo image; header CTAs as site pill buttons.
3. Feature cards: text-left / icon-right, 78px lavender icon circle.
4. Brochure CTA kept as placeholder (`#demo`) until PDF is uploaded to WP Media.

## Known publish-time actions (not bugs)

- Replace Download Solution Brief href with WordPress Media URL for `HTS_SWM_Solution` PDF.
- Wire demo form to existing CF7 / Elementor Form / CRM endpoint (preview form is UI-only).
- Swap hero visual for final product photography when available.
- Rebuild with native Elementor widgets per `ELEMENTOR-BUILD.md` (or enqueue CSS + HTML widgets).

## Verdict

**PASS — ready for Elementor rebuild/publish.** Desktop and mobile bug tests completed; no blocking layout or accessibility defects found in the preview package.
