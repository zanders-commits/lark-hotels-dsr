# Reeco Design System

The visual identity, tone, and UI foundations for **Reeco** — the AI‑driven procure‑to‑pay platform for the hospitality industry.

**Source of truth: Reeco Brandbook 2026 (Figma).** This system mirrors the brand book directly — colors, type, logo, and house markers are extracted from the file, not reconstructed.

---

## About Reeco

Reeco is an all‑in‑one hotel procurement platform trusted by 1,000+ hospitality properties. It unifies **purchasing, receiving, inventory management, recipe costing, and AP automation** into a single product — freeing back‑of‑house teams from Excel sheets, punchout systems, and manual GL coding.

**Product surfaces in this system:**
1. **Web App** — the core procure‑to‑pay platform (purchasing, receiving, inventory, recipes, AP).
2. **Marketing Site** (reeco.com) — the public product website.

**Mission** — making life simpler — not just work better — for everyone in hospitality who works early mornings, late nights, holidays, and weekends to keep guests happy.

---

## Index

| File / folder | What it is |
|---|---|
| `README.md` | This file — brand context, voice, visual foundations, iconography. |
| `SKILL.md` | Agent skill manifest — how to invoke the design system. |
| `colors_and_type.css` | Source‑of‑truth CSS tokens (colors, scales, type, spacing, radii, shadows). |
| `fonts/` | Inter variable font (the brand's primary face). |
| `assets/` | Logos, marks. |
| `preview/` | Small HTML cards for the Design System review pane. |
| `ui_kits/web-app/index.html` | Reeco procure‑to‑pay web app shell. |
| `ui_kits/marketing-site/index.html` | Reeco.com marketing page. |

---

## Visual Foundations

### Colors

Strict 80 / 20 split: **80% primary (Mint), 20% secondary + accent.**

| Family | Core | Role |
|---|---|---|
| **Mint** *(primary)* | `#2BCC89` | Primary buttons, key headlines, main UI elements. The Reeco signature color. |
| **Navy** *(secondary)* | `#0A184A` | Headlines, secondary buttons, accents. Pairs with Mint for contrast. |
| **Rose** *(secondary)* | `#FF479A` | Highlights, action‑required CTAs, warnings, notifications. Sparingly for impact. |
| **Sky** *(tertiary)* | `#3BB0F4` | Links, information, progress indicators. |
| **Sun** *(tertiary)* | `#F6BE00` | Corp tone, budget warnings, accents. |
| **Stone** *(neutral)* | `#353535` | Body text, subtle UI. Stone‑400 is the disabled state. |

Every family ships a 6–7 step scale (see `colors_and_type.css`):

- Mint: `mint-900 → mint-50` (`#1A5E6D → #F2FCF8`)
- Navy: `navy-900 → navy-100` (`#0A184A → #F5F6F9`)
- Rose: `rose-500 → rose-100`
- Sky: `sky-500 → sky-100`
- Sun: `sun-500 → sun-100`
- Stone: `stone-900 → stone-100`

**Accessibility:** maintain sufficient contrast between text and background — never ship Mint text on Mint‑100 panels or Sun text on Stone‑100.

### Typography

**Inter** is the primary face — the brand book opens with *"Simplified with Inter."* Shipped as a variable font (`fonts/Inter-v20-latin.woff2`) so all four working weights load from one file.

**Type hierarchy** (verbatim from the brand book):

| Style | Spec |
|---|---|
| H1 | Inter Black, 32px / 36px |
| H2 | Inter Bold, 24px / 28px |
| H3 | Inter Bold, 18px / 22px |
| Body | Inter Regular, 12–14px |
| Links | Inter Semi‑bold, 12–14px (Sky) |

**Weights** — only four are in active use: **Black, Bold, Semi‑bold, Regular.** Use no more than 2–3 weights on a single page.

**Display/section titles** are 52px Bold with `-0.01em` tracking. The brand book uses *huge* Inter Black for cover and feature numerals (96–240px).

**Tone:** lowercase for a friendly, approachable feel. Maintain consistent hierarchy. Ensure sufficient contrast between text and background.

### House Markers

The brand book consistently uses **`///`** as a stylistic mark:

- As a bullet prefix (`/// Use lowercase for a friendly feel`)
- As a divider between name and role (`Mint Green /// Primary`)

Use `.rc-slash` (bullet) and the `///` literal (divider) — these are part of the visual identity, not decoration.

### Logo & Mark

The brand has two assets:

- **Wordmark** — "reeco" set in a custom geometric letterform. Use as the primary logo on light/Mist surfaces.
- **ee mark** — the dual‑loop cursive "ee" monogram. Use for favicons, avatars, app icons, and where a square brand bug is needed. Lives in a Mint or Rose rounded‑square container with white fill.

Files in `assets/`:

- `reeco-logo-primary-green.svg` — wordmark, Mint on light
- `reeco-logo-white.svg` — wordmark, white on dark/Mint
- `reeco-mark.svg` — ee mark, Mint
- `reeco-mark-white.svg` — ee mark, white

The brand book uses the mark in **Mint‑on‑white**, **white‑on‑Mint**, and **white‑on‑Rose** lockups. Container corner radius is roughly **12% of the side length** (e.g. `radius-3xl` ≈ 40px on a 378px tile).

### Layout, Spacing, Surfaces

- 4px baseline grid. Rhythm: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64.
- **Radii** are generous: cards 16px, hero/feature cards 24px, brand‑book signature cards 40px (`--radius-3xl`).
- **Shadows** are soft and Navy‑tinted: `0 25px 29px rgba(10, 24, 74, 0.20)` is the signature lift used on mark tiles in the brand book.
- Cards have full perimeter borders OR soft Navy‑tinted shadow on white. Never both at full strength.
- The hero cover motif is **Mint background + white cloud / scallop shape rising from the bottom** — a distinctive brand element used on covers and section openers.

### Motion

- 120–180ms transitions, `cubic-bezier(0.16, 1, 0.3, 1)`.
- Fades + 2–6px translates. No bouncing on exit, no scroll‑linked hero animations.
- Hover: darker fill on primary (Mint‑700), tinted background on ghost.
- Focus: 3px Mint ring at 30% opacity (`--shadow-focus`).

### Imagery

Warm, natural, un‑stylized hospitality shots (kitchens, pantries, service) — not stock business imagery. No duotone, no grain.

---

## Content Fundamentals

**Voice:** Hospitality operator → hospitality operator. Simple, clear, warm, confident, direct, time‑respecting.

**Avoid:** Corporate jargon, buzzwords, verbose hedging, hype. *"Leverage," "synergy," "best‑in‑class," "cutting‑edge,"* and *"paradigm"* are banned.

**Voice rules:**

- Address the reader as *"you"* / *"your team."* First‑person company voice is *"we."*
- **Lowercase / sentence case** for headings, buttons, and labels (brand book: *"Use lowercase for a friendly, approachable feel"*).
- Short sentences. If it reads like a contract, rewrite it.
- Concrete over abstract. *"Catches errors early"* > *"improves quality outcomes."*
- Written for non‑native English readers — the product serves hospitality staff across many languages. Avoid idioms.
- Em dashes — sparingly — for cadence.
- **No emoji in product UI.**
- Numbers win. *"1,000+ properties," "800% growth," "6‑figure purchases."*

**CTAs** — action verbs, lowercase except the first letter: *"Get a demo," "Start free trial," "Create order."*

---

## Iconography

Reeco does not ship a custom icon set. The product UI uses a clean, uniform line‑icon system.

- **Chosen system: [Lucide](https://lucide.dev/)** — stroke‑based, geometric, matches Inter's personality, CDN‑available, permissive license. *(This is a substitution — confirm or replace with a Reeco‑owned set if available.)*
- Sizes: 16px (inline), 20px (standard), 24px (nav), 32px+ (empty states).
- Stroke: 1.75px default. Color: `currentColor`.
- **No emoji, no unicode glyphs as icons** in product UI.

---

## Caveats

- **Lucide is a substitute** icon system — confirm or replace.
- **No product screenshots or codebase were provided** — the UI kit components are informed reconstructions guided by the brand book and public product descriptions.
- The brand book ships extensive page templates and applications (covers, business cards, social posts) we have not yet ported into HTML kits. Ask if those are needed.
