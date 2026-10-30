---
name: smb-site-design
description: Rules for designing small-business websites (clinic, boutique hotel, wedding venue, manufacturer/B2B, beauty salon) that don't look AI-generated. Ban list with replacements, sector directions (font pairs, palette, layout, trust signals), distinct page skeletons, working without stock photos, and a 10-point pre-delivery check. Use when building a business site, demo site or landing page, or when fixing a site that "looks like a template".
---

# Small-business site design

Goal: the owner looks at the site and says "this was made for us", not "this is a template".
Default constraint: a single `index.html` with inline CSS; external resources limited to Google Fonts and, optionally, GSAP/Lenis from a CDN.

## 0. Write first, then code (5 minutes)
Before writing any code, write these 5 lines. If one is empty, don't start.
1. **The one real difference of this business** (e.g. "downtown, 24/7 emergency", "garden for 140 guests", "CE-certified stainless tanks").
2. **The visitor's one job** (call / WhatsApp / check a date / request a quote).
3. **Material:** 3 concrete things from the business's own world: sign color, floor, product, neighborhood, machinery. Color and texture come from here.
4. **Palette:** 4-6 named hex values (background, text, primary, one accent, rule line).
5. **Font pair and layout idea:** one sentence plus a rough sketch. Then ask: "Would I build the same thing for another business in this sector?" If yes, change it.

