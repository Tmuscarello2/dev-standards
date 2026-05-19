# Folder Structure

This document defines how projects that use this component library should be organized, and how this repository itself is structured.

---

## This Repository (`dev-standards`)

dev-standards/
├── CLAUDE.md                        ← Claude's operating instructions
├── README.md                        ← Repo overview and quick reference
│
├── standards/                       ← Coding rules and conventions
│   ├── coding-standards.md
│   ├── naming-conventions.md
│   ├── folder-structure.md          ← This file
│   └── styling-guide.md
│
├── components/                      ← All reusable UI components
│   ├── _template/                   ← Starter template for new components
│   │   ├── component.html
│   │   ├── component.css
│   │   ├── component.js
│   │   └── README.md
│   │
│   ├── ui/                          ← Small, single-purpose UI elements
│   │   ├── button/
│   │   ├── badge/
│   │   ├── card/
│   │   ├── modal/
│   │   ├── tooltip/
│   │   └── input/
│   │
│   ├── layout/                      ← Structural and spacing components
│   │   ├── container/
│   │   ├── grid/
│   │   └── section/
│   │
│   └── navigation/                  ← Nav patterns
│       ├── navbar/
│       ├── sidebar/
│       └── breadcrumb/
│
└── snippets/                        ← Small patterns that aren't full components
└── README.md

---

## Project Structure (Consumer Projects)

When starting a new project that references this library, use this structure:

my-project/
├── index.html
├── about.html
│
├── assets/
│   ├── css/
│   │   ├── tokens.css          ← CSS custom properties (copy from dev-standards)
│   │   ├── reset.css           ← CSS reset
│   │   ├── base.css            ← Typography, global defaults
│   │   └── components/         ← Per-component CSS (copied from dev-standards)
│   │       ├── button.css
│   │       └── card.css
│   │
│   ├── js/
│   │   ├── main.js             ← Entry point, page-level logic
│   │   └── components/         ← Per-component JS
│   │       ├── modal.js
│   │       └── form.js
│   │
│   └── images/
│       └── (organized by page or feature)
│
└── README.md

---

## Component Folder Structure

Every component in `/components/` must follow this pattern:

component-name/
├── component.html     ← Standalone markup (can be opened in a browser)
├── component.css      ← Scoped styles for this component only
├── component.js       ← Behavior (omit if no JS needed)
└── README.md          ← Documentation (see template for required sections)

**Rules:**
- Each component lives in its own folder
- Folder name must match the component's primary CSS block name
- The HTML file must be self-contained and previewable in a browser
- No component should import or depend on another component's CSS or JS
- Shared values (colors, spacing) go in CSS custom properties, not hardcoded

---

## Snippets vs Components

| | Snippets | Components |
|---|---|---|
| What it is | A short code pattern | A complete, reusable UI element |
| Has its own folder | No — lives in `/snippets/` | Yes |
| Has a README | No (just inline comments) | Yes |
| Standalone previewable | Not required | Required |
| Example | A CSS gradient trick | A modal with open/close behavior |

---

## What Goes Where

| Type of code | Location |
|---|---|
| New UI component | `/components/ui/component-name/` |
| New layout pattern | `/components/layout/component-name/` |
| New nav pattern | `/components/navigation/component-name/` |
| Small reusable snippet | `/snippets/README.md` (inline) |
| New coding rule | `/standards/coding-standards.md` |
| New naming rule | `/standards/naming-conventions.md` |
| New CSS pattern | `/standards/styling-guide.md` |
