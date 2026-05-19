# Snippets

Small, reusable code patterns that don't warrant their own component folder. Copy-paste these directly into your projects.

> **For Claude:** These are short patterns, not full components. Use them as building blocks or reference patterns when writing code.

---

## CSS Snippets

### Visually Hidden (Accessible)
Hides content visually while keeping it available to screen readers.
```css
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

### Truncate Text with Ellipsis
```css
.truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```

### Aspect Ratio Box
```css
.aspect-ratio-16-9 {
  aspect-ratio: 16 / 9;
  width: 100%;
}
```

### Flex Center
```css
.flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Container
```css
.container {
  width: 100%;
  max-width: var(--container-lg);
  margin-inline: auto;
  padding-inline: var(--space-4);
}
```

---

## JS Snippets

### Debounce
```js
const debounce = (fn, delay = 300) => {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
};
```

### Trap Focus in Modal
```js
const trapFocus = (el) => {
  const focusable = el.querySelectorAll(
    'a, button, input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );
  const first = focusable[0];
  const last = focusable[focusable.length - 1];

  el.addEventListener('keydown', (e) => {
    if (e.key !== 'Tab') return;
    if (e.shiftKey) {
      if (document.activeElement === first) {
        e.preventDefault();
        last.focus();
      }
    } else {
      if (document.activeElement === last) {
        e.preventDefault();
        first.focus();
      }
    }
  });
};
```

### Get All `data-*` Attributes as an Object
```js
const getDataAttrs = (el) => {
  return Object.fromEntries(
    Object.entries(el.dataset)
  );
};
```

---

*Add new snippets here as you discover reusable patterns.*
