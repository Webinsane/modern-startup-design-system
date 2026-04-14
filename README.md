# Modern Startup App

A complete design system for building SaaS dashboards, booking platforms, and startup applications. 29 components, 72 avatar assets, full dark mode support, and a 3-layer token architecture that re-skins with a single variable change.

## Quick Start

### 1. Copy into your project

```bash
cp -r modern-startup-app/ your-project/design-system/
```

### 2. Link the tokens

```html
<link rel="stylesheet" href="design-system/tokens/tokens.css">
```

### 3. Tell your AI tool

**Claude Code:**
> Read design-system/SKILL.md and use it as the design system for all frontend work in this project.

**Cursor:** Add to your `.cursorrules`:
> When building frontend UI, read design-system/SKILL.md first. Use only the tokens from design-system/tokens/tokens.css. Follow the component specs in design-system/components/.

**Any AI:** Point it at SKILL.md — it contains the full design philosophy, token reference, component index, and strict rules.

### 4. Build something

```
Build me a dashboard with a sidebar nav, stats cards row,
a data table showing recent orders, and a filter bar.
```

The AI will use the tokens, follow the component specs, and produce consistent output.

## What's Included

| Category | Count | Details |
|----------|-------|---------|
| Components | 29 | Buttons, cards, tables, forms, modals, navigation, schedule cards, toggles, alerts, toasts, and more |
| Design tokens | 100+ | Colors, typography, spacing, shadows, motion, layout — all as CSS variables |
| Avatars | 72 | Two series of photo avatars (a01–a36, b01–b36) |
| Examples | 4 | Design system showcase, dashboard demo, doctor dashboard, doctor appointments |

## Key Features

- **3-layer token architecture** — Raw palette → Brand slots → Semantic tokens. Change `--brand-secondary` once and the entire UI re-skins.
- **Dark mode built-in** — Add `data-theme="dark"` to `<html>` and everything adapts.
- **No framework dependency** — Pure CSS custom properties + semantic HTML. Works with any stack.
- **Mobile-first responsive** — Breakpoints at 640px, 1024px. All components stack gracefully.

## File Reference

| File | Purpose |
|------|---------|
| `SKILL.md` | AI entry point — read this first |
| `tokens/tokens.css` | All design values as CSS custom properties |
| `tokens/tokens.json` | Same values in JSON for programmatic use |
| `components/*.md` | Detailed spec per UI pattern (HTML, tokens, states, responsive, accessibility) |
| `examples/*.html` | Working implementations — the source of truth alongside component specs |
| `assets/avatars/` | 72 ready-to-use avatar photos |

## Customizing

Edit `tokens/tokens.css` Layer 2 (Brand Slots) to re-skin:

```css
:root {
  --brand:            #your-color;    /* Primary brand */
  --brand-secondary:  #your-color;    /* Interactive accent */
  --brand-accent:     #your-color;    /* Highlights */
}
```

All components automatically pick up the change through semantic token cascade.
