
---

## `docs/design-principles.md`

```md
# Design Principles

## 1. Nostalgic, but not theatrical

The system draws inspiration from classic Macintosh interfaces, phosphor screens, pixel grids, and early software environments. However, the visual language should feel refined and intentional rather than cartoonish or exaggerated.

This is retro-tech with discipline.

## 2. Monochrome first, accents second

The first theme is built around a monochrome green palette. The purpose is to establish a strong visual identity through tone, contrast, surface treatment, and typography before introducing more colorful variants.

Color should support hierarchy, not replace it.

## 3. Pixel influence, not pixel overload

Pixel motifs are part of the identity, but they should appear in controlled ways:

- background grids
- small decorative patterns
- icon edges
- display typography moments

The interface should not become visually noisy or gimmicky.

## 4. Clear structure over decoration

Every visual element should help communicate structure:

- windows frame content
- panels organize information
- badges communicate state
- spacing creates rhythm
- borders define hierarchy

Decoration is allowed only when it supports readability and mood.

## 5. Elegant constraints

This system is designed for a solo developer maintaining multiple demos. Because of that, the visual language must stay within a practical level of complexity.

Preferred qualities:

- repeatable
- low maintenance
- portable
- token-driven
- themeable with CSS variables

Avoid highly custom one-off UI pieces unless they can be reused.

## 6. Surface depth should be subtle

The interface uses layered surfaces, soft borders, mild glows, and restrained shadows. Depth should feel tactile but lightweight.

Avoid:

- overly dramatic shadows
- glassmorphism-heavy blur
- neon overload
- gradients that reduce legibility

## 7. Typography creates tone

Typography carries a large part of the identity.

Current roles:

- sans-serif for body and UI readability
- display mono/pixel style for titles, metrics, and special emphasis
- monospaced type for technical or data-oriented areas

Typography should feel computational, but still polished.

## 8. Consistency across frameworks matters more than exact sameness

The goal is not pixel-perfect cloning across Next.js, Vue, and Ionic. The goal is a shared family resemblance.

That means:

- same tokens
- same tone
- similar surfaces
- consistent hierarchy
- recognizably related interactions

Each platform may adapt details while preserving the same visual DNA.

## 9. Components are local, language is shared

This repository shares visual language, not framework components.

Shared:

- tokens
- CSS variables
- theme mappings
- assets
- patterns
- rules

Local to each app:

- implementation details
- framework components
- interaction logic
- layout composition

## 10. Portfolio quality requires narrative

This system is not only a styling layer. It also supports a portfolio story.

The visual identity should communicate:

- technical care
- systems thinking
- consistency across products
- design sensitivity
- maintainability

The interface should make the demos feel like parts of the same ecosystem.