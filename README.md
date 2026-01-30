# wyvern

> Tailwind v4 and config-less

Minimal, theme-first collection of reference components built with Tailwind CSS. This repo is intentionally small and config-less so you can copy or fork components into your project quickly.

---

## TL;DR ✅

- Copy the `@theme` variables to set base colors.
- Use the components in `/components` as examples — copy markup and adapt.

---

## Quickstart (3 steps)

1. Add or override the project theme variables:

```css
@theme {
  --color-bg: #181819;
  --color-text-primary: #efefef;
  --color-text-secondary: #737373;
  --color-text-muted: #525252;
  --color-border: #262626;
  --color-surface-primary: #efefef;
  --color-surface-inverse: #181819;
  --color-success: #22c55e;
  --color-warning: #eab308;
  --color-error: #ef4444;
}
```

2. Copy a component from `/components` into your app and update classes or variables.
3. Run the preview commands:

```bash
pnpm preview
```

## For humans 🔧

### What this repo is

- A curated set of UI reference components and examples using **actual Tailwind utility classes**.
- Not a published package — intended as copy-paste-ready building blocks.
- **All component examples use real Tailwind classes (not helper CSS classes)** so you can directly copy the class strings into your project.

### Theming & conventions

- Theme is semantic and controlled by CSS variables (e.g., `--base`, `--text`).
- Prefer semantic names for new variables: `--muted`, `--accent`, `--surface`, `--inverse`.
- Keep components minimal and utility-driven so they are easy to port.
- **Critical**: Components must use Tailwind utility classes only (e.g., `px-3 py-1.5 bg-white`) — no custom CSS helper classes (e.g., `.btn`, `.card`).

### Contributing

- Keep markup and styles plain — avoid project-specific build steps.

---

## For AI agents 🤖

This section provides a compact, machine-readable summary to help agents index, run, and reason about the project.

```json
{
  "name": "wyvern",
  "type": "design-system-reference",
  "language": ["html", "css", "tailwind"],
  "entry_points": ["/index.html"],
  "preview_command": "pnpm preview",
  "theme_variables": ["--base", "--text", "--muted", "--accent", "--surface"],
  "keywords": [
    "tailwind",
    "design system",
    "theme",
    "components",
    "config-less"
  ]
}
```

Notes for agents:

- If asked to change theme, update `@theme` variables and run `pnpm preview` to validate visual output.
- When creating or updating a component, prefer semantic CSS variable names and include a brief README describing variants.
- **IMPORTANT**: All components must use actual Tailwind CSS utility classes (e.g., `px-3 py-1.5 border border-border`), NOT custom helper classes like `.btn` or `.card`. The goal is for users to copy-paste the Tailwind classes directly.

---

> **Tip:** When making programmatic changes, include a short natural-language commit message and update the component's README with an example HTML snippet.

---

## License

[MIT](/LICENSE)
