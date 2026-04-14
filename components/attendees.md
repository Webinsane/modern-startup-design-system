# Attendees / Profile List

## Overview
A sidebar widget showing a count of attendees/people with a scrollable list of user profiles. Each profile row has an avatar, name, role/subtitle, and an action menu. Used on event detail pages and resource views.

## Structure
```html
<div class="widget widget--attendees">
  <div class="widget__header">
    <div class="widget__count">
      <span class="widget__count-number">284</span>
      <span class="widget__count-label">Attendees</span>
    </div>
    <a href="#" class="widget__view-all">View all</a>
  </div>

  <ul class="profile-list">
    <li class="profile-list__item">
      <img src="assets/avatars/avatar-b12.png" class="profile-list__avatar" alt="Vicente Reyes">
      <div class="profile-list__info">
        <span class="profile-list__name">Vicente Reyes</span>
        <span class="profile-list__role">Industry</span>
      </div>
      <button class="profile-list__action" aria-label="More options">
        <i data-lucide="ellipsis"></i>
      </button>
    </li>
  </ul>
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
| **Header** | | |
| Header | display | `flex`, `justify-content: space-between`, `align-items: baseline` |
| Header | margin-bottom | `var(--space-lg)` — 20px |
| Count number | font-size | `var(--text-h1-size)` — 24px |
| Count number | font-weight | `var(--text-h1-weight)` — 700 |
| Count number | color | `var(--color-text-primary)` |
| Count label | font-size | `var(--text-body-size)` — 14px |
| Count label | font-weight | `500` |
| Count label | color | `var(--color-text-secondary)` |
| Count label | margin-left | `var(--space-xs)` — 8px |
| "View all" link | font-size | `var(--text-xs-size)` — 12px |
| "View all" link | color | `var(--color-text-link)` |
| **Profile list item** | | |
| Item | display | `flex`, `align-items: center` |
| Item | padding | `var(--space-sm) 0` — 12px top/bottom |
| Item | gap | `var(--space-sm)` — 12px |
| Avatar | width/height | 40px |
| Avatar | border-radius | `var(--radius-full)` |
| Avatar | object-fit | `cover` |
| Name | font-size | `var(--text-body-size)` — 14px |
| Name | font-weight | `600` |
| Name | color | `var(--color-text-primary)` |
| Role/subtitle | font-size | `var(--text-xs-size)` — 12px |
| Role/subtitle | color | `var(--color-text-muted)` |
| Info block | flex | `1`, `min-width: 0` |
| Name-to-role gap | gap | `2px` |
| Action button | width/height | 28px |
| Action button | color | `var(--color-text-muted)` |
| Action button | border-radius | `var(--radius-md)` |
| Action icon | size | 16px |
| Between items | border-bottom | none (spacing only, no dividers) |

## States

**Default:**
Clean list with consistent spacing between items.

**Item hover:**
Subtle background `var(--color-bg)` with `var(--radius-md)` rounding. Use negative margins + padding to extend the hover area.

**Action button hover:**
Background `var(--color-bg)`, color shifts to `var(--color-text-secondary)`.

**Loading:**
Skeleton placeholders for avatar (circle) and text (two lines).

## Responsive Behavior

**Mobile (< 640px):**
Full-width card. Shows 4-5 attendees with "View all" to see more.

**Desktop (> 1024px):**
Fixed in the sidebar column. Shows 4-6 attendees.

## Accessibility
- **List:** Use semantic `<ul>` / `<li>`
- **Avatar:** Alt text with person's name
- **Action button:** `aria-label="More options for [name]"`
- **Keyboard:** `Tab` through action buttons
- **"View all":** Opens full attendee list/modal

## Do's and Don'ts

**Do:**
- Show the large count number prominently (it's a key metric)
- Use colored avatar placeholders with initials when no photo is available
- Limit visible items to 4-6, use "View all" for the rest

**Don't:**
- Add divider lines between items — spacing is sufficient
- Show more than 6 items without scrolling or "View all"
- Use different avatar sizes in the same list
