# Tags & Badges

## Overview
Small labeling elements used to indicate status (Pending, Confirmed, Alert), categories (Hot Desk, Wi-fi), and metadata. Also includes status dots on conversation lists (Replied, Open, Closed).

## Quick Reference

| Need | Class | Token pair |
|------|-------|------------|
| Pending/waiting | `tag--pending` | `--color-pending-light` bg, `--color-pending-on-light` text |
| Confirmed/active | `tag--confirmed` | `--color-success-light` bg, `--color-success-text` text |
| Alert/error/overdue | `tag--alert` | `--color-error-light` bg, `--color-error` text |
| Closed/archived | `tag--closed` | `--color-surface-alt` bg, `--color-text-secondary` text |
| Replied (conversation) | `status--replied` | `--color-primary-light` bg, `--color-primary` text |
| Open (conversation) | `status--open` | `--color-success-light` bg, `--color-success` text |
| Category/filter | `tag` | `--color-bg` bg, `--color-text-secondary` text, border |

## Structure
```html
<!-- Status tag (pill) -->
<span class="tag tag--pending">Pending</span>
<span class="tag tag--confirmed">Active</span>
<span class="tag tag--alert">Overdue</span>
<span class="tag tag--closed">Closed</span>

<!-- Category tag -->
<span class="tag">Hot Desk</span>

<!-- Status indicator with dot -->
<span class="status status--replied"><span class="status__dot"></span> Replied</span>
<span class="status status--open"><span class="status__dot"></span> Open</span>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| All tags/badges | font-size | `var(--text-xs-size)` |
| All tags/badges | font-weight | `var(--text-xs-weight)` — 500 |
| All tags/badges | border-radius | `var(--radius-full)` |
| All tags/badges | padding | `var(--space-2xs) var(--space-xs)` |
| Pending | background | `var(--color-pending-light)` |
| Pending | color | `var(--color-pending-on-light)` |
| Confirmed | background | `var(--color-success-light)` |
| Confirmed | color | `var(--color-success-text)` |
| Alert | background | `var(--color-error-light)` |
| Alert | color | `var(--color-error)` |
| Warning (tooltip) | background | `var(--color-warning)` |
| Warning (tooltip) | color | `var(--color-text-inverse)` |
| Closed | background | `var(--color-surface-alt)` |
| Closed | color | `var(--color-text-secondary)` |
| Category tag | background | `var(--color-bg)` |
| Category tag | color | `var(--color-text-secondary)` |
| Category tag | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Replied status | background | `var(--color-primary-light)` |
| Replied status | color | `var(--color-primary)` |
| Open status | background | `var(--color-success-light)` |
| Open status | color | `var(--color-success)` |

## Layout Rules
- Tags/badges are inline elements
- Gap between multiple tags: `var(--space-xs)` (8px)
- Vertically centered with adjacent text
- Do not wrap — truncate if needed

## States

**Default:**
Pill-shaped with semantic background color and matching text.

**Hover:**
Category tags may show subtle background darken for filterable tags.

**Interactive variant:**
When tags are removable, add an × icon with `var(--space-2xs)` gap.

## Responsive Behavior

**Mobile (< 640px):**
Wrap to multiple lines if needed. Maintain same sizing.

**Desktop (> 1024px):**
Inline row of tags with `var(--space-xs)` gap.

## Accessibility
- **Role:** Use `<span>` for decorative, `role="status"` for live status updates
- **Screen reader:** Include text content; dot indicators need `aria-label`
- **Color:** Never rely on color alone — always include text label

## Variants

**Status badge (with dot):**
Includes a small colored dot (6px) before the label.

**Tooltip badge (Warning):**
Dark background with white text, appears as a floating tooltip with a small arrow.

**Count badge:**
Numeric value in a small circle, used on navigation items.

## Do's and Don'ts

**Do:**
- Use consistent status colors across the app
- Keep tag text short (1-2 words)
- Group related tags together

**Don't:**
- Create new status colors beyond the defined set
- Use tags for long descriptive text
- Mix badge styles in the same context
