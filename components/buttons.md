# Buttons

## Overview
Multi-size, multi-variant buttons for all interactive actions. Organized into five categories: **Filled**, **Soft**, **Outlined**, **Ghost**, and **Text**. Each category works in both light and dark themes via semantic tokens. Supports icon-only, loading, and disabled states.

## Quick Reference

Pick **one** from each column to assemble a button:

| Emphasis | Class | When to use |
|----------|-------|-------------|
| **High** | `btn--primary` | Main CTA per section |
| **High** | `btn--dark` | Secondary emphasis |
| **High** | `btn--success` | Confirm/approve |
| **High** | `btn--error` | Delete/destructive |
| **Medium** | `btn--soft-success` | Status action (gentler) |
| **Medium** | `btn--soft-error` | Status action (gentler) |
| **Medium** | `btn--outlined` | Secondary alongside primary |
| **Low** | `btn--ghost` | Tertiary, table row actions |
| **Low** | `btn--text` | Cancel, inline actions |

| Size | Class | Height |
|------|-------|--------|
| Large | `btn--lg` | 48px |
| Medium | `btn--md` | 40px |
| Small | `btn--sm` | 34px |
| Tiny | `btn--tiny` | 28px |

**Modifiers:** `btn--full` (100% width), `btn--icon` (square icon-only), `btn--disabled`, `btn--loading`

## Structure
```html
<!-- Standard button with icon -->
<button class="btn btn--primary btn--md">
  <i data-lucide="plus"></i> Create
</button>

<!-- Icon-only button -->
<button class="btn btn--outlined btn--md btn--icon" aria-label="Edit">
  <i data-lucide="pencil"></i>
</button>

<!-- Full-width button -->
<button class="btn btn--primary btn--md btn--full">Submit</button>
```

Icons use Lucide (`<i data-lucide="...">`) placed inline before or after the label text. No wrapper spans needed.

## Size Variants

| Size | Class | Height | Padding | Icon size |
|------|-------|--------|---------|-----------|
| Large | `btn--lg` | 48px | 0 24px | 20px |
| Medium | `btn--md` | 40px | 0 20px | 18px |
| Small | `btn--sm` | 34px | 0 16px | 16px |
| Tiny | `btn--tiny` | 28px | 0 12px | 14px |

## Variant Categories

### Filled (solid background, inverse text)
High emphasis. Use for primary actions and CTAs.

| Variant | Class | Background | Use case |
|---------|-------|------------|----------|
| Primary | `btn--primary` | `--color-secondary` (blue) | Main CTA |
| Dark | `btn--dark` | `--color-primary` | Secondary emphasis |
| Accent | `btn--accent` | `--color-accent` (orange) | Promotional actions |
| Success | `btn--success` | `--color-success` (green) | Confirmations |
| Error | `btn--error` | `--color-error` (red) | Destructive actions |

### Soft (tinted background, colored text)
Medium emphasis. Gentler than filled, works well for status actions and secondary colored buttons. These use `-light` and `-mid` token pairs that remap properly in dark mode.

| Variant | Class | Background | Text |
|---------|-------|------------|------|
| Primary | `btn--soft-primary` | `--color-secondary-light` | `--color-secondary` |
| Success | `btn--soft-success` | `--color-success-light` | `--color-success` |
| Error | `btn--soft-error` | `--color-error-light` | `--color-error` |
| Warning | `btn--soft-warning` | `--color-warning-light` | `--color-warning` |

### Outlined (border, no fill)
Medium emphasis. For secondary actions alongside a filled primary.

| Variant | Class | Border | Text |
|---------|-------|--------|------|
| Default | `btn--outlined` | `--color-border` | `--color-text-primary` |
| Primary | `btn--outlined-primary` | `--color-secondary` | `--color-secondary` |
| Error | `btn--outlined-error` | `--color-error` | `--color-error` |

### Ghost (border, transparent bg)
Low emphasis. For tertiary actions, table row actions, paired with primary buttons.

| Variant | Class | Notes |
|---------|-------|-------|
| Ghost | `btn--ghost` | Border from `--color-border`, muted text |

### Text (no border, no background)
Minimal emphasis. For navigation groups, inline actions, cancel buttons.

| Variant | Class | Color | Use case |
|---------|-------|-------|----------|
| Default | `btn--text` | `--color-text-secondary` | Low-emphasis actions |
| Primary | `btn--text-primary` | `--color-secondary` | Inline links/actions |
| Error | `btn--text-error` | `--color-error` | Subtle destructive |
| Active | `btn--text-active` | `--color-secondary` on `--color-secondary-light` bg | Active item in nav groups |

## Modifiers

| Modifier | Class | Effect |
|----------|-------|--------|
| Full width | `btn--full` | 100% container width |
| Icon only | `btn--icon` | Square aspect ratio (width = height) |
| Disabled | `btn--disabled` | 0.5 opacity, no pointer events |
| Loading | `btn--loading` | Hides text, shows spinning indicator |

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| All buttons | font-family | `var(--font-body)` |
| All buttons | font-weight | `600` |
| All buttons | border-radius | `var(--radius-lg)` |
| All buttons | gap (icon to text) | `var(--space-xs)` |
| All buttons | transition | `var(--transition-fast) var(--easing-default)` |

## States

**Hover:** Each variant has its own hover — filled darkens via `-hover` tokens, soft intensifies via `-mid` tokens, outlined/text fills with subtle background. All use `var(--transition-fast)`.

**Active / Pressed:** `transform: scale(0.98)` for tactile feedback.

**Disabled:** `opacity: 0.5`, `cursor: not-allowed`, `pointer-events: none`.

**Loading:** Text becomes transparent, a CSS spinner appears centered via `::after` pseudo-element. `pointer-events: none` prevents interaction.

## Dark Theme Behavior
All variants work in dark mode without overrides because they use semantic tokens:
- Filled buttons keep their color (blue, green, red stay vivid on dark backgrounds)
- Soft buttons use `-light` / `-mid` tokens that remap to `rgba()` tints in dark mode
- Outlined/Ghost use `--color-border` and `--color-surface-active` which remap automatically
- Text buttons use `--color-text-secondary` / `--color-text-primary` which remap
- `btn--dark` flips from black-on-white to white-on-dark via `--color-primary` remapping

## Responsive Behavior

**Mobile (< 640px):** Full-width buttons in forms/CTAs (`btn--full`). Maintain size variants elsewhere.

**Desktop (> 1024px):** Inline buttons, auto width based on content.

## Accessibility
- **Role:** Native `<button>` element (no div buttons)
- **Keyboard:** `Tab` to focus, `Enter`/`Space` to activate
- **Focus visible:** 2px outline with 2px offset
- **Icon only:** Must have `aria-label`
- **Loading:** Use `aria-busy="true"`
- **Disabled:** Use `disabled` attribute, not `aria-disabled` alone

## Do's and Don'ts

**Do:**
- Use one filled button per section/form as the primary CTA
- Use soft variants for status-related actions (approve, reject, warn)
- Use outlined/ghost for secondary actions alongside a primary
- Use text variants for cancel, reset, and navigation groups
- Match icon-only buttons to their text counterparts in variant and size

**Don't:**
- Mix button sizes in the same row
- Use tiny buttons for primary CTAs
- Use filled error buttons for non-destructive actions
- Put two filled buttons of different colors side by side
- Use soft variants where filled is needed (soft is for lower emphasis)
