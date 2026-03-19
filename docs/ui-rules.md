# UI Rules

## Naming convention

Shared classes use the `rt-` prefix.

Examples:

- `rt-window`
- `rt-panel`
- `rt-btn`
- `rt-input`
- `rt-badge`
- `rt-kpi`

This keeps the design system namespace clear and avoids collisions inside consumer apps.

## Source of truth

Current rendering source of truth lives in CSS variables defined in `core.css`.

JSON token files are maintained as structured references and future portability artifacts.

When updating a token:

1. update the CSS variable in `core.css`
2. sync the related JSON token file
3. verify the playground visually

## Theme usage

The first theme is `phosphor`.

Supported selectors currently include:

- `:root`
- `[data-rt-theme="phosphor"]`
- `[data-theme="phosphor"]` for web integration

Future themes should follow the same structure.

## Layout rules

### Shell
Use `rt-app-shell` as the page-level wrapper for demos and previews.

### Stacks
Use `rt-stack` for vertical content groups with consistent spacing.

### Grids
Use `rt-grid-2` when two related panels or windows should sit side by side on larger screens.

## Window pattern

Use `rt-window` for primary framed containers.

A window usually contains:

- `rt-window__titlebar`
- `rt-window__body`

Use windows for:

- feature sections
- grouped scenarios
- preview modules
- dashboard-like blocks

Do not use windows for every small item on screen.

## Panel pattern

Use `rt-panel` for internal grouping inside a window.

Use `rt-panel--inset` when you need a more embedded or data-oriented appearance.

Panels are appropriate for:

- text summaries
- grouped controls
- metrics
- filters
- status blocks

## Button rules

Base button class:

- `rt-btn`

Variants currently available:

- `rt-btn--primary`
- `rt-btn--ghost`

Guidelines:

- primary buttons should represent the main action of a section
- ghost buttons should remain secondary and visually lighter
- avoid placing too many primary buttons next to each other

## Input rules

Use `rt-input` for text fields inside the foundation playground and in simple recipes.

Inputs should always preserve:

- visible border
- readable placeholder
- clear focus state
- enough internal padding

## Badge rules

Use `rt-badge` for small labels, state indicators, or taxonomy tags.

Available state styles currently include:

- `rt-badge--success`
- `rt-badge--warning`
- `rt-badge--danger`

Badges should be short and high-signal.

## KPI rules

Use KPI patterns for concise data emphasis.

Structure:

- `rt-kpi`
- `rt-kpi__label`
- `rt-kpi__value`

KPI values may use display typography for stronger contrast.

## Spacing rules

Prefer tokenized spacing through the defined scale.

General rhythm:

- compact internal spacing: `space-2` to `space-4`
- section spacing: `space-4` to `space-6`
- larger layout separation: `space-6` to `space-8`

Do not introduce arbitrary spacing values unless required for a very specific visual correction.

## Radius rules

Corners should feel soft and intentional, never overly rounded.

Use:

- smaller radius for inputs and compact controls
- medium radius for buttons and panels
- larger radius for windows and prominent containers

## Border and shadow rules

Borders are part of the system identity and should remain visible.

Guidelines:

- use soft contrast for standard borders
- reserve stronger borders for emphasis and active hierarchy
- shadows should support depth, not dominate the interface

## Tailwind usage

Tailwind utilities are allowed in consumer apps and in the playground for layout and composition.

Preferred use of Tailwind:

- spacing utilities
- responsive layout
- flex and grid helpers
- max-width and alignment
- typography sizing in composition-level markup

Avoid replacing shared `rt-*` recipe classes with large chains of utility classes when a reusable pattern already exists.

## Portability rules

The foundation package should remain framework-agnostic.

Do not place framework-specific logic inside shared CSS or tokens.

Avoid adding:

- React-specific assumptions
- Vue-specific selectors
- Ionic component overrides that break portability

Adapters should stay thin and focused on theme translation.

## Quality check before adopting changes

Before finalizing a visual change, verify:

- does it still match the retro-tech family?
- does it improve clarity?
- does it remain portable?
- does it avoid unnecessary complexity?
- does it still feel maintainable for one developer?

If the answer is no, simplify.