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

Section label. Uppercase, tracked, small caps feel. Color: `--slate-02` (works on both light and dark sections).

---

## Header — `.topbar`

| Part | Class | Notes |
|------|-------|-------|
| Container | `header.topbar` | Fixed, `z-index: 50`, 30px vertical padding |
| Background fill | `.topbar-fill` | Slate bar; hidden above hero, slides in when scrolled |
| Logo link | `.logo-link` | Contains wordmark + mark; height 28px → 45px when scrolled |
| Wordmark | `.logo-word` | `assets/inframe-logo.svg`, 28px height |
| Condensed mark | `.logo-mark` | Inline SVG; slides in from right when scrolled |
| Mark animation | `.logo-mark-inner` | `translateX` clip reveal |
| Nav CTA | `.nav-cta` | "Contact" → `#contact` |
| Scrolled state | `.is-scrolled` | Applied when scroll passes hero height |

**Scrolled behavior:**

- Wordmark fades out; condensed mark appears at 45×45px
- Contact becomes amber primary button (`min-height: 45px`, `padding: 0 24px`)

**Variants:** None (no mobile menu, no additional nav links).

---

## Hero — `.hero`

| Part | Class | Notes |
|------|-------|-------|
| Scroll zone | `.hero-scroll-zone` | Bounds sticky hero |
| Section | `.hero#top` | Sticky, 100svh, content bottom-aligned |
| Media stack | `.hero-media` | Scales on scroll via `--hero-scroll` |
| Photo layer | `.hero-photo` | `assets/hero-images/hero_01.jpeg` |
| Overlay | `.hero-overlay` | Slate at 20% |
| Fade | `.hero-fade` | Bottom gradient for legibility |
| Headline | `h1.headline` | Stagger animate `.stag.d1` |
| Subline | `.subline` | `.stag.d2` |
| CTA row | `.cta-row` | `.stag.d3` |
| Primary CTA | `.btn` | "Speak with our team" |
| Secondary | `.ghost` | "Why InFrame" → `#why` |
| Content deck | `.scroll-content` | Main sections scroll over hero |

Copy fades and translates up as user scrolls (`--hero-scroll`).

---

## Why — `.why`

| Part | Class | Notes |
|------|-------|-------|
| Mark | `.why-mark` | Inline SVG from skewed mark asset; 6% opacity |
| I stem | `.why-mark-i` | Fades in first |
| Serif bars | `.why-mark-bar-top`, `.why-mark-bar-bottom` | ScaleX grow from I join point |
| Trigger | `.why-mark.in` | Separate IntersectionObserver |
| Eyebrow | `.eyebrow.reveal` | "Why InFrame" |
| Statement | `.why-statement.reveal` | Amber `<em>` emphasis + white main text |

---

## Capabilities — `.work`

| Part | Class | Notes |
|------|-------|-------|
| Section | `.work#work` | White background |
| Header row | `.head` | Eyebrow + h2 side by side on wide screens |
| Grid | `.grid3.cap-grid` | 3 equal columns, 1px stroke borders |
| Card | `.cap` | Number + title + body |
| Border stroke | `.cap-stroke` / `.cap-edge` | SVG rect; draws in on scroll |
| Card body | `.cap-body` | Content fades up after stroke |
| Number | `.n` | "01", "02", "03" in amber |

Grid gets `.in` class from dedicated IntersectionObserver (also triggers ResizeObserver layout for strokes).

---

## Coverage & markets — `.markets`

| Part | Class | Notes |
|------|-------|-------|
| Section | `.markets#coverage` | Dark slate background |
| Header block | `.markets-head` | Eyebrow, h2, subline |
| Pack diagram | `.coverage-pack.reveal` | Property / Casualty / Specialty nodes |
| Link lines | `.pack-link`, `.pack-link-glow` | Animated stroke draw |
| Merge node | `.pack-merge` | Center convergence point |
| Node boxes | `.pack-box` | Fill amber on animation complete |
| Line grid | `.lines` | 4-column uppercase cells |
| Highlight cell | `.lines li.more` | Amber "& more" |

**Listed lines:** Property, General Liability, Commercial Auto, Workers' Comp, Professional Liability, Inland Marine, Cyber, Excess & Umbrella.

---

## Scroll gallery — `.gallery-scroll`

| Part | Class | Notes |
|------|-------|-------|
| Section | `.gallery-scroll#gallery` | Tall scroll section; steel texture bg |
| Sticky viewport | `.gallery-sticky` | Pins frame while scrolling |
| Frame | `.gallery-frame` | Square clip container |
| Strip | `.gallery-strip` | Vertical stack; `translateY` on scroll |
| Slides | `.gallery-slide` | 4 images from `assets/site-images/` |

**Images:** jobsite, corporate building (×2), solar installation.

**Reduced motion:** Shows first slide only; no scroll-linked movement.

---

## Contact — `.contact`

| Part | Class | Notes |
|------|-------|-------|
| Section | `.contact#contact` | White background (matches `.work`) |
| Grid | `.contact-grid` | Copy column + form column |
| Headline | `h2` | "Get in touch." |
| Notes | `.note` | Intro + email link |
| License line | `.licensed` | Entity + license descriptor |
| Form | `#contactForm` | Name, Company, Work email |
| Field group | `.field` | Uppercase label + input |
| Submit | `.btn` | "Request a conversation" |
| Feedback | `#formMsg.form-msg` | Inline status |

**Form styling:** White inputs, slate borders, amber focus — aligned with Figma light surfaces.

**Form behavior:** Client-side only — validates required fields, shows thank-you message, resets form. Not wired to backend.

**Email link:** `contact@inframerisk.com`

---

## Footer — `footer`

| Part | Class | Notes |
|------|-------|-------|
| Top row | `.foot-top` | Logo + links |
| Wordmark | `img.word` | `assets/inframe-footer-logo-full-slate.svg`, 24px height |
| Links | `.foot-links` | Privacy, Terms, Licenses (placeholder `#`) |
| Legal | `.legal` | Compliance disclaimer with placeholders |
| Copyright | `.copyright` | © 2026 InFrame Risk Inc. |

---

## Buttons & links

### Primary button — `.btn`

Used for: hero CTA, form submit, scrolled header Contact.

Structure: text + inline SVG arrow (15×15, stroke 2.2).

### Ghost link — `.ghost`

Used for: hero secondary nav.

### Text nav — `.nav-cta`

Used for: header Contact (default state). Becomes `.btn`-like when header is scrolled.

---

## Motion classes

| Class | Use |
|-------|-----|
| `.stag` + `.d1`–`.d4` | Hero load sequence |
| `.reveal` | Scroll-triggered section entrance |
| `.in` | Applied by JS when element enters viewport |
| `.why-mark.in` | Watermark animation trigger |
| `.cap-grid.in` | Capability stroke + content sequence |
| `.is-scrolled` | Header state after hero |

---

## JavaScript dependencies

1. **Hero scroll handler** — sets `--hero-scroll`, toggles `.is-scrolled` on header.
2. **Gallery scroll handler** — translates `.gallery-strip` based on section scroll progress.
3. **IntersectionObserver (`.reveal`)** — adds `.in` to reveal elements.
4. **IntersectionObserver (`.why-mark`)** — triggers watermark animation.
5. **IntersectionObserver + ResizeObserver (`.cap-grid`)** — layout SVG strokes, trigger card animation.
6. **Form handler** — preventDefault, trim validation, success message.

No external JS libraries.
