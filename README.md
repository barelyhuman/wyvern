# wyvern

> Minimal, theme-first Tailwind CSS v4 design system

A curated collection of copy-paste ready UI components built with pure Tailwind CSS utilities. Zero config, zero build step, maximum flexibility.

---

## TL;DR ✅

- View all components at `docs/index.html` via `pnpm preview`
- Copy the `@theme` variables to set base colors
- Copy HTML markup with Tailwind classes directly into your project

---

## Quick Start

1. **Preview components locally:**
```bash
pnpm install
pnpm preview
# Visit http://localhost:3000
```

2. **Copy theme variables to your project:**
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

3. **Copy components:** Browse `docs/index.html`, find the component you need, and copy the HTML markup with Tailwind classes.

## What this is

- **Copy-paste component library** - Browse components in your browser, copy the HTML markup
- **Pure Tailwind utilities** - All components use actual Tailwind classes (no custom CSS)
- **Theme-driven** - Semantic CSS variables make theming simple and consistent
- **Zero build step** - No compilation required, works with any Tailwind CSS v4 setup
- **Reference implementation** - Not a published package, designed for copying into your project

## Component Philosophy

### ✅ What we do
- Use only **real Tailwind utility classes** like `px-3 py-1.5 bg-white border border-gray-200`
- Semantic CSS variables for colors: `--color-text-primary`, `--color-border`
- Copy-paste friendly markup that works anywhere
- Consistent spacing and sizing patterns

### ❌ What we avoid
- Custom CSS helper classes like `.btn`, `.card`, `.input`
- Complex build processes or dependencies
- Framework-specific implementations
- Hardcoded colors instead of theme variables

## Available Commands

```bash
# Install dependencies
pnpm install

# Start preview server (serves docs/index.html)
pnpm preview

# View components at http://localhost:3000
```

## Project Structure

```
wyvern/
├── docs/
│   └── index.html          # Component showcase & documentation
├── package.json            # Minimal project config (only serve dependency)
├── README.md              # This file
└── AGENTS.md              # Guidelines for AI coding agents
```

## Theming & Customization

### CSS Variables
All colors use semantic CSS variables that you can override:

```css
@theme {
  /* Core theme variables */
  --color-bg: #181819;                    /* page background */
  --color-text-primary: #efefef;          /* primary text */
  --color-text-secondary: #737373;        /* secondary text */
  --color-text-muted: #525252;           /* muted text */
  --color-border: #262626;                /* border color */
  --color-surface-primary: #efefef;       /* button backgrounds */
  --color-surface-inverse: #181819;       /* inverted surfaces */
  
  /* Semantic state colors */
  --color-success: #22c55e;               /* success states */
  --color-warning: #eab308;               /* warning states */
  --color-error: #ef4444;                 /* error states */
}
```

### Variable Naming Convention
- Use **semantic names**: `--color-text-primary` instead of `--gray-100`
- Follow the pattern: `--color-[purpose]-[variant]`
- Keep it simple: prefer `--color-accent` over `--color-blue-500`

---

## For AI Agents 🤖

### Project Metadata
```json
{
  "name": "wyvern",
  "type": "tailwind-design-system-reference",
  "framework": "none",
  "build_system": "none",
  "package_manager": "pnpm",
  "entry_point": "docs/index.html",
  "preview_command": "pnpm preview",
  "testing": "manual",
  "linting": "none"
}
```

### Key Requirements for Agents
- **Use only Tailwind utility classes** - Never create custom CSS classes like `.btn` or `.card`
- **All components live in `docs/index.html`** - Single file approach for simplicity
- **Test changes with `pnpm preview`** - Visual testing at http://localhost:3000
- **Follow semantic CSS variable naming** - Use `--color-text-primary` not `--gray-100`
- **Maintain copy-paste philosophy** - Users should be able to copy HTML markup directly

### Development Workflow
1. Edit `docs/index.html` to add/modify components
2. Run `pnpm preview` to test changes locally
3. Ensure all components use pure Tailwind classes
4. Update documentation as needed

> **Important**: See `AGENTS.md` for detailed guidelines on code style, conventions, and development practices.

---

## License

[MIT](/LICENSE)
