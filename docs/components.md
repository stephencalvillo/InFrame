# Component Inventory

Catalog of UI building blocks on the landing page, cross-referenced with the [InFrame Components Figma file](https://www.figma.com/design/DzuotbQlniNQnwHvwormPw/InFrame-Components).

## Figma component library

| Component | Variants | Figma node |
|-----------|----------|------------|
| **Button** | Primary / Secondary / Tertiary × Small (36px) / Large (48px) × Base / Hover / Press; icon front or back | [`154:2873`](https://www.figma.com/design/DzuotbQlniNQnwHvwormPw/InFrame-Components?node-id=154-2873) |
| **Text input** | Small (36px) / Large (48px) × Base / Hover / Focus; optional label, description, icon | [`154:12382`](https://www.figma.com/design/DzuotbQlniNQnwHvwormPw/InFrame-Components?node-id=154-12382) |
| **Dropdown** | Same size/state matrix as text input | [`155:13048`](https://www.figma.com/design/DzuotbQlniNQnwHvwormPw/InFrame-Components?node-id=155-13048) |
| **Date picker** | Same size/state matrix as text input | [`155:13329`](https://www.figma.com/design/DzuotbQlniNQnwHvwormPw/InFrame-Components?node-id=155-13329) |

### Figma button specs (Primary / small)

- Fill: `#F5CA52` (Amber 04), border: `#FDDC80` (Amber 03)
- Radius: 4px, padding: 16×8px, gap: 8px
- Type: Label 15 (15px Semibold), text `#222F3E`
- Shadow: `0 1px 0.5px rgba(0,0,0,0.29)`

### Figma text input specs (Small / Base)

- Surface: `#FDFEFF`, border: 1px `#E1E5F0`
- Radius: 4px, padding: 8px
- Type: Body Regular 15
- Focus: 2px border `#37485A`

---

## Landing page components

## Global

### `.wrap`

Content container. Max-width 1180px, centered, horizontal padding 40px (24px mobile).

### `.eyebrow`

Section label. Uppercase, tracked, small caps feel. Color varies by context (hero: steel; elsewhere: slate-02).

---

## Header — `.topbar`

| Part | Class | Notes |
|------|-------|-------|
| Container | `header.topbar` | Absolute, overlays hero |
| Logo link | `a[aria-label="InFrame home"]` | Wordmark 28px height, drop shadow |
| Nav CTA | `.nav-cta` | "Contact" → `#contact` |

**Variants:** None in current draft (no mobile menu, no additional nav links).

---

## Hero — `.hero`

| Part | Class | Notes |
|------|-------|-------|
| Media stack | `.hero-media` | Decorative, aria-hidden |
| Photo layer | `.hero-photo` | Replace with brand image |
| Beams | `.hero-beams` | CSS-only depth |
| Grain | `.hero-grain` | Texture overlay |
| Headline | `h1.headline` | Stagger animate `.stag.d1` |
| Subline | `.subline` | `.stag.d2` |
| CTA row | `.cta-row` | `.stag.d3` |
| Primary CTA | `.btn` | "Speak with our team" |
| Secondary | `.ghost` | "Why InFrame" → `#why` |

**Hero eyebrow:** Defined in CSS but not used in current markup (headline opens the section).

---

## Why — `.why`

| Part | Class | Notes |
|------|-------|-------|
| Watermark | `.watermark` | Icon, low opacity, decorative |
| Eyebrow | `.eyebrow.reveal` | "Why InFrame" |
| Statement | `.why-statement.reveal` | Two-tone: steel `<em>` + white main text |

---

## Capabilities — `.work`

| Part | Class | Notes |
|------|-------|-------|
| Section | `.work#work` | Subtle gradient background |
| Header row | `.head` | Eyebrow + h2 side by side on wide screens |
| Grid | `.grid3` | 3 equal columns, 1px gutters |
| Card | `.cap` | Number + title + body |
| Number | `.n` | "01", "02", "03" in amber |

---

## Coverage & markets — `.markets`

| Part | Class | Notes |
|------|-------|-------|
| Header block | `.markets-head` | Eyebrow, h2, subline |
| Line grid | `.lines` | 4-column uppercase cells |
| Highlight cell | `.lines li.more` | Amber "& more" |

**Listed lines:** Property, General Liability, Commercial Auto, Workers' Comp, Professional Liability, Inland Marine, Cyber, Excess & Umbrella.

---

## Contact — `.contact`

| Part | Class | Notes |
|------|-------|-------|
| Grid | `.contact-grid` | Copy column + form column |
| Headline | `h2` | "Get in touch." |
| Notes | `.note` | Intro + email link |
| License line | `.licensed` | Entity + license descriptor |
| Form | `#contactForm` | Name, Company, Work email |
| Field group | `.field` | Label + input |
| Submit | `.btn` | "Request a conversation" |
| Feedback | `#formMsg.form-msg` | Inline status |

**Form behavior:** Client-side only — validates required fields, shows thank-you message, resets form. Not wired to backend.

**Email link:** `contact@inframerisk.com`

---

## Footer — `footer`

| Part | Class | Notes |
|------|-------|-------|
| Top row | `.foot-top` | Logo + links |
| Wordmark | `img.word` | 24px height |
| Links | `.foot-links` | Privacy, Terms, Licenses (placeholder `#`) |
| Legal | `.legal` | Compliance disclaimer with placeholders |
| Copyright | `.copyright` | © 2026 InFrame Risk Inc. |

---

## Buttons & links

### Primary button — `.btn`

Used for: hero CTA, form submit.

Structure: text + inline SVG arrow (15×15, stroke 2.2).

### Ghost link — `.ghost`

Used for: hero secondary nav.

### Text nav — `.nav-cta`

Used for: header Contact.

---

## Motion classes

| Class | Use |
|-------|-----|
| `.stag` + `.d1`–`.d4` | Hero load sequence |
| `.reveal` | Scroll-triggered section entrance |
| `.in` | Applied by JS when element enters viewport |

---

## JavaScript dependencies

1. **IntersectionObserver** — adds `.in` to `.reveal` elements (fallback: show all immediately).
2. **Form handler** — preventDefault, trim validation, success message.

No external JS libraries.
