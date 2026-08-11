# Genyus School — Design System

A brand & UI system for **Genyus School**, distilled from the official *Manual de Marca* (BrandBook_Genyus), the brand font package, and the logo/asset kit.

> **Genyus School** is an innovative educational institution focused on training and developing skills in children, youth and adults — with a core emphasis on the **entrepreneurial spirit** and **social skills**. It uses methodologies that blend **emotion and fun** to create a unique, engaging learning experience, and is a key component of the *Movimiento Future Minds*.

Genyus is one brand with **three verticals**, each with its own primary palette:

- **Genyus School** — kids & youth (master brand). Blue / pink / orange / yellow.
- **Genyus Business** — professional / adult programs. Green / cyan / blue / purple.
- **Genyus University** — higher-level programs. Pink / purple / indigo.

**Brand archetype:** *Bufón (Jester) + Creador (Creator)* — spontaneous, creative, original, irreverent, joyful. Learning as play.

---

## Sources given

- `uploads/BrandBook_Genyus (9).pdf` — 37-page brand manual (strategy, logos, color, type, iconography, photography, graphics). Copied to `uploads/brandbook.pdf` for parsing.
- `uploads/Genyus School-…zip` — logo kit (SVG/PNG/EPS/AI/GIF), color & gradient lockups. Key assets extracted to `assets/logos/`.
- `uploads/Fuentes-…zip` — brand fonts: **Helotypo**, **Nobel Uno** (full weight family), **Anton**. Extracted to `assets/fonts/`.

No product codebase or Figma file was provided — the brand book is a **communications/brand** manual, not a UI component library. The component set below is therefore an original, on-brand standard kit (see *Components*), and UI kits are illustrative product recreations built from the brand language.

---

## CONTENT FUNDAMENTALS

**Language:** Primary language is **Spanish** (Spain / LatAm). Copy is written in the **first person plural ("nosotros")** when the brand speaks ("Fomentamos…", "Aspiramos a…", "Nuestra misión…") and addresses the reader warmly.

**Tone:** Optimistic, energetic, playful, human. Learning is framed as an **adventure, a game, a challenge (reto)**. The Jester archetype shows up as warmth and a light irreverence; the Creator archetype as language about *building, inventing, transforming ideas into reality*.

**Vocabulary that recurs:** *emprendimiento, retos, dinámicas, habilidades sociales, creatividad, diversión, futuro, líderes, Future Minds, mentes brillantes/inquietas.*

**Casing:** Sentence case for running text. Headlines in the brand's vibrant graphics are frequently **ALL CAPS** and very large (Anton). Section/eyebrow labels are small caps with wide tracking.

**Emoji:** **Not** part of the brand system — do not use emoji. Personality comes from color, type scale, and simple line icons instead.

**Vibe (examples):**
- "SER EL CORAZÓN DE LA EDUCACIÓN EMPRENDEDORA" (vision headline)
- "Genyus School es un taller de mentes brillantes."
- "Aquí, la enseñanza se viste de diversión y el aprendizaje se convierte en una exploración vibrante."

When writing English, keep the same spirit: upbeat, encouraging, action-oriented ("Start now", "Take on the challenge"), never corporate or dry.

---

## VISUAL FOUNDATIONS

**Colors.** Saturated, joyful, high-energy. Each vertical owns a palette (see `tokens/colors.css`); **School blue `#1AACFF`** and **pink `#FF35A5`** are the master anchors. Colors are rarely used flat at large scale — the brand's signature device is the **gradient** (pink→coral→orange sunset for School; purple→blue→cyan for Business; indigo→purple→pink for University). Neutrals are a near-black ink (`#0E1116`) on white/paper.

**Type.** Two brand faces + one poster face:
- **Helotypo** — display / headings (brand voice).
- **Nobel Uno** — body, UI, everything running (geometric humanist sans, weights 300–900).
- **Anton** — huge ALL-CAPS poster headlines in vibrant graphic pieces.
Type is treated as a **dominant graphic element** — bold and large to create urgency and energy.

**Backgrounds.** Three registers: (1) clean white/paper for editorial clarity, (2) **full-bleed vertical gradients** for hero and emotional moments, (3) **humanized photography** (see below). Geometric shapes — circles, lines, outlined contours — are layered over these to add movement and structure.

