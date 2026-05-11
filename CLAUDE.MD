# CLAUDE.md — Instructions for Claude

This file tells you (Claude) how to use this repository when assisting in a coding session.

---

## Your Role When This Repo Is Referenced

When the user references this repo (e.g. "check my standards", "use my component library", "follow my patterns"), you should:

1. **Read this file first**
2. **Read `/standards/coding-standards.md`** to understand the rules
3. **Read `/standards/naming-conventions.md`** for naming patterns
4. **Browse `/components/`** for any existing components relevant to the task
5. **Match existing patterns exactly** — do not invent new conventions

---

## How to Use Components

Each component lives in its own folder under `/components/` and contains:
- `component.html` — markup structure
- `component.css` — scoped styles
- `component.js` — behavior (if needed)
- `README.md` — props/options, usage example, variations

When the user asks you to build something, **check if a matching component already exists first**. If it does, use it as the base. If it doesn't, use `/components/_template/` as your starting point and follow the same structure.

---

## How to Write New Code

- Follow every rule in `/standards/coding-standards.md` — no exceptions
- Use naming patterns from `/standards/naming-conventions.md`
- Use CSS patterns from `/standards/styling-guide.md`
- Use folder structure from `/standards/folder-structure.md`
- Never introduce a new convention without flagging it to the user first

---

## When Adding a New Component

If the user asks you to add a component to the library:
1. Scaffold the folder using `/components/_template/` as the model
2. Write all four files: `component.html`, `component.css`, `component.js`, `README.md`
3. Fill in the component README fully (see template)
4. Tell the user exactly where the files should go in the repo

---

## Communication Style

When working from this repo:
- **Flag conflicts** — if a user's request conflicts with their own standards, point it out before proceeding
- **Be explicit** — tell the user which component or standard you're referencing ("Using your Button component from `/components/ui/button/`")
- **Suggest additions** — if you write something reusable that isn't in the library yet, suggest adding it
- **Ask before inventing** — if no standard covers a situation, ask the user how they want to handle it rather than guessing

---

## Repo Maintenance Tips (for the user)

- Keep `README.md` files updated in every component folder
- When you establish a new pattern, add it to the relevant standards file
- Use consistent commit messages: `feat`, `fix`, `docs`, `refactor`, `style`
