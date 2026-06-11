# Design System

Tokens from the [InFrame Design System Figma file](https://www.figma.com/design/IIllznqxWUCWcbCDblzqkL/InFrame-Design-System), with notes on how the landing page draft (`index.html`) implements them today.

## Figma color tokens (canonical)

### Primary (amber)

| Token | Hex |
|-------|-----|
| primary/100 | `#FEE5C1` |
| primary/200 | `#EFB921` |
| primary/300 | `#C09418` |
| primary/400 | `#937010` |
| primary/500 | `#684F08` |
| primary/600 | `#403003` |
| primary/700 | `#1C1301` |

### Slate (brand darks — second palette row in Figma)

| Token | Hex |
|-------|-----|
| slate/400 | `#577393` |
| slate/500 | `#3C5067` |
| slate/600 | `#222F3E` |
| slate/700 | `#0B1119` |

### Grey (neutral)

| Token | Hex |
|-------|-----|
| grey/100 | `#F0F1F1` |
| grey/200 | `#CECFD2` |
| grey/300 | `#A6A8AE` |
| grey/400 | `#80828A` |
| grey/500 | `#5D5F64` |
| grey/600 | `#3C3D41` |
| grey/700 | `#1E1F21` |

### Component aliases (from InFrame Components)

| Token | Hex | Usage |
|-------|-----|-------|
| Text Primary | `#222F3E` | Default text on light surfaces |
| Surface Main | `#FDFEFF` | Input/button backgrounds |
| Border Default | `#E1E5F0` | Input borders, secondary buttons |
| Amber 03 | `#FDDC80` | Primary button border |
| Amber 04 | `#F5CA52` | Primary button fill (component default) |

## Figma typography (canonical)

| Style | Font | Size | Weight | Line height |
|-------|------|------|--------|-------------|
| Hero Large 48 | Manrope SemiBold | 48px | 600 | 100% |
| Page header 25 | Manrope SemiBold | 25px | 600 | 100% |
| Section header 19 | Manrope Bold | 19px | 700 | 100% |
| Label 15 | Manrope SemiBold | 15px | 600 | 100% |
| Body Regular 15 | Manrope Regular | 15px | 400 | 100% |
| Legal 13 | Manrope Regular | 13px | 400 | 100% |

## Figma spacing & radius

| Token | Value |
|-------|-------|
| xsmall | 4px (radius, tight gaps) |
| small | 8px |
| medium | 16px |

---

## Landing page CSS (current implementation)

All landing colors are defined as CSS custom properties on `:root`. These predate full Figma sync — see [figma-html-alignment.md](./figma-html-alignment.md).

| Token | Hex | Role |
|-------|-----|------|
| `--slate-05` | `#222F3E` | Primary background, button text on amber |
| `--slate-04` | `#37485A` | Footer legal text |
| `--slate-03` | `#526477` | Form labels, licensed line, footer links |
| `--slate-02` | `#8394A5` | Body secondary text, capability descriptions |
| `--steel` | `#C9CFE1` | Muted text, nav CTA, sublines, ghost links |
| `--steel-02` | `#E1E5F0` | — (defined, lightly used) |
| `--steel-01` | `#F4F6FB` | — (defined, lightly used) |
| `--amber` | `#EFB921` | Primary accent, CTAs, focus states, numbered labels |
| `--amber-02` | `#F5CA52` | Button hover, form success message |
| `--white` | `#FFFFFF` | Primary text on dark backgrounds |

### Section-specific backgrounds

| Section | Background |
|---------|------------|
| Body / default sections | `--slate-05` |
| Hero overlay base | `#1b2630` (gradient terminus) |
| Work (capabilities) | Linear gradient `#1f2a35` → `#222F3E` |
| Contact | `#1b2630` |
| Footer | `#19232c` |

### Borders and dividers

Section separators use `1px solid rgba(131, 148, 165, 0.12–0.14)` — effectively `--slate-02` at low opacity.

Grid gaps (capabilities, coverage lines) use `1px` gutters with `rgba(131, 148, 165, 0.16–0.18)` as the grid background color.

## Typography

**Font family:** [Manrope](https://fonts.google.com/specimen/Manrope) (weights 300–700 loaded; body uses 400).

| Element | Size | Weight | Letter-spacing | Line-height | Notes |
|---------|------|--------|----------------|-------------|-------|
| `.eyebrow` | 11.5px | 600 | 0.26em | — | Uppercase, `--slate-02` (hero: `--steel`) |
| `h1.headline` | clamp(38px, 6.4vw, 76px) | 600 | -0.022em | 1.04 | max-width ~14ch |
| `.subline` | clamp(18px, 2vw, 22px) | 400 | — | 1.4 | max-width ~30ch |
| `.why-statement` | clamp(24px, 3.2vw, 36px) | 500 | -0.014em | 1.28 | max-width ~24ch |
| Section `h2` | clamp(22–28px, 2.6–3.4vw, 30–40px) | 600 | -0.012 to -0.014em | 1.08–1.2 | Varies by section |
| `.cap h3` | 19px | 600 | -0.01em | 1.25 | — |
| `.cap p`, `.markets-sub` | 14.5–15.5px | 400 | — | 1.62 | `--slate-02` |
| `.cap .n` | 11.5px | 700 | 0.2em | — | Amber, numbered |
| `.lines li` | 12.5px | 600 | 0.09em | — | Uppercase, `--steel` |
| `.btn` | 14.5px | 700 | — | — | Amber fill |
| `.ghost`, `.nav-cta` | 13–13.5px | 600 | 0.02–0.04em | — | Text links |
| Form labels | 11.5px | 600 | 0.14em | — | Uppercase |
| Form inputs | 15px | 400 (inherit) | — | — | — |
| Footer legal | 12px | 400 / 600 strong | — | 1.8 | — |

### Typographic patterns

- **Tight display headings** — negative letter-spacing on large headlines and section titles.
- **Constrained line lengths** — headlines and statements use `max-width` in `ch` units for editorial rhythm.
- **Emphasis without italics** — `.why-statement em` uses `font-style: normal` and `--steel` color instead of italic.

## Layout

| Token | Value |
|-------|-------|
| `--maxw` | `1180px` |
| `.wrap` padding | `40px` horizontal (desktop), `24px` (≤640px) |

### Section vertical rhythm

| Section | Padding (top / bottom) |
|---------|------------------------|
| Hero | min-height `100svh`, bottom `78px` |
| Why | `120px` / `116px` |
| Work | `108px` / `120px` |
| Markets | `108px` / `108px` |
| Contact | `118px` / `104px` |
| Footer | `50px` / `44px` |

### Grids

| Grid | Columns | Breakpoint |
|------|---------|------------|
| `.grid3` (capabilities) | 3 → 1 | ≤820px |
| `.lines` (coverage) | 4 → 2 | ≤760px |
| `.contact-grid` | 2 → 1 | ≤860px |

### Header

- **Position:** absolute over hero, `z-index: 30`, `30px` vertical padding.
- **Logo height:** 28px (header), 24px (footer).

## Components (visual treatment)

### Primary button (`.btn`)

- Background: `--amber`, text: `--slate-05`
- Padding: `16px 30px`
- Icon gap: `12px` (15×15px arrow SVG)
- Hover: `--amber-02`, `translateY(-2px)`, amber glow shadow

### Ghost / text link (`.ghost`, `.nav-cta`)

- Color: `--steel` → `--white` on hover
- No underline by default

### Eyebrow with rule (hero only)

- Flex row with `15px` gap
- `34×1.5px` amber bar via `::before`

### Form fields

- Background: `rgba(255,255,255, 0.035)`
- Border: `1px solid rgba(131, 148, 165, 0.3)`
- Focus: amber border, slightly lighter background
- Field stack gap: `16px`

### Capability cards (`.cap`)

- Padding: `36px 34px 40px`
- Sit on `--slate-05` inside 1px grid gutter

## Imagery & atmosphere

### Hero (`.hero-photo`)

Placeholder procedural jobsite scene — **replace with brand photography** before launch.

Layer stack (bottom to top):

1. `.hero-photo` — photo/placeholder + dual gradient overlays for legibility
2. `.hero-beams` — decorative skewed beam silhouettes, 50% opacity, soft-light blend
3. `.hero-grain` — diagonal stripe texture, masked fade

Photo treatment: `saturate(0.92)`, slow Ken Burns drift animation (26s).

### Watermark (`.why .watermark`)

Icon mark at ~5% opacity, bottom-right, max ~440px width.

## Motion

| Token / class | Behavior |
|---------------|----------|
| `--ease` | `cubic-bezier(0.2, 0.7, 0.2, 1)` |
| `.stag` + `.d1–.d4` | Hero entrance: rise + staggered delays (0.1s–0.56s) |
| `.reveal` | Scroll reveal: opacity + 20px Y, 0.9s; triggered by IntersectionObserver at 16% threshold |
| `.hero-photo` | Slow scale/translate drift |
| `prefers-reduced-motion` | Disables animations and smooth scroll |

## Accessibility notes (current)

- Hero decorative layers marked `aria-hidden="true"`
- Form has labels, `autocomplete`, and `role="status"` on message
- Logo home link has `aria-label`
- Smooth scroll and motion respect reduced-motion preference
- Color contrast: white/steel on slate generally passes for large text; verify small uppercase labels if adjusting colors

## Assets (embedded)

Currently inline as base64 data URIs:

- Favicon / watermark icon
- Wordmark (header + footer)

**Recommendation:** Extract to `/assets/` for easier swaps and smaller HTML file size.
