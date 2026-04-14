# Top Navigation with Tabs

## Overview
Combines the top navigation bar with a content tabs strip directly below it. Use this pattern when a section has multiple sub-views that need secondary navigation. The top nav handles global actions (search, notifications, profile) while the tabs switch between page sub-views.

See `top-nav.md` for documentation on the navigation bar itself.

## Structure
```html
<header class="top-nav">
  <!-- Hamburger button — hidden on desktop, visible on mobile -->
  <button class="top-nav__hamburger" aria-label="Open menu" onclick="openMobileDrawer()">
    <i data-lucide="menu"></i>
  </button>

  <!-- Navigation items — wrap text in <span> for mobile icon-only collapse -->
  <div class="top-nav__items">
    <button class="btn btn--text btn--sm"><i data-lucide="network"></i> <span>Org Chart</span></button>
    <button class="btn btn--text btn--sm"><i data-lucide="calendar"></i> <span>Calendar</span></button>
    <button class="btn btn--text-active btn--sm"><i data-lucide="square-check"></i> <span>Active Item</span></button>
  </div>

  <div class="top-nav__actions">
    <!-- Search, notifications, profile — see top-nav.md for full markup -->
  </div>
</header>

<!-- Content Tabs — placed immediately after the top-nav -->
<div class="content-tabs" role="tablist" aria-label="Section views">
  <a href="#" class="content-tabs__item content-tabs__item--active" role="tab" aria-selected="true">My Absence</a>
  <a href="#" class="content-tabs__item" role="tab" aria-selected="false">Absences Calendar</a>
  <a href="#" class="content-tabs__item" role="tab" aria-selected="false">Team Overview</a>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Content tabs container | background | `var(--color-surface)` |
| Content tabs container | border-bottom | `var(--border-width) var(--border-style) var(--color-border)` |
| Content tabs container | padding | `0 var(--space-xl)` |
| Content tabs container | gap | `var(--space-xs)` |
| Tab item | font-size | `var(--text-body-size)` — 14px |
| Tab item | font-weight | `500` |
| Tab item | color | `var(--color-text-secondary)` |
| Tab item | padding | `var(--space-sm) var(--space-xs)` |
| Tab item | height | `40px` |
| Tab item active | color | `var(--color-secondary)` — blue |
| Tab item active indicator | border-bottom | `2px solid var(--color-secondary)` |
| Tab item hover | color | `var(--color-text-primary)` |
| Tab item hover | background | `var(--color-surface-alt)` |
| Tab item | border-radius | `var(--radius-sm)` (top corners) |
| Tab item transition | transition | `var(--transition-fast)` |

## Layout Rules
- The `.content-tabs` strip sits flush below the `.top-nav`, sharing the same left offset as the nav bar
- Both elements are typically wrapped together in a sticky container so they scroll away as a unit or stay fixed
- Tab strip uses `display: flex; flex-direction: row; align-items: stretch`
- Active tab indicator is a bottom border on the tab item, not a separate element

## States

**Default:**
Inactive tabs are muted gray. Active tab is blue with a 2px bottom border indicator.

**Tab hover:**
Color shifts to `var(--color-text-primary)`, subtle background `var(--color-surface-alt)`.

**Tab active:**
Color `var(--color-secondary)`, bottom border `2px solid var(--color-secondary)`.

**Mobile (< 640px):**
Content tabs remain visible but may scroll horizontally if there are many items. Tab text stays visible (unlike nav items which collapse to icon-only).

## Accessibility
- **Role:** `role="tablist"` on the container, `role="tab"` on each item
- **ARIA:** `aria-selected="true/false"` on each tab, `aria-controls` pointing to the corresponding `tabpanel`
- **Keyboard:** `Tab` to reach the tab list, arrow keys to move between tabs, `Enter`/`Space` to activate
- **Tab panels:** Each panel has `role="tabpanel"` and `aria-labelledby` pointing to its tab

## Do's and Don'ts

**Do:**
- Use for sections with 2–6 distinct sub-views
- Keep tab labels short (1–3 words)
- Match the active tab label to the page's `<h1>` or page title for screen readers

**Don't:**
- Nest content tabs inside another tabbed interface — use a different navigation pattern instead
- Use content tabs as a replacement for breadcrumbs or page-level navigation
- Add icons to content tab labels — keep them text-only for scannability
