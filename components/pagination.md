# Pagination

## Overview
Page navigation control with Previous/Next buttons, numbered page items, active state, and an ellipsis for truncated ranges. Two variants: **full** (text buttons + numbers + ellipsis) and **compact** (icon-only arrows + numbers). On mobile, the full variant collapses — middle page numbers are hidden to show only the active page, one neighbor, and the last page. Previous/Next text becomes chevron icons.

## Structure

### Full Variant
```html
<nav class="pagination" aria-label="Page navigation">
  <a class="pagination__btn" aria-label="Previous page">
    <i data-lucide="chevron-left" class="pagination__btn-icon"></i>
    <span class="pagination__btn-text">Previous</span>
  </a>
  <a class="pagination__item pagination__item--active">1</a>
  <a class="pagination__item">2</a>
  <a class="pagination__item pagination__item--hide-mobile">3</a>
  <span class="pagination__ellipsis">...</span>
  <a class="pagination__item pagination__item--hide-mobile">15</a>
  <a class="pagination__item pagination__item--hide-mobile">16</a>
  <a class="pagination__item">17</a>
  <a class="pagination__btn" aria-label="Next page">
    <i data-lucide="chevron-right" class="pagination__btn-icon"></i>
    <span class="pagination__btn-text">Next</span>
  </a>
</nav>
```

### Compact Variant
```html
<nav class="pagination" aria-label="Page navigation">
  <a class="pagination__item" aria-label="Previous"><i data-lucide="chevron-left"></i></a>
  <a class="pagination__item pagination__item--active">1</a>
  <a class="pagination__item">2</a>
  <a class="pagination__item" aria-label="Next"><i data-lucide="chevron-right"></i></a>
</nav>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | display | flex |
| Container | gap | `var(--space-xs)` (desktop), `var(--space-2xs)` (mobile) |
| Page item | width / height | 36px |
| Page item | font-size | `var(--text-body-size)` |
| Page item | font-weight | 500 |
| Page item | color | `var(--color-text-primary)` |
| Page item | background | `var(--color-surface)` |
| Page item | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Page item | border-radius | `var(--radius-md)` |
| Page item hover | background | `var(--color-surface-alt)` |
| Active page item | background | `var(--color-primary)` |
| Active page item | color | `var(--color-text-inverse)` |
| Active page item | border-color | `var(--color-primary)` |
| Active hover | background | `var(--color-primary-hover)` |
| Page item icon | size | 16px |
| Ellipsis | width / height | 36px |
| Ellipsis | color | `var(--color-text-muted)` |
| Prev/Next button | height | 36px |
| Prev/Next button | padding | `var(--space-xs) var(--space-md)` |
| Prev/Next button | font-size | `var(--text-body-size)` |
| Prev/Next button | font-weight | 500 |
| Prev/Next button | border-radius | `var(--radius-md)` |
| Prev/Next button | background | `var(--color-surface)` |
| Prev/Next button | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Prev/Next button hover | background | `var(--color-surface-alt)` |

## Layout Rules
- Flex row with centered items
- All items are 36px square (numbers) or 36px tall (prev/next buttons)
- Prev/Next buttons have text padding on desktop, become 36px square icon-only on mobile
- Ellipsis is non-interactive, same size as page items

## States

**Default:** Outlined page items with primary text.

**Hover:** Subtle background shift to `var(--color-surface-alt)`.

**Active:** Filled `var(--color-primary)` background with inverse text. Active hover uses `var(--color-primary-hover)`.

**Disabled (first/last page):** Reduced opacity, `pointer-events: none`. Apply `pagination__btn--disabled` class.

## Responsive Behavior

**Mobile (< 640px):**
- Gap reduces from `var(--space-xs)` to `var(--space-2xs)`
- Pages marked with `.pagination__item--hide-mobile` are hidden (`display: none`)
- Ellipsis marked with `.pagination__ellipsis--hide-mobile` are hidden
- Keep visible: active page, one neighbor, and the last page (typically 2–3 numbers total)
- Previous/Next text (`.pagination__btn-text`) is hidden, chevron icons (`.pagination__btn-icon`) are shown instead
- Prev/Next buttons become 36px square icon-only buttons

### How to mark items for mobile hiding
Add `pagination__item--hide-mobile` to page numbers that should collapse on mobile. Typically hide middle-range numbers and keep:
- The active page
- One adjacent page (next or previous)
- The last page number

**Desktop (> 640px):**
Full layout — all numbers visible, Previous/Next show text labels, chevron icons hidden.

## Accessibility
- **Container:** `<nav>` with `aria-label="Page navigation"`
- **Active:** `aria-current="page"` on the active item
- **Prev/Next:** `aria-label="Previous page"` and `aria-label="Next page"`
- **Keyboard:** `Tab` through all items, `Enter`/`Space` to activate
- **Disabled:** `aria-disabled="true"` on disabled prev/next buttons

## Do's and Don'ts

**Do:**
- Show at most 2–3 page numbers on mobile to prevent cramping
- Use ellipsis to indicate skipped ranges
- Always show the active page number
- Wrap Previous/Next button text in `.pagination__btn-text` and include a `.pagination__btn-icon` chevron for mobile fallback

**Don't:**
- Show more than 7 page numbers at once (even on desktop)
- Hide Previous/Next buttons — always keep them accessible
- Use pagination for fewer than 3 pages — show all content instead
