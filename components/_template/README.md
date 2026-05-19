# Component Name

> One-sentence description of what this component does and when to use it.

---

## Preview

Open `component.html` in a browser to see the component in isolation.

---

## Usage

Paste this markup where you want the component to appear:

```html
<div class="component-name" data-component="component-name">
  <div class="component-name__inner">
    <!-- Content here -->
  </div>
</div>
```

Include the styles and script:

```html
<link rel="stylesheet" href="path/to/component.css">
<script src="path/to/component.js" defer></script>
```

---

## Variants

| Class modifier | Description |
|----------------|-------------|
| *(base)* | Default appearance |
| `.component-name--variant` | Description of this variant |

**Example:**
```html
<div class="component-name component-name--variant">
  ...
</div>
```

---

## Options / Data Attributes

| Attribute | Values | Description |
|-----------|--------|-------------|
| `data-component="component-name"` | — | Required. Activates JS behavior |
| `data-option-name` | `value1`, `value2` | Description of what this controls |

---

## CSS Custom Properties

These properties can be overridden per-instance to customize the component:

| Property | Default | Description |
|----------|---------|-------------|
| `--_bg` | `var(--color-neutral-0)` | Background color |
| `--_text` | `var(--color-neutral-900)` | Text color |
| `--_padding` | `var(--space-4)` | Internal padding |

**Example override:**
```css
.my-context .component-name {
  --_bg: var(--color-primary-light);
}
```

---

## Accessibility

- [ ] Keyboard navigable
- [ ] Focus styles visible
- [ ] ARIA roles/labels applied
- [ ] Sufficient color contrast
- Notes on any specific accessibility considerations for this component

---

## Dependencies

- None *(or list any shared CSS tokens, other components, etc.)*

---

## Changelog

| Date | Change |
|------|--------|
| YYYY-MM-DD | Initial version |
