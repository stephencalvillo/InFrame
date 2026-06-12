# Figma ↔ HTML Alignment

How the Figma design system relates to the current landing page draft, and where they intentionally diverge.

## Shared foundations ✓

| Token | Figma | HTML (`index.html`) |
|-------|-------|---------------------|
| Font | Manrope | Manrope ✓ |
| Primary accent | `primary/200` `#EFB921` | `--amber` `#EFB921` ✓ |
| Accent hover | `Amber 04` `#F5CA52` | `--amber-02` `#F5CA52` ✓ |
| Dark surface | Slate `#222F3E` (palette row) | `--slate-05` `#222F3E` ✓ |
| Text on light | `Text Primary` `#222F3E` | Button text on amber ✓ |
| Section header size | 19px Bold | `.cap h3` 19px weight 600 (close) |
| Body size | 15px Regular | Form inputs 15px ✓ |

## Intentional or unresolved differences

### 1. Theme mode

| | Figma components | Landing page |
|---|------------------|--------------|
| Surfaces | White `#FDFEFF` | **Alternating** dark (`--slate-05`) and light (`--white`) sections |
| Form fields | White bg, `#E1E5F0` border | White bg on Contact section — **now aligned** |
| Focus ring | 2px `#37485A` (slate) | 1px amber border + `--steel-01` fill |

**Recommendation:** Treat Figma as source for the **product/app UI**. The landing page uses a **marketing rhythm** — dark editorial sections (Why, Coverage, Gallery) alternate with light sections (What we handle, Contact). Document new sections against this pattern rather than defaulting to all-dark.

### 2. Button shape

| | Figma Primary (small) | Landing `.btn` |
|---|----------------------|----------------|
| Border radius | 4px (`--xsmall`) | 0 (sharp corners) |
| Border | 1.67px `#FDDc80` (amber-03) | None |
| Shadow | Drop shadow `0 1px 0.5px rgba(0,0,0,0.29)` | Hover glow only |
| Padding | 16px × 8px | 16px × 30px |
| Type | Label 15 Semibold (600) | 14.5px weight 700 |
| Primary fill | `#F5CA52` (amber-04) in dev inspect | `#EFB921` base |

The landing CTA is **editorial/sharp**; Figma buttons are **app-style/rounded**. Decide which wins before global sync.

### 3. Button variants

Figma defines **Primary, Secondary, Tertiary** × **small (36px) / large (48px)** with Base, Hover, Press, and icon front/back.

Landing page uses:
- `.btn` → closest to **Primary large** (but styled differently)
- `.ghost` → closest to **Tertiary** (text link, no button chrome)
- No **Secondary** (outlined) on landing

### 4. Typography scale

| Figma style | Spec | Landing equivalent |
|-------------|------|-------------------|
| Hero Large 48 | 48px / 600 / 100% LH | `h1.headline` clamp 38–76px (responsive, not fixed 48) |
| Page header 25 | 25px / 600 | Section h2s use clamp 22–40px |
| Section header 19 | 19px / 700 | `.cap h3` 19px / 600 |
| Label 15 | 15px / 600 | Buttons, form labels (landing labels are 11.5px uppercase — **not in Figma**) |
| Body Regular 15 | 15px / 400 | Body copy 14.5–15.5px |
| Legal 13 | 13px / 400 | Footer 12px (slightly smaller) |

**Eyebrow** (11.5px, 0.26em tracking, uppercase) exists only on the landing page — consider adding to Figma as **Eyebrow 11.5** if it becomes a pattern.

### 5. Spacing tokens (Figma)

| Token | Value | Used in components |
|-------|-------|-------------------|
| `--xsmall` | 4px | Border radius, field stack gap |
| `--small` | 8px | Button/input padding-y, icon gap |
| `--medium` | 16px | Button/input padding-x |

Landing page uses ad-hoc spacing (26px, 44px, 64px section gaps) — not yet tokenized in Figma.

### 6. Color naming

Figma Design System file uses:
- **primary/** scale (amber, 100–700)
- **grey/** scale (neutral, 100–700)
- **Slate row** in palette: `#577393` → `#0B1119` (second row, mislabeled "primary" in layer names)

HTML uses **slate-** and **steel-** names from the draft, which map loosely to the slate row + grey scale but aren't 1:1.

Suggested canonical mapping:

| HTML var | Figma equivalent |
|----------|------------------|
| `--slate-05` | Slate 600 `#222F3E` |
| `--slate-04` | Slate 500 `#3C5067` |
| `--slate-03` | Slate 400 `#577393` or grey/500 |
| `--slate-02` | grey/300 `#A6A8AE` |
| `--steel` | grey/200 `#CECFD2` |
| `--steel-02` | Border default `#E1E5F0` |
| `--amber` | primary/200 `#EFB921` |
| `--amber-02` | Amber 04 `#F5CA52` |

## Form components on landing

Contact form is now a simplified subset of Figma **Text input / large + Label** on a light surface:

| Figma | Landing today |
|-------|---------------|
| White surface input | White bg ✓ |
| Border default `#E1E5F0` | `rgba(131,148,165,.42)` (close) |
| Label 15 sentence case | 11.5px uppercase label (marketing pattern) |
| Optional description | Not used |
| Optional icon | Not used |
| Focus: 2px slate border | Focus: 1px amber border |

Dropdown and Date picker exist in Figma but aren't on the landing page.

## Recommended next steps

1. **Document marketing theme in Figma** — dark/light section rhythm, eyebrow pattern, sharp-corner CTAs.
2. **Resolve button spec** — align landing CTAs to Figma Primary/large or document marketing override.
3. **Add Eyebrow to Figma** if it's a recurring marketing pattern.
4. **Tokenize landing spacing** or accept marketing-specific layout values.
5. **Update CSS vars** to use Figma names when ready to sync.