## 1. Ban list (AI tells)
| Banned | Instead |
| --- | --- |
| 2-3 color `radial-gradient` blobs or halos in the hero | Flat color field, a real photo, or large type |
| Cream/beige background (around #F4F1EA) + thin serif + copper/gold accent | A palette taken from the business's own material (see sectors) |
| Cormorant/Fraunces + Manrope on every site | The pairs in the sector table; never the same pair twice in a row |
| One word in the headline set in italic or color | If emphasis is needed, use weight or size of the same font |
| Every section the same: heading + 3 cards + FAQ + contact | Sections shaped by content; at least one list/table and one full-bleed section |
| 8-10 different `border-radius` values, everything a rounded card | Two radii at most, or none |
| The same fade-up entrance on every section | Each section gets its own motion; `prefers-reduced-motion` is mandatory |
| Small ALL-CAPS label above headings (eyebrow) | Let the heading speak for itself |
| 01 / 02 / 03 section numbers | Only when there is a real sequence (booking steps) |
| Pill-shaped buttons, condensed bold ALL-CAPS headlines | Plain grotesk, sentence case, modest corners |
| Purple-blue gradients, gradient text, neon glow | Flat color, emphasis through contrast |
| Inter, Poppins, Montserrat, Geist, Space Grotesk by default | The sector table |
| Monospace/typewriter fonts as decoration | The body font; `tabular-nums` for figures |
| Emoji or ✓ ★ → characters used as icons | One open-license icon set (Tabler, Phosphor) at one stroke weight, inline SVG |
| Boxed icon above a heading + 3 equal cards | Icon inline next to the text; a list without cards |
| Fake numbers ("98% satisfaction", "10,000+ clients"), fake reviews | Verified real information, or nothing |
| Empty phrases: "your dream", "unique experience", "quality and trust", "one-stop shop" | Concrete facts: hours, price range, capacity, neighborhood, names |
| "Not X. Y." pattern, an em dash in every sentence | Plain, short sentences |
| Cards with a thick colored stripe on the left edge | No stripe, or a 1px rule |
| Stock arrow buttons like "Book now →" | Name the action: "Message us on WhatsApp", "Check the date" |

## 2. Mandatory rules
- **Type:** two families at most, 2-3 weights each. Body 17-18px, 60-72 characters per line. Large headings get `letter-spacing` between -0.01em and -0.03em; never tighten small text. `text-wrap: balance` on headings, `pretty` on paragraphs.
- **Local characters:** if the site isn't in English, the font must cover that language (e.g. `latin-ext`). Before delivery, render a test line of the language's special characters on screen (for Turkish: "ĞÜŞİÖÇ ığüşiöç").
- **Color:** one primary, one accent. The accent appears in 3-5 places on the page. Grey text is derived from the background hue. Body contrast ≥ 4.5:1.
- **Layout:** instead of a symmetric centered hero, use left alignment or an asymmetric grid (e.g. 7/5 columns). Related items close, groups far apart. One section should "break" the rhythm: a full-bleed band, oversized type, or a table.
- **Real content is the design:** price list, opening hours, address and directions, capacity, the doctor's or craftsman's name are never hidden in decorative cards; they become a readable table or list.
- **Browser details:** `::selection` color, `:focus-visible` ring, `accent-color`, link `text-underline-offset`, all from the palette.
- **Mobile first:** no horizontal scroll at 375px; a fixed bottom bar with one action (Call / WhatsApp).
- **Motion:** the site should feel alive in the first second, but motion must come from the content. Examples: line-masked headline reveal in the hero, 2-3 scroll-driven scenes (pinned section, horizontal strip, a drawn SVG line), a counter or a staggered list, micro-interactions on buttons and cards. Use one signature easing curve. Animate only `transform`, `opacity` and `clip-path`. Everything turns off under `prefers-reduced-motion`, and the page reads fully without motion. Text meant to be read never sits on a moving background; put it on an opaque panel.

## 3. Sector directions
All fonts are on Google Fonts with `latin-ext` coverage. Palettes are examples; the real source is the business's own color.

| Sector | Font pair (heading / body) | Palette direction | Layout | Trust signals |
| --- | --- | --- | --- | --- |
| Health / clinic | Schibsted Grotesk / Atkinson Hyperlegible Next · alt: Hanken Grotesk alone | Clinical white (#F6F7F7), deep petrol text (#10353C), one warm accent (e.g. coral #D9583B); no pastel blue-green | Plain left-aligned hero: doctor's name + specialty + neighborhood; treatments below as a table | Doctor's name and specialty, licensed facility info, how the first visit works, opening hours. Health advertising is regulated in many countries: skip before/after photos and patient testimonials unless allowed |
| Boutique hotel / tourism | Gloock / Hanken Grotesk · alt: Bodoni Moda (upright) / Archivo | The building's and the city's colors: stone grey, night blue, olive; a dark theme is fine for an evening-mood hotel | Date and guest picker or a "Book direct" bar in the hero; rooms shown large, one by one; walking distances listed in the location section | Book-direct benefit, check-in/out times, tourism license number, a sourced review score, cancellation policy |
| Wedding / event venue | Bodoni Moda / Albert Sans · alt: Libre Caslon Display / Jost | The venue's real light: garden green (#1F3A2E), lime white (#EEF0EC), one dusty-rose accent; no pink + gold, no script fonts | "Is your date free?" at the very top; hall/garden options as a table (capacity, seating); menu price range | Capacity, parking, menu price range, floor plan, bridal room |
| Manufacturer / B2B | Archivo (condensed, 700) / IBM Plex Sans · alt: Barlow Condensed / Public Sans | Steel grey + white + the sector's signal color (safety yellow #F2B705); `tabular-nums` for figures | One sentence on what they make + a technical capacity line; product groups as a table; machinery list | ISO/CE certificates with numbers, production area, founding year, export countries, technical datasheet, references only with permission |
| Beauty / aesthetics salon | Hedvig Letters Serif / Hedvig Letters Sans · alt: Bricolage Grotesque alone | One strong color from the salon's interior or logo + neutrals; no blush pink + gold | The service and price list is the backbone of the page (like a menu); specialist names; one-tap WhatsApp booking | Price list, specialist names, hygiene/sterilization, product brands used, opening hours |

For other sectors use the same method: the business's material → palette; the visitor's one job → hero.

## 4. Design creates the impact, not stock photos
- No stock photos. Never represent the venue, product or people with AI-generated images.
- If the business has its **own** photos (with permission), use them; if not, let the design carry the page: oversized type, one strong visual idea, strong contrast (dark background + one warm accent, or the reverse).
- Empty colored boxes and "photo coming soon" placeholders never ship. With no photo, remove that area or turn it into a type or motion scene.
- Without photos, in order: a type-led hero (business name or one real fact, 56-120px with `clamp`) → information as image (capacity, hours, price list, distances as well-set tables) → a very light texture (SVG `feTurbulence` grain). Never gradient blobs.

## 5. A different skeleton for every site
"Heading left + paragraph right + row of cards" should not be every site. Each site takes a different skeleton from this list:

| Skeleton | Essence |
| --- | --- |
| Cinematic full-screen | Full-screen scenes, pinned image sequence, horizontal gallery |
| Magazine collage | Asymmetric photos, huge headline, columned text, cover-page feel |
| Split screen | Fixed image on the left, scrolling content on the right; the image changes per section |
| Catalog / menu | The service list is the backbone; hovering a row reveals an image |
| Datasheet / document | The language of forms, tables and rulers |
| Bold grid | Heavy type, color blocks, counters |
| Minimal breathing room | Lots of space, one large image, slow transitions |
| Night theme | Dark background, the venue's own light |

Keep it calm: colored blocks never sit glued together (≥ 24px between cards, 88-160px between sections). Strong colors appear in 1-2 places on the page. The same information (hours, phone) appears at most once plus the footer. No decorative giant text band that carries no real information.

## 6. Pre-delivery check (10 points)
| # | Check | How |
| --- | --- | --- |
| 1 | Nothing from the ban list | The command below returns 0; then check by eye |
| 2 | "Would this fit another business?" test | Remove the logo and name: can you still tell which business it is? |
| 3 | Every claim is real | Numbers, certificates, ratings, reviews: no source, delete it |
| 4 | Local characters and spelling | Special characters render correctly; headings in sentence case |
| 5 | Mobile at 375px | No horizontal scroll, one action in the bottom bar |
| 6 | Contrast | Body ≥ 4.5:1, large text ≥ 3:1 |
| 7 | The action works | `tel:`, `https://wa.me/...` and map links are tappable |
| 8 | Max 2 font families, 2 radii, 1 accent color | Count them in the CSS |
| 9 | Reduced motion | A `prefers-reduced-motion` block exists; the page works without motion |
| 10 | Meta and weight | `title`, `description`, favicon; file < 150 KB excluding images |

Command for point 1:
```bash
grep -cE "radial-gradient|family=(Inter|Poppins|Montserrat|Fraunces|Cormorant)" index.html
```

## Credits
These rules come from lessons learned building demo sites for small businesses in Turkey. The design language draws on these open-source projects: [impeccable](https://github.com/pbakaus/impeccable), [taste-skill](https://github.com/Leonxlnx/taste-skill), [hallmark](https://github.com/Nutlope/hallmark), [Open Props](https://github.com/argyleink/open-props).
