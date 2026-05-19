# Naming Conventions

Consistent naming makes the codebase predictable. Claude should follow these patterns exactly when generating any file names, class names, IDs, variables, or functions.

---

## Files & Folders

| Type | Convention | Example |
|------|-----------|---------|
| Folders | `kebab-case` | `button-group/`, `nav-bar/` |
| HTML files | `kebab-case.html` | `contact-form.html` |
| CSS files | `kebab-case.css` | `contact-form.css` |
| JS files | `kebab-case.js` | `contact-form.js` |
| Standards/docs | `kebab-case.md` | `coding-standards.md` |

- Folder names should match the component name exactly
- One component per folder
- No spaces, no uppercase in file or folder names

---

## CSS Classes — BEM

Use **BEM (Block Element Modifier)** naming for all CSS classes.
