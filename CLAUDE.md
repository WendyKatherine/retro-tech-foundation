# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev               # Tailwind CLI watch mode — compiles playground CSS on save
npm run build:playground  # One-shot compile of playground CSS
npm run format            # Prettier over all files
```

There are no tests. Visual verification is done through `src/playground/index.html` — open it in a browser while `npm run dev` is running.

> **Mac ARM + Node 18 note:** `@tailwindcss/oxide-darwin-arm64` must be installed explicitly. The project was validated on Node 18.20.4 / npm 10.7.0 / arm64.

## Architecture

This is a **CSS-only design system package** (`@wendy/retro-tech-foundation`). It exports CSS files and JSON tokens — no JavaScript, no framework components.

### CSS layer chain

```
core.css          ← global tokens (:root), resets, base utility classes
themes/*.css      ← per-theme CSS variables scoped to [data-rt-theme="..."]
recipes.css       ← all reusable UI patterns (.rt-*)
web.css           ← assembles the three above + maps rt- vars → DaisyUI --color-* vars
ionic.css         ← assembles the three above + maps rt- vars → --ion-* vars
```

Consumer apps import either `web.css` (Next.js, Vue) or `ionic.css` (Ionic), never both.

### Theming model

Themes are scoped to attribute selectors — never `:root` (except in `ionic.css` as a phosphor default fallback, which is a known limitation). The active theme is set on a wrapper element:

```html
<div data-rt-theme="phosphor">  <!-- or ivory, bigblue -->
```

DaisyUI consumers can also use `data-theme="phosphor"` — both selectors are present in each theme block.

### Variable namespaces

- `--rt-*` — system variables defined in `core.css` and `themes/*.css` (spacing, radius, motion, colors, surfaces, glass effects)
- `--color-*` — DaisyUI mapping in `web.css`
- `--ion-*` — Ionic mapping in `ionic.css`

JSON tokens in `src/tokens/` are documentation artifacts. The CSS variables are the runtime source of truth. When updating a token, change the CSS variable first, then sync the JSON.

### Known issues

- `core.css` contains phosphor-specific hardcoded color values in `body`, `::selection`, and `.rt-dot`. These do not respond to theme changes.
- `ionic.css` binds phosphor as `:root` default, so Ionic apps are implicitly phosphor unless a `data-rt-theme` attribute is set.

## Conventions

- All system classes use the `rt-` prefix to avoid collisions in consumer apps.
- Adapters (`web.css`, `ionic.css`) must stay thin — only variable mappings, no new visual rules.
- Recipes in `recipes.css` must use `--rt-*` variables exclusively — no hardcoded color values.
- Tailwind utilities are allowed in the playground and in consumer apps for layout/composition. Do not replace `rt-*` recipe classes with utility chains when a recipe already exists.
- `rt-window` is for primary framed containers; `rt-panel` is for internal grouping inside a window. Do not nest windows.

## Design intent

Retro-tech aesthetic inspired by classic Macintosh, phosphor screens, and early computing — intentionally nostalgic but not theatrical. See `docs/design-principles.md` for the full design philosophy and `docs/ui-rules.md` for component usage rules.
