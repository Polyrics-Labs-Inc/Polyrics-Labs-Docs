---
name: polyrics-labs
description: |
  Design system for Polyrics Labs — an open-source software laboratory.
  Editorial white canvas, berry-plum accent ramp (5 stops), Elms Sans typography.
  Two visual modes: Editorial Minimal and Brutalist-Editorial. Includes tokens,
  components, effects, brand assets, and integration targets for any project.
triggers:
  - "polyrics"
  - "polyrics labs"
  - "laboratorio de software"
  - "berry plum palette"
  - "elms sans"
  - "editorial minimal"
  - "brutalist editorial"
od:
  mode: design-system
  category: design-systems
---

# Polyrics Labs — Design System

> **"Software de todos para todos"**

Design system for an open-source software laboratory. Editorial white canvas with a
berry-plum gradient accent ramp (`#38355B` → `#FFC2D7`). Elms Sans as canonical
typeface. Built on four pillars: Open By Design, Utility First, Lean System, and
Universal Readability.

## Four Pillars (binding design rules)

- **Open By Design** — All tokens are public. Share the process, not just the result.
- **Utility First** — Every component serves a function. No decoration.
- **Lean System** — Minimal tokens. Derive values via `color-mix()`.
- **Universal Readability** — High contrast (≥7:1 body on white), legible hierarchy.

## Palette

### Surface stack (white-first, 3 levels)
| Token | Value | Role |
|-------|-------|------|
| `--bg` | `#FAF7F8` | Warm-white page |
| `--surface` | `#FFFFFF` | Cards, panels |
| `--surface-warm` | `#F7F2F5` | Hover, secondary areas |

### Foreground ramp (4 levels)
| Token | Value | Role |
|-------|-------|------|
| `--fg` | `#17121B` | Primary text |
| `--fg-2` | `#372E3D` | Secondary text |
| `--muted` | `#6B5E73` | Captions |
| `--meta` | `#998BA3` | Timestamps |

### Accent ramp — berry-plum (5 stops)

| Token | Value | Role | Contrast on white |
|-------|-------|------|-------------------|
| `--accent` | `#38355B` | Primary CTAs, deep plum | 10.4:1 AAA |
| `--accent-2` | `#6C4676` | Hover, secondary actions | 5.6:1 AA |
| `--accent-3` | `#B55C96` | Links, glitch, focus rings | 3.3:1 (decorative) |
| `--accent-4` | `#FF87B7` | Badges, progress, pulses | 1.5:1 (decorative) |
| `--accent-5` | `#FFC2D7` | Soft backgrounds, dividers | 1.2:1 (decorative) |

### Semantic colors
| Token | Value | Role |
|-------|-------|------|
| `--success` | `#0A8A40` | Confirmation |
| `--warn` | `#C07A08` | Attention |
| `--danger` | `#D43030` | Error |

## Typography

- **Display / headings:** Elms Sans, weight 600–900, `letter-spacing: -0.02em`
- **Body:** Elms Sans, weight 400–500, `line-height: 1.58`
- **Mono:** JetBrains Mono → IBM Plex Mono → ui-monospace
- **Type scale:** 11 / 13 / 16 / 20 / 24 / 36 / 52 / 76 px
- **Brutalist mode:** weight 800–900 headlines, 10–11px mono metadata

Elms Sans available in 9 weights (100–900) × Regular + Italic.
Font files: `assets/fonts/mpid18*-ElmsSans-*.ttf`

## Visual Modes

### Editorial Minimal (default)
Crisp white canvas. Hairline 1px borders, 4–8px radii. Generous whitespace.
Refined hierarchy. For documentation, internal tools, system showcases.

### Brutalist-Editorial (landing, blog, products)
Same tokens, amplified: 2–5px borders, zero radius, noise overlay + scanlines,
glitch text animations, raw form fields, gradient dividers. For public-facing pages
that communicate the laboratory's anti-corporate, open-source DNA.

