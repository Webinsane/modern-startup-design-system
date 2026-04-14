# Booking Sidebar

## Overview
Compact sidebar form for configuring and confirming a booking. Contains date/time selection, service add-ons, discount code, total, and action buttons.

## Structure
```html
<aside class="sidebar">
  <h2 class="sidebar__title">Select a time</h2>

  <div class="sidebar__field">
    <label class="sidebar__label">Start:</label>
    <div class="sidebar__input-row">
      <input type="text" class="sidebar__input" value="28 Jun, 2020 - 10:00">
      <button class="sidebar__calendar-btn"><i data-lucide="calendar"></i></button>
    </div>
  </div>

  <div class="sidebar__field">
    <label class="sidebar__label">End:</label>
    <div class="sidebar__input-row">
      <input type="text" class="sidebar__input" value="30 Jun, 2020 - 12:00">
      <button class="sidebar__calendar-btn"><i data-lucide="calendar"></i></button>
    </div>
  </div>

  <label class="sidebar__checkbox">
    <input type="checkbox">
    Make this booking recurrent
  </label>

  <div class="sidebar__section">
    <h3 class="sidebar__section-title">Additional Services</h3>
    <div class="sidebar__service">
      <label><input type="checkbox" checked> Catering Service</label>
      <span class="sidebar__price">+$20.00</span>
    </div>
    <div class="sidebar__service">
      <label><input type="checkbox"> Projector</label>
      <span class="sidebar__price">+$30.00</span>
    </div>
  </div>

  <div class="sidebar__section">
    <h3 class="sidebar__section-title">Discount code</h3>
    <div class="sidebar__discount-row">
      <input type="text" class="sidebar__input" placeholder="Enter discount code">
      <button class="btn btn--outlined btn--sm">Apply</button>
    </div>
  </div>

  <div class="sidebar__total">
    <span class="sidebar__total-label">Total</span>
    <span class="sidebar__total-amount">$300.00</span>
  </div>

  <button class="btn btn--primary btn--lg sidebar__cta">Confirm this booking</button>
  <button class="btn btn--outlined btn--lg sidebar__secondary">Add to Cart</button>
</aside>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Sidebar | width | `var(--sidebar-width)` — 320px |
| Sidebar | background | `var(--color-surface)` |
| Sidebar | padding | `var(--space-xl)` — 24px |
| Sidebar | border-radius | `var(--radius-lg)` |
| Sidebar | box-shadow | `var(--shadow-md)` |
| Title | font-size | `var(--text-h2-size)` — 20px |
| Title | font-weight | `var(--text-h2-weight)` |
| Title | color | `var(--color-text-primary)` |
| Labels | font-size | `var(--text-small-size)` |
| Labels | color | `var(--color-text-muted)` |
| Inputs | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Inputs | border-radius | `var(--radius-md)` |
| Inputs | padding | `var(--space-xs) var(--space-sm)` |
| Inputs | font-size | `var(--text-body-size)` |
| Section title | font-size | `var(--text-h4-size)` |
| Section title | font-weight | `var(--text-h4-weight)` |
| Service price | color | `var(--color-text-secondary)` |
| Total amount | font-size | `var(--text-h1-size)` — 24px |
| Total amount | font-weight | `var(--text-h1-weight)` — 700 |
| Field spacing | gap | `var(--space-md)` — 16px |
| Section spacing | margin-top | `var(--space-lg)` — 20px |
| CTA buttons | margin-top | `var(--space-lg)` — 20px |
| Between buttons | gap | `var(--space-sm)` — 12px |

## Layout Rules
- Fixed width sidebar (`var(--sidebar-width)`)
- Vertical stack layout with consistent field spacing
- Total amount is large and right-aligned or centered
- CTA is full-width, primary filled
- Secondary action (Add to Cart) is full-width, outlined

## States

**Default:**
Clean form layout with subtle borders on inputs.

**Input focus:**
Border changes to `var(--color-border-focus)`.

**Checkbox checked:**
Uses `var(--color-primary)` for checkmark.

**Discount applied:**
Show success message below discount input.

## Responsive Behavior

**Mobile (< 640px):**
Full-width, pinned to bottom as a sheet or full-page overlay.

**Desktop (> 1024px):**
Fixed sidebar alongside the main content area.

## Accessibility
- **Role:** `<aside>` with `aria-label="Booking details"`
- **Keyboard:** `Tab` through all form fields in order
- **Screen reader:** Labels associated with inputs via `for`/`id`
- **Price updates:** Use `aria-live="polite"` on total amount

## Do's and Don'ts

**Do:**
- Show running total that updates as services are toggled
- Make the primary CTA the most prominent element
- Group related fields (dates together, services together)

**Don't:**
- Allow the sidebar to scroll independently from main content on desktop
- Hide the total amount — it should always be visible
