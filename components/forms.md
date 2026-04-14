# Form Inputs

## Overview
Form elements including text inputs, date pickers, password fields, number steppers, select dropdowns, checkboxes, discount code fields, and invite/tag inputs. Used in booking sidebar, search filters, dialogs, and authentication flows.

## Quick Reference

| Need | Pattern |
|------|---------|
| Text input | `form-field` + `form-field__label` + `form-field__input` |
| Select dropdown | Same structure, `<select class="form-field__input">` |
| Input with icon | Wrap in `form-field__input-wrapper`, add `form-field__input-icon` |
| Error state | Add `form-field__input--error` to input, add `form-field__error` message |
| Password toggle | Icon with `form-field__input-icon--action` modifier |
| Checkbox | `<label class="form-checkbox"><input type="checkbox"> Label</label>` |
| Chip selector | `form-chips` container with `form-chip` items, `form-chip--selected` |

All inputs: `var(--color-surface)` background, `var(--color-border)` border, `var(--radius-md)` corners, 44px height.

## Structure
```html
<!-- Text input -->
<div class="form-field">
  <label class="form-field__label">Full Name</label>
  <input type="text" class="form-field__input" placeholder="Enter your name">
</div>

<!-- Select / Dropdown -->
<div class="form-field">
  <label class="form-field__label">Price Plan</label>
  <select class="form-field__input">
    <option>Desk</option>
    <option>Meeting Room</option>
  </select>
</div>

<!-- Date picker with icon -->
<div class="form-field">
  <label class="form-field__label">Start Date</label>
  <div class="form-field__input-wrapper">
    <input type="text" class="form-field__input" placeholder="02/22/2021">
    <span class="form-field__input-icon"><i data-lucide="calendar"></i></span>
  </div>
</div>

<!-- Password with toggle and error -->
<div class="form-field">
  <div class="form-field__label-row">
    <label class="form-field__label">Password</label>
    <a class="form-field__label-link" href="#">Forgot Your Password?</a>
  </div>
  <div class="form-field__input-wrapper">
    <input type="password" class="form-field__input form-field__input--error" value="password">
    <button class="form-field__input-icon form-field__input-icon--action" aria-label="Toggle visibility">
      <i data-lucide="eye"></i>
    </button>
  </div>
  <p class="form-field__error">Wrong password, try another one</p>
</div>

<!-- Password with strength meter -->
<div class="form-field">
  <div class="form-field__label-row">
    <label class="form-field__label">Password</label>
    <div class="password-strength">
      <span class="password-strength__label">Average</span>
      <div class="password-strength__bar">
        <span class="password-strength__segment password-strength__segment--filled"></span>
        <span class="password-strength__segment password-strength__segment--filled"></span>
        <span class="password-strength__segment"></span>
        <span class="password-strength__segment"></span>
      </div>
    </div>
  </div>
  <div class="form-field__input-wrapper">
    <input type="password" class="form-field__input" value="password">
    <button class="form-field__input-icon form-field__input-icon--action" aria-label="Toggle visibility">
      <i data-lucide="eye"></i>
    </button>
  </div>
</div>

<!-- Validation checklist -->
<ul class="validation-checklist">
  <li class="validation-checklist__item validation-checklist__item--pass"><i data-lucide="check"></i> At least 7 characters</li>
  <li class="validation-checklist__item validation-checklist__item--fail"><i data-lucide="x"></i> At least 1 special character</li>
</ul>

<!-- Number input with stepper -->
<div class="form-field">
  <label class="form-field__label">Add to membership</label>
  <div class="form-field__row">
    <div class="form-field"><input type="text" class="form-field__input" placeholder="Add to membership"></div>
    <div class="number-stepper">
      <button class="number-stepper__btn" aria-label="Decrease">&minus;</button>
      <input type="number" class="number-stepper__value" value="1" min="0">
      <button class="number-stepper__btn" aria-label="Increase">+</button>
    </div>
  </div>
</div>

<!-- Checkbox -->
<label class="form-checkbox">
  <input type="checkbox"> Window seat preferred
</label>

<!-- Chip selector -->
<div class="form-chips">
  <span class="form-chip form-chip--selected"><i data-lucide="x"></i> Design</span>
  <span class="form-chip">Marketing</span>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Label | font-size | `var(--text-body-size)` — 14px |
| Label | font-weight | `600` |
| Label | color | `var(--color-text-primary)` |
| Label to input gap | margin-bottom | `var(--space-xs)` — 8px |
| Label link | font-size | `var(--text-small-size)` — 13px |
| Label link | color | `var(--color-secondary)` |
| Input | background | `var(--color-surface)` |
| Input | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Input | border-radius | `var(--radius-md)` — 8px |
| Input | height | `44px` |
| Input | padding | `0 var(--space-sm)` — 0 12px |
| Input | font-size | `var(--text-body-size)` — 14px |
| Input | color | `var(--color-text-primary)` |
| Input placeholder | color | `var(--color-text-muted)` |
| Input icon | color | `var(--color-text-muted)` |
| Input icon | size | `18px` |
| Error border | border-color | `var(--color-error)` |
| Error text | color | `var(--color-error)` |
| Error text | font-size | `var(--text-xs-size)` |
| Field spacing | margin-bottom | `var(--space-md)` — 16px |
| Number stepper | height | `44px` |
| Number stepper | background | `var(--color-surface)` |
| Number stepper btn | color | `var(--color-text-secondary)` |
| Strength segment | size | `24px × 4px` |
| Strength filled | background | `var(--color-accent)` |
| Strength empty | background | `var(--color-border-light)` |
| Checklist pass icon | color | `var(--color-success)` |
| Checklist fail icon | color | `var(--color-text-muted)` |
| Checkbox box | size | 18px |
| Checkbox box | border-radius | `var(--radius-sm)` |
| Checkbox checked | background | `var(--color-primary)` |
| Chip | background | `var(--color-bg)` |
| Chip | border-radius | `var(--radius-full)` |
| Selected chip | background | `var(--color-primary-light)` |

## States

**Default:**
White background, light grey border (`var(--color-border)`), 44px height.

**Focus:**
Border color changes to `var(--color-border-focus)`.

**Error:**
Border color `var(--color-error)`. Error message below in `var(--color-error)` text at `var(--text-xs-size)`.

**Disabled:**
Background `var(--color-bg)`, opacity 0.6, cursor `not-allowed`.

## Variants

**Input with trailing icon:** Wrap input in `.form-field__input-wrapper`, add `.form-field__input-icon` after input. Use `--action` modifier for clickable icons (e.g., eye toggle).

**Label row with link:** Use `.form-field__label-row` flex container to place label and link side-by-side.

**Number stepper:** Standalone `.number-stepper` with minus/value/plus. Pairs with a text input via `.form-field__row`.

**Password strength:** `.password-strength` in label row with colored segments.

**Validation checklist:** `<ul class="validation-checklist">` with `--pass` and `--fail` item modifiers.

## Responsive Behavior

**Mobile (< 640px):**
All inputs full-width. Stacked vertically. `.form-field__row` stacks to column.

**Desktop (> 1024px):**
Inputs may sit side-by-side in two-column layouts.

## Accessibility
- **Label:** Every input must have an associated `<label>` with `for`/`id`
- **Keyboard:** `Tab` to navigate, `Space` to toggle checkboxes
- **Error:** Use `aria-invalid="true"` and `aria-describedby` pointing to error message
- **Required:** Use `aria-required="true"` on required fields
- **Password toggle:** Button with `aria-label="Toggle password visibility"`
- **Number stepper:** Buttons with `aria-label="Increase"` / `aria-label="Decrease"`

## Do's and Don'ts

**Do:**
- Always show labels above inputs (bold, black, 14px)
- Use trailing icons for date pickers, password toggles, and search
- Use white backgrounds on all inputs
- Maintain 44px height for all single-line inputs
- Group related fields visually

**Don't:**
- Use floating labels — this system uses fixed labels above inputs
- Use grey backgrounds on inputs — always white
- Style select dropdowns differently from text inputs
- Omit focus states
- Use muted/grey labels — labels are always bold black
