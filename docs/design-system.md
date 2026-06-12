# Design System

Tokens from the [InFrame Design System Figma file](https://www.figma.com/design/IIllznqxWUCWcbCDblzqkL/InFrame-Design-System), with notes on how the landing page (`index.html`) implements them today.

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

All landing colors are defined as CSS custom properties on `:root`. See [figma-html-alignment.md](./figma-html-alignment.md) for how these relate to Figma tokens.

| Token | Hex | Role |
|-------|-----|------|
| `--slate-05` | `#222F3E` | Primary dark background, button text on amber |
| `--slate-04` | `#37485A` | — (defined, lightly used) |
| `--slate-03` | `#526477` | Body copy on light sections, licensed line |
| `--slate-02` | `#8394A5` | Eyebrows, form labels, footer text |
| `--steel` | `#C9CFE1` | Mark fills, muted accents |
| `--steel-02` | `#E1E5F0` | — (defined, lightly used) |
| `--steel-01` | `#F4F6FB` | Input focus background, gallery frame fallback |
| `--on-slate` | `#F4F6FB` | Primary text on dark backgrounds |
| `--amber` | `#EFB921` | Primary accent, CTAs, focus states, emphasis |
| `--amber-02` | `#F5CA52` | Button hover, form success message |
| `--white` | `#FFFFFF` | Light section backgrounds |

### Section backgrounds (page rhythm)

The page alternates **dark** and **light** sections for visual pacing:

| Section | Background | Text |
|---------|------------|------|
| Body default | `--slate-05` | `--on-slate` |
| Hero overlay base | `--slate-05` at 20% + bottom gradient | `--on-slate` |
| Why InFrame | `--slate-05` | `--on-slate` |
| What we handle (`.work`) | `--white` | `--slate-05` / `--slate-03` |
| Coverage & access (`.markets`) | `--slate-05` | `--on-slate` |
| Scroll gallery (`.gallery-scroll`) | `--slate-05` + `assets/image-steel-texture.png` | — |
| Contact | `--white` | `--slate-05` / `--slate-03` |
| Footer | `#19232c` | `--slate-02` |

### Borders and dividers

Section separators use `1px solid rgba(131, 148, 165, 0.12)` — effectively `--slate-02` at low opacity.

Grid gutters (capabilities, coverage lines) use `1px` with `rgba(131, 148, 165, 0.16–0.42)` depending on context.

## Typography

**Font family:** [Manrope](https://fonts.google.com/specimen/Manrope) (weights 300–700 loaded; body uses 400).

| Element | Size | Weight | Letter-spacing | Line-height | Notes |
|---------|------|--------|----------------|-------------|-------|
| `.eyebrow` | 11.5px | 600 | 0.26em | — | Uppercase, `--slate-02` |
| `h1.headline` | clamp(38px, 6.4vw, 76px) | 600 | -0.022em | 1.04 | max-width ~14ch |
| `.subline` | clamp(18px, 2vw, 22px) | 400 | — | 1.4 | max-width tied to headline |
| `.why-statement` | clamp(24px, 3.2vw, 36px) | 500 | -0.014em | 1.28 | max-width ~24ch |
| Section `h2` | clamp(22–28px, 2.6–3.4vw, 30–40px) | 600 | -0.012 to -0.014em | 1.08–1.2 | Varies by section |
| `.cap h3` | 19px | 600 | -0.01em | 1.25 | Dark text on light section |
| `.cap p`, `.markets-sub`, `.contact .note` | 14.5–15.5px | 400 | — | 1.6–1.62 | `--slate-03` on light; inherited on dark |
| `.cap .n` | 11.5px | 700 | 0.2em | — | Amber, numbered |
| `.lines li` | 12.5px | 600 | 0.09em | — | Uppercase on dark |
| `.btn` | 14.5px | 700 | — | — | Amber fill |
| `.ghost`, `.nav-cta` | 13–13.5px | 600 | 0.02–0.04em | — | Text links |
| Form labels | 11.5px | 600 | 0.14em | — | Uppercase, `--slate-02` |
| Form inputs | 15px | 400 (inherit) | — | — | `--slate-05` on white |
| Footer legal | 12px | 400 / 600 strong | — | 1.8 | — |

### Typographic patterns

- **Tight display headings** — negative letter-spacing on large headlines and section titles.
- **Constrained line lengths** — headlines and statements use `max-width` in `ch` units for editorial rhythm.
- **Emphasis without italics** — `.why-statement em` uses `font-style: normal` and `--amber` color.

## Layout

| Token | Value |
|-------|-------|
| `--maxw` | `1180px` |
| `.wrap` padding | `40px` horizontal (desktop), `24px` (≤640px) |

### Page structure

```
header.topbar (fixed)
.hero-scroll-zone
  section.hero (sticky, 100svh)
  main.scroll-content (scrolls over hero)
    section.why
    section.work
    section.markets
    section.gallery-scroll
    section.contact
    footer
```

The hero stays pinned while content scrolls over it. `.scroll-content` carries an upward shadow for depth.

### Section vertical rhythm

| Section | Padding (top / bottom) |
|---------|------------------------|
| Hero | min-height `100svh`, bottom `78px` |
| Why | `120px` / `116px` |
| Work | `108px` / `120px` |
| Markets | `108px` / `108px` |
| Gallery | Tall scroll section (see below) |
| Contact | `118px` / `104px` |
| Footer | `50px` / `44px` |

### Grids

| Grid | Columns | Breakpoint |
|------|---------|------------|
| `.grid3` (capabilities) | 3 → 1 | ≤820px |
| `.lines` (coverage) | 4 → 2 | ≤760px |
| `.contact-grid` | 2 → 1 | ≤860px |

### Header

- **Position:** fixed, `z-index: 50`, `30px` vertical padding (unchanged when scrolled).
- **Default (over hero):** wordmark 28px, Contact as text link.
- **Scrolled (`.is-scrolled`, past hero):** slate fill slides in; wordmark → condensed mark at **45×45px**; Contact → amber button (`min-height: 45px`, `padding: 0 24px`).

## Components (visual treatment)

### Primary button (`.btn`)

- Background: `--amber`, text: `--slate-05`
- Padding: `16px 30px`
- Icon gap: `12px` (15×15px arrow SVG)
- Hover: `--amber-02`, `translateY(-2px)`, amber glow shadow

### Ghost / text link (`.ghost`, `.nav-cta`)

- Default: inherited color, no underline
- Scrolled header Contact (`.nav-cta`): becomes primary button styling

### Form fields (Contact section)

- Background: `--white`
- Border: `1px solid rgba(131, 148, 165, 0.42)`
- Focus: amber border, `--steel-01` background
- Field stack gap: `16px`

### Capability cards (`.cap`)

- White background on light section
- SVG rect stroke (`.cap-edge`) draws in on scroll; body content fades up after
- Padding: `36px 34px 40px`

## Imagery & atmosphere

### Hero (`.hero-photo`)

Brand photography: `assets/hero-images/hero_01.jpeg` (cover, centered).

Layer stack (bottom to top):

1. `.hero-photo` — photography
2. `.hero-overlay` — `--slate-05` at 20% opacity
3. `.hero-fade` — bottom-up black gradient for legibility

Photo treatment: slow Ken Burns drift animation (26s). Hero media also scales/translates slightly via `--hero-scroll` CSS variable as user scrolls.

### Why InFrame mark (`.why-mark`)

Inline SVG from `assets/inframe-mark-skewed.svg`. Decorative watermark at **6% opacity**, vertically centered, anchored at **72% from left**.

Animation on scroll into section (`.why-mark.in`):

1. I stem fades in (`.why-mark-i`)
2. Top serif bar scales X from join point (`.why-mark-bar-top`)
3. Bottom serif bar follows (`.why-mark-bar-bottom`)

### Scroll gallery

Four square images in `assets/site-images/`, clipped in a centered frame over steel texture background. Scroll progress drives vertical translation of `.gallery-strip`.

## Motion

| Token / class | Behavior |
|---------------|----------|
| `--ease` | `cubic-bezier(0.2, 0.7, 0.2, 1)` |
| `--hero-scroll` | 0–1, set by scroll JS; drives hero media scale and copy fade |
| `.stag` + `.d1–.d4` | Hero entrance: rise + staggered delays (0.1s–0.56s) |
| `.reveal` | Scroll reveal: opacity + 20px Y, 0.9s; IntersectionObserver at 12% threshold |
| `.why-mark` | Separate observer; I fade + bar scaleX sequence |
| `.cap-grid` | Stroke draw-in + staggered card body reveal |
| `.coverage-pack.reveal` | Link draw, merge pulse, box amber fill (via `.reveal.in`) |
| `.gallery-strip` | Scroll-linked `translateY` through pinned section |
| `header.topbar.is-scrolled` | Fill slide, logo swap, Contact → button |
| `.hero-photo` | Slow scale/translate drift |
| `prefers-reduced-motion` | Disables animations; gallery shows first slide only; header shows scrolled state styles without transitions |

## Accessibility notes (current)

- Hero decorative layers marked `aria-hidden="true"`
- Gallery section has `aria-label="Built environment photography"`
- Form has labels, `autocomplete`, and `role="status"` on message
- Logo home link has `aria-label`
- Smooth scroll and motion respect reduced-motion preference
- Verify contrast on light sections (`--slate-03` body on white) if adjusting colors

## Assets (`/assets/`)

| File | Usage |
|------|-------|
| `inframe-logo.svg` | Header wordmark |
| `inframe-logo-mark-condensed.svg` | Source for inline header mark SVG |
| `inframe-mark-skewed.svg` | Why section watermark (inline SVG in HTML) |
| `inframe-favicon.svg` | Favicon |
| `inframe-footer-logo-full-slate.svg` | Footer wordmark |
| `hero-images/hero_01.jpeg` | Hero background |
| `image-steel-texture.png` | Gallery section background |
| `site-images/*.png` | Gallery slides (4 images) |
