# dev-standards

A personal component library and coding standards repository for Vanilla HTML/CSS/JS projects.

> **For Claude:** When referenced in a session, read this file first, then `CLAUDE.md` for instructions on how to assist. Browse `/components` for reusable UI components and `/standards` for coding rules and conventions. Always match existing patterns before writing new code.

---

## Repository Structure

```
dev-standards/
├── CLAUDE.md                  ← Instructions for Claude (read this)
├── README.md                  ← You are here
├── standards/
│   ├── coding-standards.md    ← Core rules: formatting, naming, structure
│   ├── naming-conventions.md  ← File, class, variable naming rules
│   ├── folder-structure.md    ← How projects should be organized
│   └── styling-guide.md       ← CSS approach and patterns
├── components/
│   ├── ui/                    ← Buttons, modals, inputs, badges, etc.
│   ├── layout/                ← Grids, containers, headers, footers
│   ├── navigation/            ← Navbars, sidebars, breadcrumbs
│   └── _template/             ← Copy this when adding a new component
│       ├── component.html
│       ├── component.css
│       ├── component.js
│       └── README.md
└── snippets/
    └── README.md              ← Small reusable code patterns (not full components)
```

---

## Quick Reference

| I need...           | Go to...                          |
|---------------------|-----------------------------------|
| A UI component      | `/components/ui/`                 |
| A layout pattern    | `/components/layout/`             |
| Naming rules        | `/standards/naming-conventions.md`|
| CSS patterns        | `/standards/styling-guide.md`     |
| Project structure   | `/standards/folder-structure.md`  |
| New component setup | `/components/_template/`          |

---

## Stack

- **Language:** Vanilla HTML, CSS, JavaScript (ES6+)
- **Styling:** See `/standards/styling-guide.md`
- **No frameworks, no build tools required** unless noted inside a component's README

---

## Adding a New Component

1. Copy `/components/_template/` into the appropriate subfolder
2. Rename the folder to your component name (kebab-case)
3. Fill in the component files and update its `README.md`
4. Commit with message: `feat(components): add [component-name]`
