# Cards

## Overview
Primary content container used for room bookings, events, discussion boards, benefits, perks, visitors, and dashboard widgets. Cards come in several distinct variants based on content type.

## Structure
```html
<!-- With real image -->
<div class="card">
  <img src="photo.jpg" alt="Event photo" class="card__image">
  <div class="card__body">...</div>
</div>

<!-- With gradient placeholder -->
<div class="card">
  <div class="card__image card__image--placeholder"></div>
  <div class="card__body">
    <div class="card__header">
      <div class="card__title">Title</div>
      <span class="tag tag--confirmed">Status</span>
    </div>
    <div class="card__subtitle">Description text here.</div>
    <div class="card__meta"><i data-lucide="calendar"></i> Meta info</div>
  </div>
  <div class="card__footer">
    <span class="card__footer-meta"><i data-lucide="users"></i> 24 attending</span>
    <button class="btn btn--primary btn--tiny">Action</button>
  </div>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | border-radius | `var(--radius-lg)` — 12px |
| Container | box-shadow | `var(--shadow-md)` |
| Container | overflow | `hidden` |
| Container | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Body | padding | `var(--space-lg)` — 20px |
| Header | margin-bottom | `var(--space-xs)` — 8px |
| Title | font-size | `var(--text-h3-size)` |
| Title | font-weight | `var(--text-h3-weight)` |
| Title | color | `var(--color-text-primary)` |
| Subtitle | font-size | `var(--text-small-size)` |
| Subtitle | color | `var(--color-text-muted)` |
| Subtitle | line-height | `var(--text-body-lh)` |
| Subtitle | margin-bottom | `var(--space-xs)` — 8px |
| Meta text | font-size | `var(--text-xs-size)` |
| Meta text | color | `var(--color-text-secondary)` |
| Actions | padding-top | `var(--space-md)` — 16px |
| Actions | border-top | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Image | width | `100%` |
| Image | height | `160px` |
| Image | object-fit | `cover` |
| Image placeholder | background | `linear-gradient(135deg, var(--color-primary-light) 0%, var(--color-bg) 100%)` |
| Footer | padding | `var(--space-sm) var(--space-lg)` |
| Footer | background | `var(--color-surface-alt)` |
| Footer | border-top | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Footer meta | font-size | `var(--text-xs-size)` |
| Footer meta | color | `var(--color-text-muted)` |
| Footer meta | gap | `var(--space-xs)` |
| Gap between cards | gap | `var(--space-lg)` — 20px |

## Layout Rules
- Cards in a grid use `var(--space-lg)` (20px) gap — visible in annotated designs
- Internal vertical spacing between elements: `var(--space-xs)` (8px) for tight, `var(--space-md)` (16px) for sections
- Padding lives on `.card__body`, not the root `.card` container
- `.card__image` sits flush against the card edges (no border-radius or margin) thanks to `overflow: hidden` on the container
- `.card__footer` spans full width with its own background and top border
- Column gap between card groups: `var(--space-xl)` (24px) — visible in the annotated card design

## States

**Default:**
White background, subtle border, light shadow.

**Hover:**
Shadow elevates to `var(--shadow-lg)`, slight upward translate (-2px). Transition: `var(--transition-fast)`.

**Active/Selected:**
Background shifts to `var(--color-surface-active)` (light purple tint) — seen on first table row highlight.

**Empty:**
Show placeholder illustration with muted text "No items found."

## Responsive Behavior

**Mobile (< 640px):**
Single column stack. Full-width cards. Body padding reduces to `var(--space-md)`. Always set `min-width: 0` on cards inside CSS Grid to prevent overflow.

**Tablet (640-1024px):**
2-column grid for room cards.

**Desktop (> 1024px):**
3-column grid for dashboard widgets. 2-column for events + discussion side-by-side.

**Note:** Cards inside CSS Grid containers must have `min-width: 0` to prevent content (tables, long text) from overflowing the grid track.

## Accessibility
- **Role:** Use `<article>` for self-contained cards, `<div>` for widget containers
- **Keyboard:** Entire card clickable via wrapping `<a>` or button, with `focus-visible` outline
- **Screen reader:** Card title serves as accessible name
- **Focus visible:** 2px outline `var(--color-primary)` with 2px offset

## Variants

**Image card:**
Has a `.card__image` element at the top (before `.card__body`). The image is full-width, 160px tall, with `object-fit: cover` and `display: block`. Use `.card__image--placeholder` modifier for a gradient placeholder background instead of an actual image. The image sits flush with the card edges thanks to `overflow: hidden` on the container.

**Status card:**
Uses `.card__header` with a `.tag` variant (e.g. `.tag--confirmed`, `.tag--pending`) alongside the title. Includes subtitle, meta info, and a `.card__footer` with `.card__footer-meta` for secondary info and an action button. Status cards work well for bookings, events, and any content with a lifecycle state.

**Flat card (no image):**
Omits the `.card__image` element entirely. The `.card__body` sits directly inside the card container. Used for stats widgets, discussion boards, benefits lists, and other text-heavy content. Can include `.card__actions` with a top border separator for action buttons.

## Do's and Don'ts

**Do:**
- Use `.card__body` for all card content padding — never pad the root `.card`
- Include a `.card__footer` when the card needs secondary meta info or actions
- Maintain the 20px gap between cards in grids
- Use `.card__image--placeholder` when no real image is available

**Don't:**
- Nest cards inside other cards
- Use different border-radius values for different card types
- Add padding or margin to `.card__image` — it should be flush with card edges
- Put content directly inside `.card` without wrapping it in `.card__body`
