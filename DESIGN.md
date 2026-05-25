# Polyrics Labs — Design System

> **"Software de todos para todos"**
> A design system for a digital craftsmanship laboratory — editorial white canvas,
> berry-plum accent ramp, precision-focused. Built for open-source tooling and
> universal readability.

## Visual Theme & Atmosphere

Two valid visual modes sharing the same token contract:

### 1. Editorial Minimal (default)
A crisp, editorial white canvas. Warm-white page (`#FAF7F8`) with near-black text and
a berry-plum gradient accent ramp (`#38355B` → `#FFC2D7`). Generous whitespace,
refined hierarchy, no decoration — every element earns its place.

### 2. Brutalist-Editorial (landing page, blog, products)
Same token base, amplified: heavy 2–5px borders replace hairline separators, noise
textures and scanlines evoke dystopian hyperrealism, glitch animations on headlines,
monospace metadata leaks into every component, and raw form fields use near-black
borders with zero border-radius. This mode communicates the laboratory's raw,
anti-corporate, open-source DNA.

**Mode selection rule:** Use Editorial Minimal for design-system documentation,
color/type showcases, and internal tools. Use Brutalist-Editorial for public-facing
landing pages, blog, product listings, and contact forms.

## Color Palette & Roles

| Token | Value | Role |
|-------|-------|------|
| `--bg` | `#FAF7F8` | Page background — warm white |
| `--surface` | `#FFFFFF` | Cards, modals, raised panels |
| `--surface-warm` | `#F7F2F5` | Sidebars, hover states |
| `--fg` | `#17121B` | Primary text — near-black |
| `--fg-2` | `#372E3D` | Secondary text |
| `--muted` | `#6B5E73` | Captions, placeholders |
| `--meta` | `#998BA3` | Timestamps, legal, metadata |
| `--border` | `#E5DEE3` | Card edges, input borders (editorial mode) |
| `--border-soft` | `#F2EAF0` | Row separators |
| `--accent` | `#38355B` | Primary CTAs — deep plum |
| `--accent-2` | `#6C4676` | Hover states, secondary actions |
| `--accent-3` | `#B55C96` | Interactive, links, glitch colors |
| `--accent-4` | `#FF87B7` | Badges, subtle accents, progress |
| `--accent-5` | `#FFC2D7` | Soft backgrounds, dividers |
| `--success` | `#0A8A40` | Confirmation, completion |
| `--warn` | `#C07A08` | Attention, pending |
| `--danger` | `#D43030` | Error, destructive actions |

## Accent Ramp Usage

- **`#38355B` (--accent)** — Buttons, CTAs, heavy borders in brutalist mode. Maximum twice per screen.
- **`#6C4676` (--accent-2)** — Hover states, secondary action color, cursor-dot cycling.
- **`#B55C96` (--accent-3)** — Glitch chromatic aberration, inline links, focus rings, section labels.
- **`#FF87B7` (--accent-4)** — Progress bars, status dots (active), glitch colors, pulse animations.
- **`#FFC2D7` (--accent-5)** — Gradient backgrounds, subtle hover overlays, divider gradients.

## Logo

The Polyrics Labs mark — **"Prism Node"** — is a pure geometric constellation built
from primitive shapes: polygons, circles, and lines. The outer hexagon represents the
laboratory frame; the inner diamonds represent polyvalence and craft; the vertex nodes
represent community.

### Color usage
- **Primary use:** `--accent` (`#38355B`) on white backgrounds.
- **Monochrome:** Near-black for text-only contexts, white on dark-background watermarks.
- **Metadata / icons:** May use `--muted` for subdued iconography.

### Files
- `logo.svg` — Full mark + "POLYRICS LABS" wordmark (256×320, uses `currentColor`)
- `assets/icons/logo-compact.svg` — Mark only, no text (256×256) — use inline
- `assets/icons/logo-16.png` through `assets/icons/logo-1024.png` — Raster exports

## Typography Rules

- **Display / headings:** `Elms Sans`, weight 600–900
- **Body:** `Elms Sans`, weight 400–500
- **Mono:** `JetBrains Mono` → `IBM Plex Mono` → `ui-monospace`
- Scale (px): 11 · 13 · 16 · 20 · 24 · 36 · 52 · 76
- Line-height: 1.58 body, 1.04 headings (brutalist mode uses tighter leading)
- Letter-spacing: -0.028em on display sizes (≥36px)
- **Brutalist mode:** Use weight 800–900 for headlines, 10–11px mono for all metadata labels

### Elms Sans Font Weights

| Weight | Name | File |
|--------|------|------|
| 100 | Thin | `mpid18pd-ElmsSans-Thin.ttf` |
| 200 | ExtraLight | `mpid18n9-ElmsSans-ExtraLight.ttf` |
| 300 | Light | `mpid18nk-ElmsSans-Light.ttf` |
| 400 | Regular | `mpid18p4-ElmsSans-Regular.ttf` |
| 500 | Medium | `mpid18np-ElmsSans-Medium.ttf` |
| 600 | SemiBold | `mpid18p8-ElmsSans-SemiBold.ttf` |
| 700 | Bold | `mpid18mx-ElmsSans-Bold.ttf` |
| 800 | ExtraBold | `mpid18n4-ElmsSans-ExtraBold.ttf` |
| 900 | Black | `mpid18mi-ElmsSans-Black.ttf` |

All weights also have italic variants (suffixed `-Italic`).

## Components

### Editorial Minimal Mode

