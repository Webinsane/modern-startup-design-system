# Toasts

## Overview
Floating notification toasts in light and dark themes, across all semantic types (success, error, warning, info). Appear temporarily to confirm actions or surface system messages. Compact variant available for brief confirmations.

## Structure
```html
<div class="toast toast--success">
  <i data-lucide="check-circle" class="toast__icon"></i>
  <div class="toast__content">
    <strong class="toast__title">Booking confirmed</strong>
    <p class="toast__desc">You'll receive a confirmation email shortly.</p>
  </div>
  <button class="toast__close">&times;</button>
</div>
```

### Variants
```html
<!-- Success -->
<div class="toast toast--success">...</div>

<!-- Error -->
<div class="toast toast--error">...</div>

<!-- Warning -->
<div class="toast toast--warning">...</div>

<!-- Compact (no description) -->
<div class="toast toast--success toast--compact">
  <i data-lucide="check-circle" class="toast__icon"></i>
  <div class="toast__content">
    <strong class="toast__title">Saved</strong>
  </div>
  <button class="toast__close">&times;</button>
</div>

<!-- Dark theme -->
<div class="toast toast--success toast--dark">...</div>
```

### With Action Link
```html
<div class="toast toast--success">
  <i data-lucide="check-circle" class="toast__icon"></i>
  <div class="toast__content">
    <strong class="toast__title">Booking confirmed</strong>
    <div class="toast__actions">
      <a href="#" class="toast__link">View details</a>
      <a href="#" class="toast__link toast__link--bold">Undo</a>
    </div>
  </div>
  <button class="toast__close">&times;</button>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Toast | background | `var(--color-white)` |
| Toast | border-radius | `var(--radius-lg)` |
| Toast | box-shadow | `var(--shadow-lg)` |
| Toast | padding | `var(--space-md)` |
| Dark toast | background | `var(--color-black)` |
| Dark toast | color | `var(--color-white)` |
| Title | font-weight | `600` |
| Description | color | `var(--color-text-secondary)` |
| Link | color | `var(--color-primary)` |
| Close | color | `var(--color-text-muted)` |

## Layout Rules
- Toast is a flex row: icon, content (flex: 1), close button
- Position toasts in a fixed container (top-right or bottom-right)
- Stack multiple toasts vertically with `var(--space-sm)` gap
- Auto-dismiss after 4-5 seconds, or persist until manually closed for errors
- Compact variant omits the description for shorter height

## Accessibility
- Use `role="status"` and `aria-live="polite"` for the toast container
- Close button should have `aria-label="Dismiss"`
- Ensure sufficient display time for screen reader announcement

## Do's and Don'ts

**Do:**
- Auto-dismiss success/info toasts after a few seconds
- Keep error toasts persistent until the user dismisses them
- Use compact variant for simple confirmations ("Saved", "Copied")

**Don't:**
- Show more than 3 toasts simultaneously
- Put critical information only in toasts — they're ephemeral
- Use toasts for inline form validation
