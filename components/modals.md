# Modals

## Overview
Dialog windows for focused user tasks. White surface with radius-xl and shadow-xl. Multiple variants for different use cases including profile editing, option selection, and confirmations.

## Quick Reference

| Variant | Class | Use case | Footer buttons |
|---------|-------|----------|----------------|
| Edit Profile | `modal-profile` | Edit user info, permissions, tags | Cancel + Save |
| Select Option | `modal-location` | Pick from a grid of options | Cancel + Confirm |
| Confirm (destructive) | `modal-confirm` + `--error` icon | Delete, remove | Cancel + `btn--error` |
| Confirm (warning) | `modal-confirm` + `--warning` icon | Significant but reversible | Cancel + `btn--primary` |

All modals: `var(--color-overlay)` backdrop, `var(--radius-xl)` corners, `var(--shadow-xl)`, max-width 420px. Profile avatar from `assets/avatars/`.

## Structure

### Variant 1: Edit Profile

```html
<div class="modal-overlay">
  <div class="modal modal-profile">
    <button class="modal__close" aria-label="Close">
      <i data-lucide="x"></i>
    </button>
    <div class="modal__body">
      <div class="modal-profile__header">
        <img class="modal-profile__avatar" src="assets/avatars/avatar-b05.png" alt="Sarah Chen" />
        <div class="modal-profile__info">
          <h3 class="modal__title">Name</h3>
          <p class="modal__subtitle">Role</p>
        </div>
      </div>
      <div class="modal-profile__permissions">
        <label class="modal-profile__check">
          <span class="modal-profile__check-icon modal-profile__check-icon--active">
            <i data-lucide="check"></i>
          </span>
          Permission label
        </label>
        <!-- more checkboxes -->
      </div>
      <div class="modal-profile__section">
        <p class="modal__section-label">Section Label</p>
        <div class="modal-profile__tags">
          <input class="modal-profile__tag-input" type="text" placeholder="Add tag..." />
        </div>
      </div>
    </div>
    <div class="modal__footer">
      <button class="btn btn--text">Cancel</button>
      <button class="btn btn--primary">Save</button>
    </div>
  </div>
</div>
```

### Variant 2: Select Option

```html
<div class="modal-overlay">
  <div class="modal modal-location">
    <button class="modal__close" aria-label="Close">
      <i data-lucide="x"></i>
    </button>
    <div class="modal__body">
      <h3 class="modal__title">Title</h3>
      <p class="modal__description">Description text</p>
      <div class="modal-location__grid">
        <div class="modal-location__card modal-location__card--selected">
          <div class="modal-location__card-icon">
            <i data-lucide="..."></i>
          </div>
          <p class="modal-location__card-name">Card Name</p>
          <p class="modal-location__card-desc">Card description</p>
        </div>
        <!-- more cards -->
      </div>
    </div>
    <div class="modal__footer">
      <button class="btn btn--text">Cancel</button>
      <button class="btn btn--primary">Confirm</button>
    </div>
  </div>
</div>
```

### Variant 3: Confirmation (Destructive)

```html
<div class="modal-overlay">
  <div class="modal modal-confirm">
    <button class="modal__close" aria-label="Close">
      <i data-lucide="x"></i>
    </button>
    <div class="modal__body">
      <div class="modal-confirm__icon modal-confirm__icon--error">
        <i data-lucide="alert-triangle"></i>
      </div>
      <h3 class="modal__title">Destructive Action</h3>
      <p class="modal__description">Are you sure? This action cannot be undone.</p>
    </div>
    <div class="modal__footer">
      <button class="btn btn--text">Cancel</button>
      <button class="btn btn--error">Delete</button>
    </div>
  </div>
</div>
```

### Variant 4: Confirmation (Warning)

