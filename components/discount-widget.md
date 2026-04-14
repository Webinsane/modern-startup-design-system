# Discount / Pricing Widget

## Overview
A sidebar widget for applying discount codes and displaying the total price with primary and secondary CTAs. Used on event and booking detail pages for purchase/registration flows.

## Structure
```html
<div class="widget widget--pricing">
  <div class="widget__section">
    <h3 class="widget__label">Discount code</h3>
    <div class="discount-input">
      <input type="text" class="discount-input__field" placeholder="Enter discount code">
      <button class="discount-input__apply">Apply</button>
    </div>
  </div>

  <div class="widget__total">
    <span class="widget__total-label">Total</span>
    <span class="widget__total-amount">$50.00</span>
  </div>

  <button class="btn btn--primary btn--block">Get Tickets</button>
  <button class="btn btn--ghost btn--block">Add to Cart</button>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Widget container | background | `var(--color-surface)` |
| Widget container | border-radius | `var(--radius-lg)` |
| Widget container | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Widget container | padding | `var(--space-lg)` — 20px |
| Widget container | box-shadow | `var(--shadow-md)` |
| **Label** | | |
| Section label | font-size | `var(--text-h4-size)` — 14px |
| Section label | font-weight | `var(--text-h4-weight)` — 600 |
| Section label | color | `var(--color-text-primary)` |
| Label to input gap | margin-bottom | `var(--space-xs)` — 8px |
| **Discount input row** | | |
| Input row | display | `flex` |
| Input row | gap | `0` (input and button are adjacent) |
| Input field | flex | `1` |
| Input field | padding | `var(--space-xs) var(--space-sm)` — 8px 12px |
| Input field | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Input field | border-radius | `var(--radius-md) 0 0 var(--radius-md)` — left corners only |
| Input field | font-size | `var(--text-body-size)` |
| Input placeholder | color | `var(--color-text-muted)` |
| Apply button | padding | `var(--space-xs) var(--space-md)` — 8px 16px |
| Apply button | background | `transparent` |
| Apply button | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Apply button | border-left | `none` |
| Apply button | border-radius | `0 var(--radius-md) var(--radius-md) 0` — right corners only |
| Apply button | font-size | `var(--text-body-size)` |
| Apply button | font-weight | `600` |
| Apply button | color | `var(--color-text-link)` |
| **Total** | | |
| Total row | display | `flex`, `justify-content: space-between`, `align-items: baseline` |
| Total row | margin | `var(--space-lg) 0` — 20px |
| Total row | padding-top | `var(--space-md)` — 16px |
| Total row | border-top | `var(--border-width) var(--border-style) var(--color-border)` |
| "Total" label | font-size | `var(--text-body-size)` |
| "Total" label | color | `var(--color-text-secondary)` |
| Total amount | font-size | `var(--text-h1-size)` — 24px |
| Total amount | font-weight | `var(--text-h1-weight)` — 700 |
| Total amount | color | `var(--color-text-primary)` |
| **CTA buttons** | | |
| Primary CTA | uses `btn btn--primary btn--block` |
| Primary CTA | width | 100% |
| Primary CTA | padding | `var(--space-sm) var(--space-lg)` — 12px 20px |
| Primary CTA | border-radius | `var(--radius-full)` — pill |
| Primary CTA | font-size | `var(--text-body-size)` |
| Primary CTA | font-weight | `600` |
| Primary CTA | background | `var(--color-primary)` |
| Between buttons | gap | `var(--space-sm)` — 12px |
| Ghost CTA | background | `transparent` |
| Ghost CTA | color | `var(--color-text-secondary)` |
| Ghost CTA | font-size | `var(--text-body-size)` |
| Ghost CTA | font-weight | `500` |
| Ghost CTA | width | 100% |
| Ghost CTA | text-align | `center` |

## States

**Default:**
Clean card with input, total, and two CTA buttons stacked.

**Input focus:**
Border color `var(--color-border-focus)`. Subtle focus ring: `0 0 0 3px var(--color-primary-light)`.

**Apply hover:**
Color darkens to `var(--color-primary-hover)`.

**Discount applied:**
Show a success line below the input: "Code SAVE20 applied" in `var(--color-success)` with a checkmark icon. Input becomes read-only with a remove/× button.

**Primary CTA hover:**
Background `var(--color-primary-hover)`.

**Ghost CTA hover:**
Background `var(--color-bg)`.

## Responsive Behavior

**Mobile (< 640px):**
Full-width card. CTA buttons remain full-width. May become a sticky bottom bar.

**Desktop (> 1024px):**
Fixed in sidebar column, `var(--detail-sidebar-width)` wide.

## Accessibility
- **Input:** Associated `<label>` (visually the "Discount code" heading serves this role, use `for`/`id`)
- **Apply:** `aria-label="Apply discount code"`
- **Total:** Use `aria-live="polite"` so price changes are announced
- **CTA:** Clear, descriptive button text ("Get Tickets", not "Submit")

## Do's and Don'ts

**Do:**
- Make the total amount large and prominent
- Keep the primary CTA as the most visually dominant element
- Show the discount input above the total
- Use a divider line above the total for visual separation

**Don't:**
- Hide the total price — it should always be visible
- Use two equally prominent buttons — primary is filled, secondary is ghost/text
- Put additional form fields in this widget — keep it focused on pricing/purchase