**Photography.** Real people, natural light, **warm tones**, genuine spontaneous emotion, diversity of age/gender/ethnicity, relaxed non-posed composition. Never cold, stocky, or corporate. Often cut-out figures (calado) layered over gradients.

**Graphics / motifs.** Bold type + bright color + gradients + simple geometric shapes + simple line iconography (e.g. an outlined rocket), composed in **overlapping layers** for depth and dynamism.

**Corner radii.** Round and friendly — buttons and chips are fully **pill-shaped**; cards use 22px; small controls 8–14px. Nothing sharp.

**Cards.** White surface, soft shadow (`--shadow-sm`), 1px hairline border, generous padding, 22px radius. Optional **gradient top-accent bar** or full-gradient background (white text) for hero cards.

**Shadows.** Soft and low-contrast, tinted toward ink; colored **glow** shadows (pink / blue) under gradient & primary CTAs. No harsh or neumorphic shadows. No inner shadows by default.

**Borders.** Hairlines in `--ink-200/300`. Inputs use a 1.5px border that turns blue on focus with a soft blue focus ring.

**Transparency & blur.** Used sparingly — dialog scrims use a translucent ink with a light backdrop blur; soft-tone badges use low-opacity color fills.

**Animation.** Playful and slightly **bouncy** (`--ease-bounce`). Buttons scale down on press (0.96), toggles spring, dialogs pop in. Durations 120–380ms. Fades for tooltips. No infinite decorative loops.

**Hover / press states.** Hover generally brightens/keeps color with elevation; **press shrinks** (scale) rather than darkening — reinforcing the bouncy, tactile personality. Icon buttons shrink to 0.92.

**Layout.** Generous whitespace, 4px spacing rhythm, 1200px max container. Content is airy; energy comes from color and type, not density.

---

## ICONOGRAPHY

The brand manual specifies **simple, single-weight outlined line icons** (it shows an outlined rocket / *cohete delineado* as the exemplar) used to add fun and accessibility. No proprietary icon font or SVG set was shipped in the asset kit.

**Substitution (please confirm):** we use **[Lucide](https://lucide.dev)** — clean, single-weight, rounded line icons that closely match the brand's stated style. Load it via CDN:

```html
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
```

The `Icon` and `IconButton` components wrap Lucide. Good picks for Genyus: `rocket`, `sparkles`, `graduation-cap`, `lightbulb`, `trophy`, `users`, `target`, `play`, `book-open`. **Emoji and unicode glyphs are not used as icons.** If Genyus has (or wants) a bespoke icon set, send it and we'll swap Lucide out.

---

## Index / Manifest

**Root**
- `styles.css` — global entry point (consumers link this). `@import`s all tokens + fonts.
- `readme.md` — this guide.
- `SKILL.md` — Agent-Skill wrapper.

**Tokens** (`tokens/`)
- `fonts.css` — `@font-face` for Helotypo, Nobel Uno, Anton.
- `colors.css` — vertical palettes, neutrals, semantic aliases, signature gradients.
- `typography.css` — font families, weights, type scale, line-height, tracking.
- `spacing.css` — spacing scale, radii, shadows, motion, layout.

**Assets** (`assets/`)
- `fonts/` — brand webfonts (TTF/OTF).
- `logos/` — Genyus wordmark & School lockup in blue / black / white / gradient (SVG + PNG).

**Guidelines** (`guidelines/`) — foundation specimen cards (Colors, Type, Spacing, Brand).

**Components** (`components/`) — reusable React primitives:
- `forms/` — **Button**, **IconButton**, **Input**, **Select**, **Checkbox**, **Radio**, **Switch**
- `data/` — **Badge**, **Tag**, **Avatar**, **ProgressBar**
- `navigation/` — **Tabs**
- `feedback/` — **Tooltip**, **Dialog**, **Toast**
- `media/` — **Icon**
- `layout/` — **Card**

**UI kits** (`ui_kits/`)
- `marketing/` — Genyus School marketing landing page.
- `learn/` — student learning dashboard app.

### Intentional additions
- **Icon** — wrapper over Lucide, added because the brand relies on line icons but shipped no icon set. See ICONOGRAPHY.

---

## Namespace

Components compile to `window.GenyusSchoolDesignSystem_87b1a3`. In card / kit HTML:

```js
const { Button, Card, Icon } = window.GenyusSchoolDesignSystem_87b1a3;
```
