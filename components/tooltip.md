# Tooltip

## Overview
Small floating label that appears on hover to provide additional context. Dark background with white text, positioned relative to a trigger element. Four directional variants: top (default), bottom, left, right.

## Structure
```html
<span class="tooltip-wrap">
  <span class="tooltip tooltip--top">Tooltip text here</span>
  <button>Trigger element</button>
</span>
```

### Directional Variants
```html
<!-- Top (default — class is optional) -->
<span class="tooltip-wrap">
  <span class="tooltip tooltip--top">Top tooltip</span>
  <button>Hover me</button>
</span>

<!-- Bottom -->
<span class="tooltip-wrap">
  <span class="tooltip tooltip--bottom">Bottom tooltip</span>
  <button>Hover me</button>
</span>

<!-- Left -->
<span class="tooltip-wrap">
  <span class="tooltip tooltip--left">Left tooltip</span>
  <button>Hover me</button>
</span>

<!-- Right -->
<span class="tooltip-wrap">
  <span class="tooltip tooltip--right">Right tooltip</span>
  <button>Hover me</button>
</span>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Wrapper | display | `inline-flex` |
| Wrapper | position | `relative` |
| Tooltip | background | `var(--color-black)` |
| Tooltip | color | `var(--color-white)` |
| Tooltip | font-size | `var(--text-small-size)` |
| Tooltip | font-weight | `500` |
| Tooltip | line-height | `1.4` |
| Tooltip | padding | `var(--space-xs) var(--space-sm)` |
| Tooltip | border-radius | `var(--radius-md)` |
| Tooltip | max-width | `200px` |
| Tooltip | z-index | `var(--z-tooltip)` |
| Arrow | size | `5px` (border trick) |
| Arrow | color | `var(--color-black)` (matches tooltip bg) |
| Gap (tooltip to trigger) | spacing | `var(--space-xs)` |

## States

**Default (hidden):**
`opacity: 0`, `pointer-events: none`. Tooltip is invisible and non-interactive.

**Hover (visible):**
When `.tooltip-wrap` is hovered, tooltip transitions to `opacity: 1` via `var(--transition-fast)`.

## Layout Rules
- Tooltip is always a child of `.tooltip-wrap`, positioned absolutely
- The trigger element (button, tag, icon, etc.) is a sibling of the tooltip inside the wrapper
- Arrow is rendered via `::after` pseudo-element using the CSS border trick
- `width: max-content` keeps tooltip sized to its text, capped at `max-width: 200px`
- `text-align: center` for short labels
- `pointer-events: none` — tooltip cannot be hovered or clicked

## Positioning
- **Top:** anchored above the trigger, horizontally centered
- **Bottom:** anchored below the trigger, horizontally centered
- **Left:** anchored to the left of the trigger, vertically centered
- **Right:** anchored to the right of the trigger, vertically centered

## Accessibility
- Tooltips are visual-only hover hints — they are not keyboard-accessible by default
- For accessible tooltips on interactive elements, add `aria-describedby` on the trigger pointing to the tooltip's `id`, and use `role="tooltip"` on the tooltip element
- Do not put essential information only in tooltips — they should supplement, not replace, visible labels

## Do's and Don'ts

**Do:**
- Use on icon-only buttons to clarify their action
- Use on status tags to provide extra context
- Keep text short — one line ideally, two max
- Use `tooltip--top` as the default direction

**Don't:**
- Put interactive content (links, buttons) inside tooltips
- Use tooltips on touch-only interfaces (no hover available)
- Replace visible labels with tooltips for essential information
- Nest tooltips inside other tooltips
- Use tooltips for long-form content — use a popover instead
