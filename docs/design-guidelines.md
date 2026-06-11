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
| Use amber for primary actions and numbered accents | Add extra accent colors (blue links, green success, etc.) |
| Keep backgrounds in the slate family with subtle gradient shifts between sections | Introduce white or light-mode sections mid-page |
| Use `--steel` / `--slate-02` for supporting copy | Use pure gray `#999` or off-palette neutrals |

Amber should **draw the eye to action** — one primary CTA per viewport when possible.

### Typography

| Do | Don't |
|----|-------|
| Keep Manrope across all text | Mix in secondary display fonts without strong reason |
| Use eyebrows to label sections | Replace eyebrows with decorative icons |
| Constrain headline width (`max-width` in `ch`) | Let hero headlines span full container width |
| Use weight 600 for headings, 400–500 for body | Default to bold (700) for paragraph text |

### Photography & hero

The hero is the emotional anchor. When replacing the placeholder:

- Prefer **editorial jobsite / built-environment** imagery
- Maintain the **dual gradient overlay** for text legibility
- Keep overlays warm-slate, not pure black
- Avoid stock photos with obvious handshakes, headsets, or generic office scenes

Beam silhouettes and grain are optional atmosphere — they should complement, not compete with, real photography.

## Layout principles

1. **Single-column narrative** — sections stack vertically; no sidebar or multi-page nav on this draft.
2. **Full-bleed hero, contained content** — hero media edge-to-edge; text lives in `.wrap` at 1180px max.
3. **1px grid gutters** — capabilities and coverage lists use hairline dividers, not card shadows or rounded boxes.
4. **Generous section padding** — ~108–120px vertical; don't compress sections below ~80px without reason.
5. **Mobile-first breakpoints** — grids collapse at 760–860px; reduce horizontal padding at 640px.

## Content patterns

### Section structure

Most sections follow:

```
Eyebrow (label)
Headline or statement
Supporting copy (optional)
Content block (grid, list, or form)
```

### Capability cards

Framed around **the reader's moment** — "When X happens" — not feature lists. Keep three cards for balance; if adding a fourth, reconsider grid (2×2 vs 4-column).

### Coverage lines

Uppercase, compact grid cells. The last cell (`& more`) uses amber to signal extensibility without listing everything.

## Interaction

| Pattern | Guideline |
|---------|-----------|
| Primary CTA | Amber button with arrow; links to `#contact` |
| Secondary action | Ghost text link; no button styling |
| Hover | Subtle color shift or 2px lift on buttons — no aggressive scale |
| Scroll | Smooth scroll to anchors; section reveals on enter |
| Form | Inline validation message only (no modal); success copy uses first name |

## Voice & copy checklist

When editing copy, check:

- [ ] Speaks to **operations and exposure**, not abstract "risk solutions"
- [ ] Uses **specific scenarios** (contracts, loans, hard markets, claims)
- [ ] Avoids unverifiable superlatives unless substantiated
- [ ] Legal/compliance claims reviewed (see [open-items.md](./open-items.md))

## What to preserve unless asked otherwise

These are core to the draft the client likes:

- Dark-only palette with amber accent
- Full-viewport hero with bottom-aligned content
- Three-column capability grid with numbered amber labels
- Coverage grid with uppercase line names
- Two-column contact (copy left, form right)
- Minimal top nav (logo + Contact only)

## Extension guidance

If adding new sections, match:

- Same `.wrap` container and section padding band (~108–120px)
- Same eyebrow + headline pattern
- Same border-top separator between major sections
- Same reveal animation class (`.reveal`) for scroll entrance

If the site grows beyond one page, consider extracting tokens to a shared CSS file before duplicating styles.