```html
<div class="modal-overlay">
  <div class="modal modal-confirm">
    <button class="modal__close" aria-label="Close">
      <i data-lucide="x"></i>
    </button>
    <div class="modal__body">
      <div class="modal-confirm__icon modal-confirm__icon--warning">
        <i data-lucide="alert-circle"></i>
      </div>
      <h3 class="modal__title">Warning Title</h3>
      <p class="modal__description">Description of what will happen.</p>
    </div>
    <div class="modal__footer">
      <button class="btn btn--text">Cancel</button>
      <button class="btn btn--primary">Continue</button>
    </div>
  </div>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Overlay | background | `var(--color-overlay)` |
| Modal container | background | `var(--color-surface)` |
| Modal container | border-radius | `var(--radius-xl)` |
| Modal container | box-shadow | `var(--shadow-xl)` |
| Modal container | max-width | `420px` |
| Body | padding | `var(--space-2xl) var(--space-2xl) var(--space-xl)` |
| Footer | display | `flex`, justify `flex-end` |
| Footer | gap | `var(--space-sm)` |
| Footer | padding | `var(--space-lg) var(--space-2xl)` |
| Footer | border-top | `var(--border-width) var(--border-style) var(--color-border)` |
| Close button | position | `absolute`, top-right |
| Close button | size | `var(--space-2xl)` — 32px |
| Close button | border-radius | `var(--radius-full)` |
| Title | font-size | Use `--text-h4` scale |
| Title | color | `var(--color-text-primary)` |
| Description | font-size | Use `--text-body` scale |
| Description | color | `var(--color-text-secondary)` |
| Profile avatar | size | 56px (use `avatar--xl` closest, or custom) |
| Profile avatar | display | inline with name (flex row) |
| Profile avatar | border-radius | `var(--radius-full)` |
| Profile check circle | background (active) | `var(--color-success)` |
| Profile check circle | color (active) | `var(--color-text-inverse)` |
| Profile check circle | background (inactive) | `var(--color-surface-raised)` |
| Selection card | border | `2px solid var(--color-border)` |
| Selection card | border-radius | `var(--radius-lg)` |
| Selection card (selected) | border-color | `var(--color-secondary)` |
| Selection card icon | size | `var(--space-3xl)` — 40px |
| Selection card icon | border-radius | `var(--radius-md)` |
| Selection card icon (selected) | background | `var(--color-secondary-light)` |
| Selection card icon (selected) | color | `var(--color-secondary)` |
| Selection grid | display | `grid`, 2 columns |
| Selection grid | gap | `var(--space-sm)` |
| Confirm icon circle | size | 48px (matches `avatar--lg`) |
| Confirm icon circle | border-radius | `var(--radius-full)` |
| `modal-confirm__icon--error` | background | light error tint |
| `modal-confirm__icon--error` | color | `var(--color-error)` |
| `modal-confirm__icon--warning` | background | light warning tint |
| `modal-confirm__icon--warning` | color | `var(--color-warning)` |
| `modal-confirm__icon--success` | background | light success tint |
| `modal-confirm__icon--success` | color | `var(--color-success)` |

## States

**Default:**
Modal centered on screen over a semi-transparent overlay. White surface with `radius-xl` and `shadow-xl`.

**Hover (close button):**
Background shifts to `var(--color-surface-raised)`. Transition uses `var(--transition-fast)`.

**Hover (selection card):**
Border color darkens. Transition uses `var(--transition-fast)`.

**Selected (selection card):**
Border switches to `var(--color-secondary)`. Icon background becomes `var(--color-secondary-light)` with `var(--color-secondary)` icon color.

**Active (profile check):**
Circle background turns `var(--color-success)` with white check icon. Inactive checks show neutral `var(--color-surface-raised)` background with no icon.

**Loading:**
Replace modal body content with skeleton placeholders. Maintain modal dimensions to prevent layout shift.

**Empty:**
Not applicable; modals are triggered with pre-populated content.

## Responsive Behavior

**Mobile (< 640px):**
Modal takes full width with `16px` side margins. Max-width removed. Selection grid collapses to single column. Modal may anchor to bottom of viewport with `border-radius` only on top corners. Footer buttons stack full-width.

**Tablet (640px - 1024px):**
Centered modal with standard `420px` max-width. Layout unchanged from desktop.

**Desktop (> 1024px):**
Centered modal with `420px` max-width. Full layout as designed.

## Accessibility
- **Role:** `role="dialog"` with `aria-modal="true"` on the modal container
- **Label:** `aria-labelledby` pointing to the modal title element
- **Keyboard:** `Tab` cycles through focusable elements within the modal (focus trap). `Escape` closes the modal. `Enter`/`Space` activates buttons and checkboxes.
- **Focus visible:** 2px outline using `var(--color-primary)` with 2px offset on all interactive elements
- **Screen reader:** Modal title announced on open. Close button labelled with `aria-label="Close"`. Confirmation icon variants do not rely on color alone; title and description convey intent.
- **Focus management:** On open, focus moves to the first focusable element or the close button. On close, focus returns to the trigger element.

## Do's and Don'ts

**Do:**
- Use one primary action button per modal footer
- Keep modal content focused on a single task
- Always provide a way to dismiss (close button, cancel button, or overlay click)
- Use destructive confirmation for irreversible actions with `btn--error`
- Use warning confirmation for reversible but significant actions with `btn--primary`
- Trap focus inside the modal while it is open
- Return focus to the trigger element when the modal closes

**Don't:**
- Stack multiple modals on top of each other
- Use modals for simple information that could be an inline message or toast
- Override `border-radius` — all modals use `radius-xl`
- Place more than two buttons in the footer
- Allow page scroll behind the modal while it is open
- Use color alone to distinguish confirmation severity; always pair with clear title and description text
