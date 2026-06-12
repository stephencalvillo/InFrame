# Design Guidelines

How the InFrame landing page should look, read, and behave when you make changes.

## Brand positioning

InFrame speaks to **operators** — businesses with physical exposure, contracts, and real insurance needs — not generic "business owners." The tone is:

- **Confident, not loud** — specialist credibility over sales hype
- **Direct** — short sentences, concrete scenarios ("when requirements drive coverage")
- **Contrast-driven** — the Why section explicitly positions against large brokers reserving specialists for biggest accounts

Avoid consumer-insurance language, cartoon mascots, or overly friendly startup casualness.

## Visual identity

### Mood

**Industrial editorial** — dark slate palette, steel secondary tones, amber as the sole warm accent. Think built environment, structural beams, jobsite photography — not glossy fintech or generic corporate blue.

### Color usage

| Do | Don't |
|----|-------|
| Use amber for primary actions, numbered accents, and key emphasis | Add extra accent colors (blue links, green success, etc.) |
| Alternate dark and light sections for rhythm (see below) | Randomly mix surfaces without intentional contrast |
| Use `--slate-03` / `--slate-02` for supporting copy on light sections | Use pure gray `#999` or off-palette neutrals |

Amber should **draw the eye to action** — one primary CTA per viewport when possible.

### Section rhythm (dark ↔ light)

The page follows an intentional alternation:

```
Hero (dark) → Why (dark) → What we handle (light) → Coverage (dark) → Gallery (dark) → Contact (light) → Footer (dark)
```

Light sections (`.work`, `.contact`) use `--white` backgrounds with `--slate-05` headings and `--slate-03` body copy. Dark sections use `--slate-05` with `--on-slate` text. New sections should continue this pattern rather than stacking multiple dark or light blocks without reason.

### Typography

| Do | Don't |
|----|-------|
| Keep Manrope across all text | Mix in secondary display fonts without strong reason |
| Use eyebrows to label sections | Replace eyebrows with decorative icons |
| Constrain headline width (`max-width` in `ch`) | Let hero headlines span full container width |
| Use weight 600 for headings, 400–500 for body | Default to bold (700) for paragraph text |

### Photography & hero

The hero is the emotional anchor:

- Prefer **editorial jobsite / built-environment** imagery
- Maintain **overlay + bottom gradient** for text legibility
- Keep overlays warm-slate, not pure black
- Avoid stock photos with obvious handshakes, headsets, or generic office scenes

Current hero uses `assets/hero-images/hero_01.jpeg`. Swap for final brand-approved photography when ready.

## Layout principles

1. **Single-column narrative** — sections stack vertically; no sidebar or multi-page nav on this draft.
2. **Sticky hero, scrolling deck** — hero pins while `.scroll-content` slides over it; content sections live inside the deck.
3. **Full-bleed hero, contained content** — hero media edge-to-edge; text lives in `.wrap` at 1180px max.
4. **1px grid gutters** — capabilities and coverage lists use hairline dividers, not card shadows or rounded boxes.
5. **Generous section padding** — ~108–120px vertical; don't compress sections below ~80px without reason.
6. **Mobile-first breakpoints** — grids collapse at 760–860px; reduce horizontal padding at 640px.

## Content patterns

### Section structure

Most sections follow:

```
Eyebrow (label)
Headline or statement
Supporting copy (optional)
Content block (grid, list, form, or gallery)
```

### Capability cards

Framed around **the reader's moment** — "When X happens" — not feature lists. Keep three cards for balance; if adding a fourth, reconsider grid (2×2 vs 4-column).

Cards animate in with a drawn border stroke, then content fade-up — preserve this sequence when editing.

### Coverage lines

Uppercase, compact grid cells. The last cell (`& more`) uses amber to signal extensibility without listing everything.

### Scroll gallery

Full-width dark section with steel texture. Images advance on scroll inside a centered square frame. No copy in this section — photography only. Use built-environment imagery consistent with the hero.

## Interaction

| Pattern | Guideline |
|---------|-----------|
| Primary CTA | Amber button with arrow; links to `#contact` |
| Secondary action | Ghost text link; no button styling |
| Header (scrolled) | Wordmark → condensed mark; Contact text → amber button |
| Hover | Subtle color shift or 2px lift on buttons — no aggressive scale |
| Scroll | Smooth scroll to anchors; section reveals on enter |
| Why mark | I appears, then serif bars grow outward — one-time on scroll |
| Form | Inline validation message only (no modal); success copy uses first name |

## Voice & copy checklist

When editing copy, check:

- [ ] Speaks to **operations and exposure**, not abstract "risk solutions"
- [ ] Uses **specific scenarios** (contracts, loans, hard markets, claims)
- [ ] Avoids unverifiable superlatives unless substantiated
- [ ] Legal/compliance claims reviewed (see [open-items.md](./open-items.md))

## What to preserve unless asked otherwise

These are core to the current draft:

- Dark/light section rhythm with amber accent
- Sticky full-viewport hero with scroll-over content deck
- Fixed header with scroll state (wordmark → mark, Contact → button)
- Three-column capability grid with numbered amber labels and stroke animation
- Coverage grid with uppercase line names and animated pack diagram
- Scroll-pinned photography gallery before Contact
- Two-column contact (copy left, form right) on white background
- Minimal top nav (logo + Contact only)
- Why InFrame animated mark watermark

## Extension guidance

If adding new sections, match:

- Same `.wrap` container and section padding band (~108–120px)
- Same eyebrow + headline pattern
- Same border-top separator between major sections
- Same reveal animation class (`.reveal`) for scroll entrance
- Continue the dark/light alternation from adjacent sections

If the site grows beyond one page, consider extracting tokens to a shared CSS file before duplicating styles.
