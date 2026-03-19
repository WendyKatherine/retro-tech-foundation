# Retro Tech Foundation

Shared visual foundation package for a family of technical portfolio demos.

This repository contains the reusable visual base for three separate demo apps:

- Next.js + TypeScript + Tailwind CSS + daisyUI
- Vue 3 + TypeScript + Vite + Tailwind CSS + daisyUI
- Ionic + Capacitor + TypeScript

The goal is not to share framework-specific components. The goal is to share a consistent visual language across products through:

- design tokens
- CSS variables
- theme adapters
- reusable visual recipes
- SVG assets and patterns
- documentation and playground previews

## Purpose

Retro Tech Foundation is a lightweight design system inspired by:

- classic Macintosh interfaces
- phosphor monochrome screens
- 8-bit and early computing aesthetics
- pixel grids and game-like UI language
- cleaner modern product surfaces

The system is intentionally designed to feel nostalgic without becoming overly decorative, noisy, or difficult to maintain for a solo developer.

## Current status

Current version includes:

- initial `phosphor` theme
- design tokens in JSON format
- shared CSS variables
- platform adapters for web and Ionic
- local playground preview for rapid visual testing

## Repository structure

```txt
.
├── docs/
│   ├── design-principles.md
│   └── ui-rules.md
├── src/
│   ├── assets/
│   ├── css/
│   │   ├── core.css
│   │   ├── ionic.css
│   │   └── web.css
│   ├── playground/
│   │   ├── index.html
│   │   └── input.css
│   └── tokens/
│       ├── colors.json
│       ├── motion.json
│       ├── radius.json
│       ├── spacing.json
│       └── typography.json
├── package.json
└── README.md