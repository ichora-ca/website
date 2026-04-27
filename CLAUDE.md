# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start Astro dev server with HMR
npm run build     # Astro static build → dist/
npm run preview   # Serve the production build locally
```

No test suite is configured.

## Architecture

This is a single-page marketing website for Ichora (cold plasma seed treatment technology) built with Astro.

**[src/layouts/Layout.astro](src/layouts/Layout.astro)** — HTML shell: `<head>`, Google Fonts, Lucide CDN script, global CSS import.

**[src/pages/index.astro](src/pages/index.astro)** — All page content (nav + every section).

**[src/styles/global.css](src/styles/global.css)** — All CSS.

**[public/](public/)** — Static assets (images, SVGs, favicon). Referenced with leading `/` paths.

### CSS conventions

- Color system uses CSS custom properties defined in `:root` (`--ink`, `--cream`, `--magenta`, `--rule`)
- No CSS framework — all styles are handcrafted with grid/flexbox
- Responsive breakpoints are at `<820px`, `<800px`, and `<900px`

### JavaScript

Lucide icons (CDN `unpkg.com/lucide@latest`) are initialized via `<script is:inline>` in the layout:

```js
document.addEventListener('DOMContentLoaded', () => { if (window.lucide) lucide.createIcons(); });
window.addEventListener('load', () => { if (window.lucide) lucide.createIcons(); });
```

### Page sections (in order)

Navigation → Hero (with YouTube embed) → Problem (stats) → Science (cold plasma explanation + flowchart) → Process (4-step) → Results (trial metrics) → Team (5 members) → Vision (UN SDGs) → Contact → Footer
