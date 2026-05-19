
markdown# Styling Guide

This document defines the CSS approach and patterns used across all components and projects. Update this file as your styling decisions become more defined.

> **Note:** A specific CSS methodology (Tailwind, CSS Modules, etc.) has not yet been chosen. This guide uses plain CSS with custom properties and BEM as the default approach. When a framework or tooling preference is decided, update this file to reflect it.

---

## Core Approach

- **Plain CSS** with CSS custom properties (variables)
- **BEM naming** for class structure (see `naming-conventions.md`)
- **Mobile-first** responsive design
- **No frameworks required** — components work in any project without build tools

---

## CSS Reset

Include a minimal reset at the top of every project's base stylesheet:

```css
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 100%;
  -webkit-text-size-adjust: 100%;
}

body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}

input, button, textarea, select {
  font: inherit;
}

p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
```

---

## Design Tokens

All visual values are defined as CSS custom properties in `:root`. Never hardcode colors, spacing, or font sizes — always reference a token.

```css
:root {
  /* ── Colors ──────────────────────── */
  --color-primary:       #2563eb;
  --color-primary-dark:  #1d4ed8;
  --color-primary-light: #dbeafe;

  --color-neutral-0:    #ffffff;
  --color-neutral-100:  #f5f5f5;
  --color-neutral-200:  #e5e5e5;
  --color-neutral-400:  #a3a3a3;
  --color-neutral-700:  #404040;
  --color-neutral-900:  #111111;

  --color-success:  #16a34a;
  --color-warning:  #d97706;
  --color-error:    #dc2626;

  /* ── Typography ──────────────────── */
  --font-base:    Georgia, 'Times New Roman', serif;
  --font-ui:      system-ui, sans-serif;
  --font-mono:    'Courier New', Courier, monospace;

  --text-xs:   0.75rem;
  --text-sm:   0.875rem;
  --text-base: 1rem;
  --text-lg:   1.125rem;
  --text-xl:   1.25rem;
  --text-2xl:  1.5rem;
  --text-3xl:  1.875rem;
  --text-4xl:  2.25rem;

  --leading-tight:  1.25;
  --leading-normal: 1.5;
  --leading-loose:  1.75;

  --weight-normal:   400;
  --weight-medium:   500;
  --weight-semibold: 600;
  --weight-bold:     700;

  /* ── Spacing ─────────────────────── */
  --space-1:  0.25rem;
  --space-2:  0.5rem;
  --space-3:  0.75rem;
  --space-4:  1rem;
  --space-6:  1.5rem;
  --space-8:  2rem;
  --space-12: 3rem;
  --space-16: 4rem;

  /* ── Borders ─────────────────────── */
  --radius-sm:   4px;
  --radius-md:   8px;
  --radius-lg:   12px;
  --radius-full: 9999px;

  --border-thin:   1px solid var(--color-neutral-200);
  --border-medium: 2px solid var(--color-neutral-200);

  /* ── Shadows ─────────────────────── */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);

  /* ── Transitions ─────────────────── */
  --transition-fast:   150ms ease;
  --transition-normal: 250ms ease;
  --transition-slow:   400ms ease;

  /* ── Layout ──────────────────────── */
  --container-sm:  640px;
  --container-md:  768px;
  --container-lg:  1024px;
  --container-xl:  1280px;
}
```

---

## Breakpoints

Always write mobile-first. Use `min-width` media queries to scale up:

```css
/* Mobile (default) — no media query needed */

/* Small: 640px+ */
@media (min-width: 640px) { }

/* Medium: 768px+ */
@media (min-width: 768px) { }

/* Large: 1024px+ */
@media (min-width: 1024px) { }

/* XL: 1280px+ */
@media (min-width: 1280px) { }
```

---

## Typography Defaults

```css
body {
  font-family: var(--font-base);
  font-size: var(--text-base);
  line-height: var(--leading-normal);
  color: var(--color-neutral-900);
  background-color: var(--color-neutral-0);
}

h1, h2, h3, h4, h5, h6 {
  font-family: var(--font-ui);
  font-weight: var(--weight-bold);
  line-height: var(--leading-tight);
}

h1 { font-size: var(--text-4xl); }
h2 { font-size: var(--text-3xl); }
h3 { font-size: var(--text-2xl); }
h4 { font-size: var(--text-xl); }
h5 { font-size: var(--text-lg); }
h6 { font-size: var(--text-base); }
```

---

## Focus Styles

Never remove focus outlines. Use a consistent custom focus style:

```css
:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}
```

---

## Future Decisions

When you decide on a styling framework or tooling approach, document it here:

- [ ] CSS methodology decision (Tailwind / CSS Modules / Styled Components / plain CSS)
- [ ] Font choices (self-hosted vs CDN)
- [ ] Dark mode strategy
- [ ] Animation/transition library (if any)
