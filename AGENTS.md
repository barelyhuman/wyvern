# Agent Guidelines for Reaper Design System

This guide provides coding agents with essential information for working on the Reaper Design System - a minimal, theme-first Tailwind CSS v4 component library.

## Quick Reference

### Project Overview
- **Type**: Tailwind CSS v4 Design System Reference Library
- **Purpose**: Copy-paste component library (not a published package)
- **Package Manager**: PNPM v10.19.0+
- **Build System**: Config-less Tailwind CSS v4 with semantic CSS variables

## Build & Development Commands

### Core Commands
```bash
# Install dependencies
pnpm install

# Start development server (serves docs/)
pnpm preview

# Build CSS (when implemented)
pnpm build:css

# Run all checks
pnpm install && pnpm preview
```

### Testing
- **No testing framework is currently configured**
- Manual testing via `pnpm preview` and visual inspection
- Components are tested by viewing `docs/index.html` at http://localhost:3000

### Linting & Formatting
- **No ESLint or Prettier configured** - project uses minimal tooling approach
- Follow existing code patterns in `docs/index.html` for consistency
- HTML formatting should be clean and readable

## Code Style Guidelines

### HTML Structure & Formatting
```html
<!-- Good: Clean indentation, semantic structure -->
<div class="bg-transparent border border-border p-8 mb-3 flex items-center gap-3 flex-wrap">
    <button class="px-3 py-1.5 bg-white text-black border border-white text-sm font-normal cursor-pointer transition-all hover:bg-text-primary hover:border-text-primary">
        Default
    </button>
</div>

<!-- Bad: Poor formatting, no semantic meaning -->
<div class="wrapper"><btn class="btn-primary">Click</btn></div>
```

### Tailwind CSS Class Conventions

#### ✅ Required Patterns
- **Use actual Tailwind utility classes only** - NO custom CSS helper classes
- **Semantic spacing**: `px-3 py-1.5`, `mb-3`, `gap-3`
- **Consistent sizing**: `text-sm`, `text-base`, `text-xl`
- **Transition classes**: `transition-all hover:bg-text-primary`
- **Theme-based colors**: Use semantic color variables like `bg-text-primary`, `border-border`

#### ❌ Avoid These Patterns
```html
<!-- Bad: Custom CSS classes -->
<button class="btn btn-primary">Click</button>

<!-- Good: Pure Tailwind utilities -->
<button class="px-3 py-1.5 bg-white text-black border border-white text-sm font-normal cursor-pointer transition-all">
    Click
</button>
```

### CSS Theme Variables

#### Semantic Color System
```css
@theme {
  --base: #181819;        /* background */
  --text: #efefef;        /* primary text */
  --text-secondary: #737373;  /* secondary text */
  --text-muted: #525252;      /* muted text */
  --border: #262626;          /* border color */
  --accent: /* ... */         /* accent colors */
  --surface: /* ... */        /* surface colors */
}
```

#### Variable Naming Rules
- Use semantic names: `--text`, `--border`, `--surface` (not `--gray-600`)
- Follow existing convention: `--text-primary`, `--text-secondary`, `--text-muted`
- Avoid color-specific names: Use `--accent` not `--blue`

### Component Structure

#### Component Documentation
Every component should include:
```html
<section id="component-name" class="mb-20">
    <h2 class="text-xl font-normal mb-2 text-text-primary">Component Name</h2>
    <p class="text-text-secondary text-sm mb-10 font-light">Brief description.</p>
    
    <!-- Visual examples -->
    <div class="bg-transparent border border-border p-8 mb-3 flex items-center gap-3 flex-wrap">
        <!-- Component variants here -->
    </div>
    
    <!-- Code snippet -->
    <div class="bg-transparent border-l border-border pl-4 py-3 mb-12 font-mono text-[13px] overflow-x-auto text-text-secondary leading-[1.8]">
        <!-- HTML markup here -->
    </div>
</section>
```

#### Component Variants
- **Size variants**: Small (`px-2.5 py-1`), Default (`px-3 py-1.5`), Large (`px-[18px] py-2.5`)
- **State variants**: Default, hover, focus, disabled
- **Type variants**: Default, outline, ghost, filled

## File Organization

### Directory Structure
```
/Users/sid/lab/components/
├── docs/
│   └── index.html          # Component showcase & documentation
├── components/             # Component reference files (create as needed)
├── package.json           # Project configuration
├── README.md              # Human & AI documentation
└── AGENTS.md              # This file - agent guidelines
```

### Component Files (when creating new components)
- Place in `/components/{component-name}/`
- Include `README.md` with variants and usage examples
- Keep components as pure HTML with Tailwind classes

## Error Handling & Debugging

### Common Issues
1. **Missing dependencies**: Run `pnpm install`
2. **Port conflicts**: Preview server runs on default port (usually 3000)
3. **CSS not updating**: No build step required - refresh browser
4. **Tailwind classes not working**: Check for typos in class names

### Debugging Steps
```bash
# 1. Check package installation
pnpm list

# 2. Verify preview server
pnpm preview

# 3. Test in browser
open http://localhost:3000
```

## Naming Conventions

### Files & Directories
- Use `kebab-case` for file and directory names
- Component directories: `/components/button/`, `/components/form-input/`
- Documentation files: `README.md`, `AGENTS.md`

### CSS Variables & Classes
- Theme variables: `--text-primary`, `--border-subtle`
- Component variants: Use descriptive Tailwind classes only
- No custom CSS classes - pure utility approach

### HTML Elements
- Use semantic HTML5 elements: `<button>`, `<input>`, `<section>`
- Meaningful class ordering: layout → spacing → colors → typography → interactions

## Dependencies & Tools

### Core Dependencies
- `@tailwindcss/cli@^4.1.18` - Tailwind CSS v4 CLI
- `tailwind@^4.0.0` - Core Tailwind CSS
- `serve@^14.2.5` - Static file serving (dev dependency)

### Development Workflow
1. Edit `docs/index.html` for new components
2. Use `pnpm preview` for live testing
3. Follow existing component patterns
4. Ensure copy-paste friendly markup
5. Update documentation as needed

## Special Requirements

### Copy-Paste Philosophy
- All components must use **pure Tailwind utility classes**
- No build step required for component usage
- Users should be able to copy class strings directly
- Avoid project-specific abstractions

### Theme-First Approach
- Always use semantic CSS variables for colors
- Maintain dark theme compatibility
- Keep theme variables minimal and focused
- Test with different theme configurations

---

## Quick Checklist for Agents

Before committing changes:
- [ ] Used only Tailwind utility classes (no `.btn`, `.card` etc.)
- [ ] Followed semantic color variable naming
- [ ] Added component to docs/index.html if new
- [ ] Tested with `pnpm preview`
- [ ] Maintained existing code formatting patterns
- [ ] Ensured copy-paste friendly markup
- [ ] Updated relevant documentation

## Resources

- **Project README**: `/Users/sid/lab/components/README.md`
- **Live Preview**: `pnpm preview` → http://localhost:3000
- **Tailwind CSS v4 Docs**: https://tailwindcss.com/docs
- **Package Manager**: PNPM (required)