- **Buttons:** 2–4px radius. Primary = deep plum fill + white label. Secondary = 1px border. Outline = 2px border + transparent.
- **Cards:** White surface, 1px border, 8px internal padding. Subtle shadow on hover.
- **Inputs:** 1px border, 4px radius. Plum border + ring on focus.
- **Links:** Plum color, no underline, underline on hover.
- **Code blocks:** Surface background + mono font + 1px border.

### Brutalist-Editorial Mode (new)

- **Glitch text:** Headlines use \`::before` and \`::after` pseudo-elements with `clip-path` keyframe animations in magenta/pink chromatic aberration colors. Hover triggers full glitch reveal.
- **Noise overlay:** Fixed full-viewport SVG `feTurbulence` filter at opacity 0.032 with `mix-blend-mode: multiply`. Animates via `steps(3)` keyframes for CRT flicker.
- **Scanlines:** Fixed full-viewport `repeating-linear-gradient` at opacity 0.022, 2px vertical bands.
- **Brutalist cards:** 2px solid borders (`--fg` or `--border`), zero radius, hover lifts with deep plum accent border and subtle gradient overlay.
- **Project cards:** CSS grid with 2px shared borders (no gaps), progress bars in accent-3/4, status dots with glow.
- **Blog cards:** Scanline overlaid gradient image areas, border-bottom gradient underline animation on hover.
- **Raw form fields:** 2px near-black borders, zero radius, transparent background, mono placeholder text, plum border on focus with subtle background tint.
- **Cursor dot:** 14px circle with `mix-blend-mode: exclusion`. Color-cycles through all 5 accent stops over 4 seconds. Grows to 32px on interactive elements. 0.08 lerp delay.
- **Scroll reveal:** `IntersectionObserver` at threshold 0.12. Fade + translateY(28px) with staggered delays (0.08s–0.32s) on grid children.
- **Gradient dividers:** `<hr>` replacements using `linear-gradient(90deg, transparent, var(--accent-5) 20%, var(--accent-3) 50%, var(--accent-5) 80%, transparent)`, 3px height.
- **Section labels:** Monospace 10px, uppercase, letter-spacing 0.14em, underline accent border, inline-block.
- **Stats:** 2px accent border, center-aligned, display font 40px number + mono 10px label.

## Layout Principles

- 12-column grid, 1200px max-width, 28px gutters (desktop).
- Sections: 112px top+bottom default. 80px tablet/phone.
- Brutalist mode: Zero border-radius. 2px minimum border width. Whitespace as contrast, not filler.
- Editorial mode: 4–8px radii. 1px borders. Generous whitespace.

## Effects & Animations

### Dystopian layer stack (brutalist mode, z-index ordered)
1. `z-index: 9999` — Cursor dot (`pointer-events: none`)
2. `z-index: 9998` — Noise overlay (`pointer-events: none, mix-blend-mode: multiply`)
3. `z-index: 9997` — Scanlines (`pointer-events: none, repeating-linear-gradient`)
4. `z-index: 10` — Sticky topnav with backdrop blur
5. Content in normal flow

### Glitch animation
- Dual pseudo-element chromatic aberration: `::before` in magenta (`#B55C96`), `::after` in pink (`#FF87B7`)
- Clip-path inset cycling with translations at 3s and 2.7s intervals, `alternate-reverse`
- Full opacity on hover
- Applies only to `.glitch` spans

### Color cycling cursor
- SetInterval 800ms cycling through all 5 accent stops
- CSS transition on background for smooth color changes
- Class toggle `.hovering` on interactive elements (32px size, `mix-blend-mode: difference`)

### Scroll reveal
- `IntersectionObserver` at threshold 0.12
- Initial state: `opacity: 0; transform: translateY(28px)`
- Visible state: `opacity: 1; transform: translateY(0)`
- Transition: 0.7s `cubic-bezier(0.2, 0, 0, 1)`
- Delay classes: `.reveal-delay-1` (0.08s) through `.reveal-delay-4` (0.32s)

### Gradient usage rules
- Allowed: horizontal dividers, hero accent rule, card hover overlays (low opacity), cursor dot cycling
- Forbidden: full-page gradient washes, gradient text (use solid accent values), gradient backgrounds replacing solid colors

## Do's and Don'ts

- ✅ White editorial canvas with crisp typography — focused, not murky.
- ✅ One accent (`#38355B`), used at most twice per screen. The ramp provides nuance.
- ✅ Brutalist mode: heavy borders (2–5px), noise/scanline overlays, glitch animations.
- ✅ Editorial mode: light borders (1px), whitespace as separator, clean layouts.
- ✅ Mono for code, numerics, timestamps, IDs, metadata, section labels.
- ✅ Use the Prism Node logo in hero and nav.
- ✅ Use Elms Sans as the primary typeface for both display and body text.
- ✅ Gradient use restricted to dividers, hero accents, hover overlays, and cursor dot.
- ✅ Real content, no filler — if a stat or tag doesn't exist, leave it out.
- ❌ No dark backgrounds — this is a white-first system. The effects layer adds texture without changing the canvas.
- ❌ No emoji as icons.
- ❌ No gradients as full-page backgrounds.
- ❌ No more than three type sizes on one screen.
- ❌ No Inter, Roboto, or Arial — Elms Sans is canonical.
- ❌ No rounded corners in brutalist mode (0px radius).
- ❌ No decorative effects that reduce readability or performance.

## Business Model Alignment

- **Open By Design:** The token system is public. Anyone can use it.
- **Utility First:** Every component serves a function. No decoration.
- **Lean System:** Minimal tokens. Derived values via `color-mix()`.
- **Universal Readability:** High contrast (≥7:1 for body text on white).
