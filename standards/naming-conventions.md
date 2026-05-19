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
.block {}
.block__element {}
.block--modifier {}
.block__element--modifier {}

| Part | What it is | Example |
|------|-----------|---------|
| Block | The standalone component | `.card` |
| Element | A part of the block (use `__`) | `.card__title` |
| Modifier | A variation or state (use `--`) | `.card--featured` |

**Examples:**
```css
.btn {}                   /* Block */
.btn__icon {}             /* Element */
.btn--primary {}          /* Modifier */
.btn--disabled {}         /* State modifier */

.form {}
.form__field {}
.form__label {}
.form__input {}
.form__input--error {}
```

**Rules:**
- Never nest BEM deeper than 2 levels (block > element — not block > element > element)
- Modifiers never exist without their block or element class
- State classes (like `is-active`, `is-hidden`) are allowed alongside BEM: `.btn.is-loading`

---

## CSS Custom Properties

Use `--category-name` format, grouped by category:

```css
:root {
  /* Colors */
  --color-primary: #2563eb;
  --color-primary-dark: #1d4ed8;
  --color-neutral-100: #f5f5f5;
  --color-neutral-900: #111111;

  /* Typography */
  --font-base: 'Georgia', serif;
  --font-mono: 'Courier New', monospace;
  --text-sm: 0.875rem;
  --text-base: 1rem;
  --text-lg: 1.25rem;

  /* Spacing */
  --space-xs: 0.25rem;
  --space-sm: 0.5rem;
  --space-md: 1rem;
  --space-lg: 2rem;
  --space-xl: 4rem;

  /* Borders */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-full: 9999px;

  /* Breakpoints (for use in JS; in CSS use min-width directly) */
  --bp-sm: 640px;
  --bp-md: 768px;
  --bp-lg: 1024px;
}
```

---

## JavaScript Variables & Functions

| Type | Convention | Example |
|------|-----------|---------|
| Variables | `camelCase` | `submitBtn`, `formData` |
| Constants (module-level) | `SCREAMING_SNAKE_CASE` | `MAX_RETRIES`, `API_URL` |
| Functions | `camelCase`, verb-first | `handleSubmit()`, `fetchData()`, `validateForm()` |
| Event handlers | `handle` + Event | `handleClick()`, `handleKeydown()` |
| Boolean variables | `is` or `has` prefix | `isValid`, `hasError`, `isLoading` |
| DOM elements | noun + element type | `submitBtn`, `nameInput`, `errorMsg` |

---

## HTML IDs & Data Attributes

- IDs: `kebab-case`, used sparingly (for accessibility links and JS when truly needed)
- `data-*` attributes: `data-kebab-case`, used for all JS hooks

```html
<form id="contact-form">
  <input
    id="field-email"
    data-validate="email"
    data-field="email"
  >
</form>
```

---

## Git Commit Messages

Use conventional commits format: `type(scope): description`

| Type | When to use |
|------|------------|
| `feat` | Adding a new component or feature |
| `fix` | Fixing a bug |
| `docs` | Documentation only changes |
| `style` | CSS/formatting changes, no logic change |
| `refactor` | Code change that isn't a fix or feature |
| `chore` | Maintenance (dependency updates, config) |

**Examples:**
feat(components): add modal component
fix(button): correct focus style on keyboard navigation
docs(standards): update naming conventions
style(card): adjust spacing to match design tokens