## Integration Targets

These are the canonical entry points for consuming Polyrics Labs in other projects:

### Target 1: Tokens (`tokens.css`)
Paste the `:root` block verbatim into any artifact's first `<style>`.
Includes all @font-face blocks for Elms Sans (18 variants).
Reference all tokens via `var(--*)` — never raw hex outside `:root`.
File: `tokens.css`

### Target 2: Components (`components.html`)
Complete component library: buttons (4 variants), inputs (2), badges (4 colors),
cards, code blocks, alerts, toasts, navigation, tabs, progress bars, tables,
pagination, avatars, tooltips, radio/checkbox. Each with all interactive states.
Snippets extractable as standalone HTML. File: `components.html`

### Target 3: Landing page (`polyrics.html`)
Production landing page with 7 sections (hero, mission, products, pillars,
upcoming projects, blog, contact). Full dystopian layer stack: particle field,
noise overlay, scanlines, glitch loader, cursor dot with color cycling,
scroll reveal. File: `polyrics.html`

### Target 4: Brand assets (`assets/icons/`)
- `logo.svg` — Full Prism Node mark + "POLYRICS LABS" wordmark (256×320)
- `assets/icons/logo-compact.svg` — Mark only (256×256)
- `assets/icons/logo-{16..1024}.png` — 9 raster sizes
- All use `currentColor` — inherit accent at use-site

## Dystopian Layer Stack (z-index)

| z-index | Layer | Effect |
|---------|-------|--------|
| 99999 | Loader | Fullscreen glitch splash on page load |
| 9999 | Cursor dot | 14px, color-cycles, `mix-blend-mode: exclusion` |
| 9998 | Noise overlay | SVG `feTurbulence` at 0.032 opacity |
| 9997 | Scanlines | `repeating-linear-gradient` at 0.022 opacity |
| 9996 | Grid pattern | Subtle 48px grid at 0.03 opacity |
| 10 | Topnav | Sticky, `backdrop-filter: blur(12px)` |
| 1 | Content | Normal document flow |

## Animation Contracts

- **Particle field:** 80 circles, 1.5–5px radius, 5 accent colors. Drift at random vectors, wrap on viewport exit. Mouse repulsion radius 180px. Pulse frequency 0.2–0.5Hz.
- **Glitch text:** Dual `::before`/`::after` chromatic aberration (magenta `#B55C96`, pink `#FF87B7`). `clip-path` inset cycling at 3s / 2.7s intervals.
- **Cursor dot:** `setInterval` 800ms cycling all 5 accent stops. Grows 14px→32px on interactive elements. Lerp delay 0.08 for smooth trailing.
- **Scroll reveal:** `IntersectionObserver` at threshold 0.12. Fade + translateY(28px). 0.7s cubic-bezier transition. Stagger delays 0.08–0.32s.
- **Gradient dividers:** `linear-gradient(90deg, transparent, --accent-5 20%, --accent-3 50%, --accent-5 80%, transparent)`, 3px height.

## Do's & Don'ts

- ✅ One accent (`#38355B`) max twice per screen. Ramp provides nuance.
- ✅ Elms Sans canonical. Mono for code, numerics, metadata.
- ✅ Gradients restricted to dividers, hero accents, hover overlays, cursor dot.
- ✅ Brutalist: 2–5px borders, noise, glitch, raw forms. Editorial: 1px, radii, space.
- ✅ Prism Node logo in hero + nav. Inherits accent via `currentColor`.
- ✅ Real content only. No filler, no invented metrics.
- ❌ No dark backgrounds. This is a white-first system.
- ❌ No emoji as icons.
- ❌ No gradients as full-page backgrounds.
- ❌ No more than 3 type sizes per screen.
- ❌ No Inter, Roboto, Arial. Only Elms Sans.
- ❌ No rounded corners in brutalist mode (0px radius).
