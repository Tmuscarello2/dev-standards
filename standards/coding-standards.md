# Coding Standards

These are the core rules for all code written in this repository and any project that references it. Claude should treat these as non-negotiable unless the user explicitly overrides a rule.

---

## General Principles

- **Readable over clever** — code should be easy to understand at a glance
- **Consistent over personal** — follow the pattern that already exists, even if you'd do it differently
- **Simple over complex** — don't over-engineer; solve the problem in front of you
- **No magic numbers** — use named variables or CSS custom properties instead of raw values

---

## HTML

- Use semantic elements (`<header>`, `<main>`, `<section>`, `<article>`, `<nav>`, `<footer>`, `<button>`, etc.)
- Every interactive element must be keyboard accessible
- Every image needs a descriptive `alt` attribute (or `alt=""` if purely decorative)
- Use `data-*` attributes for JS hooks — never use classes or IDs for JavaScript selection
- Indent with **2 spaces**
- One element per line for multi-attribute tags
- Boolean attributes written without values: `<input disabled>` not `<input disabled="true">`
- Always include `lang` on `<html>`: `<html lang="en">`

**Example:**
```html
<button
  class="btn btn--primary"
  data-action="submit-form"
  aria-label="Submit contact form"
>
  Submit
</button>
```

---

## CSS

- Indent with **2 spaces**
- One property per line
- Always include a space after the colon: `color: red;` not `color:red;`
- End every declaration with a semicolon
- Use **CSS custom properties** for all colors, spacing, fonts, and breakpoints
- Define all custom properties in `:root` at the top of the stylesheet
- Avoid `!important` — if you need it, the specificity structure is wrong
- Don't use inline styles
- Media queries go at the **bottom** of the file or at the bottom of the relevant component block
- Mobile-first: write base styles for mobile, then use `min-width` breakpoints to scale up

**Example:**
```css
:root {
  --color-primary: #2563eb;
  --space-md: 1rem;
}

.btn {
  display: inline-flex;
  align-items: center;
  padding: var(--space-sm) var(--space-md);
  background-color: var(--color-primary);
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
```

---

## JavaScript

- Use **ES6+** syntax (arrow functions, `const`/`let`, template literals, destructuring)
- Never use `var`
- Use `const` by default; only use `let` when the value will be reassigned
- Use descriptive variable and function names — avoid single-letter names outside of loop counters
- Use `addEventListener` — never use inline event handlers (`onclick=""`)
- Select elements with `data-*` attributes for JS, not classes or IDs
- Keep functions small and single-purpose
- Add a comment above any non-obvious logic
- Indent with **2 spaces**

**Example:**
```js
const submitBtn = document.querySelector('[data-action="submit-form"]');

const handleSubmit = (e) => {
  e.preventDefault();
  // Validate before sending
  const isValid = validateForm();
  if (!isValid) return;
  sendFormData();
};

submitBtn.addEventListener('click', handleSubmit);
```

---

## File Formatting

- **Encoding:** UTF-8
- **Line endings:** LF (Unix-style)
- **Trailing whitespace:** none
- **Newline at end of file:** always
- **Max line length:** 100 characters (soft limit)

---

## Comments

- Write comments to explain **why**, not **what** — the code shows what, comments explain intent
- Use `// TODO:` for known issues to address later
- Use `// NOTE:` for important context a future reader needs
- Remove commented-out dead code before committing

---

## Accessibility Baseline

Every component must meet these minimums:

- [ ] Keyboard navigable (Tab, Enter, Escape where appropriate)
- [ ] Sufficient color contrast (4.5:1 for text, 3:1 for UI elements)
- [ ] Focus styles visible and styled (never `outline: none` without a replacement)
- [ ] ARIA labels on icon-only buttons and interactive elements without visible text
- [ ] No content conveyed by color alone
