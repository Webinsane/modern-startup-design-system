# Alerts

## Overview
Inline notification banners in four semantic variants with icon, title, optional description, and close button. Used for page-level or section-level feedback messages.

## Structure
```html
<div class="alert alert--success">
  <i data-lucide="check-circle" class="alert__icon"></i>
  <div class="alert__body">
    <strong class="alert__title">Success</strong>
    <p class="alert__desc">Your changes have been saved.</p>
  </div>
  <button class="alert__close">&times;</button>
</div>
```

### Variants
```html
<!-- Success -->
<div class="alert alert--success">...</div>

<!-- Error -->
<div class="alert alert--error">...</div>

<!-- Warning -->
<div class="alert alert--warning">...</div>

<!-- Info -->
<div class="alert alert--info">...</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Alert | border-radius | `var(--radius-lg)` |
| Alert | padding | `var(--space-md)` |
| Success | background | `var(--color-success-light)` |
| Success | border-left | `var(--color-success)` |
| Error | background | `var(--color-error-light)` |
| Error | border-left | `var(--color-error)` |
| Warning | background | `var(--color-warning-light)` |
| Warning | border-left | `var(--color-warning)` |
| Info | background | `var(--color-info-light)` |
| Info | border-left | `var(--color-info)` |
| Title | font-weight | `600` |
| Description | color | `var(--color-text-secondary)` |
| Close button | color | `var(--color-text-muted)` |

## Layout Rules
- Alert is a flex row: icon, body (flex: 1), close button
- Icon is vertically centered with the title
- Description is optional — alert works with title only
- Full width within its container
- Stack multiple alerts with `var(--space-sm)` gap

## Accessibility
- Use `role="alert"` for urgent messages (errors, warnings)
- Use `role="status"` for informational or success messages
- Close button should have `aria-label="Dismiss"`

## Do's and Don'ts

**Do:**
- Use the correct semantic variant for the message type
- Keep titles concise (2-5 words)
- Provide a close button for dismissible alerts

**Don't:**
- Stack more than 3 alerts at once
- Use alerts for inline field validation — use form error states instead
- Put interactive elements (links, buttons) in the description
