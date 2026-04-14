# Top Navigation Bar

## Overview
Horizontal top bar fixed at the top of the content area, to the right of the sidebar. Contains navigation items on the left and utility actions (search, notifications, profile) on the right. For a variant that includes secondary content tabs below the bar, see `top-nav-tabs.md`.

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
    <!-- Theme toggle -->
    <button class="top-nav__icon-btn" id="theme-toggle" aria-label="Toggle theme">
      <i data-lucide="moon"></i>  <!-- light mode: moon icon, dark mode: sun icon -->
    </button>

    <!-- Search -->
    <button class="top-nav__icon-btn" aria-label="Search">
      <i data-lucide="search"></i>
    </button>

    <!-- Notifications -->
    <button class="top-nav__icon-btn" aria-label="Notifications" aria-haspopup="true" aria-expanded="false">
      <i data-lucide="bell"></i>
      <span class="top-nav__badge">2</span>
    </button>

    <!-- Profile -->
    <button class="top-nav__profile" aria-haspopup="true" aria-expanded="false">
      <img src="assets/avatars/avatar-a21.png" alt="" class="top-nav__avatar">
      <span class="top-nav__name">Robert Dorwart</span>
      <i data-lucide="chevron-down" class="top-nav__chevron"></i>
    </button>
  </div>
</header>

<!-- Notifications Dropdown -->
<div class="dropdown dropdown--notifications" role="dialog" aria-label="Notifications">
  <div class="dropdown__header">
    <h3 class="dropdown__title">Notifications</h3>
    <button class="dropdown__action-link">
      <i data-lucide="check-check"></i>
      Mark all as read
    </button>
  </div>
  <div class="dropdown__list">
    <a href="#" class="notification notification--unread">
      <div class="notification__icon">
        <i data-lucide="at-sign"></i>
      </div>
      <div class="notification__content">
        <p class="notification__text">
          <strong>Mark Edwards</strong> mentioned you in the <strong>#warehouse</strong> channel
        </p>
        <span class="notification__meta">Collaboration · 18m ago</span>
      </div>
    </a>
    <a href="#" class="notification">
      <div class="notification__icon">
        <i data-lucide="check-circle"></i>
      </div>
      <div class="notification__content">
        <p class="notification__text">
          <strong>SAP Data Lake</strong> connection successfully connected
        </p>
        <span class="notification__meta">Insights · 2h ago</span>
      </div>
    </a>
  </div>
  <div class="dropdown__footer">
    <button class="btn btn--primary btn--sm">Show all</button>
  </div>
</div>

<!-- Profile Dropdown -->
<div class="dropdown dropdown--profile" role="menu" aria-label="User menu">
  <div class="dropdown__user">
    <img src="assets/avatars/avatar-a21.png" alt="" class="dropdown__avatar">
    <span class="dropdown__name">Robert Dorwart</span>
  </div>
  <div class="dropdown__divider"></div>
  <a href="#" class="dropdown__item" role="menuitem">
    <i data-lucide="building"></i>
    My Organization
  </a>
  <a href="#" class="dropdown__item" role="menuitem">
    <i data-lucide="user"></i>
    My Profile
  </a>
  <a href="#" class="dropdown__item" role="menuitem">
    <i data-lucide="settings"></i>
    Settings
  </a>
  <a href="#" class="dropdown__item" role="menuitem">
    <i data-lucide="log-out"></i>
    Log Out
  </a>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Top nav bar | height | `var(--top-nav-height)` — 56px |
| Top nav bar | background | `var(--color-surface)` |
| Top nav bar | border-bottom | `var(--border-width) var(--border-style) var(--color-border)` |
| Top nav bar | padding | `0 var(--space-xl)` — 0 24px |
| Top nav bar | position | `fixed`, top: 0 |
| Top nav bar | z-index | `var(--z-sticky)` |
| Hamburger button | size | 40px |
| Hamburger button | display | `none` (desktop), `flex` (mobile < 640px) |
| Hamburger button | icon size | 22px |
| Hamburger button | color | `var(--color-text-secondary)` |
| Hamburger button hover | background | `var(--color-surface-alt)` |
| Hamburger button | margin-right | `var(--space-sm)` |
| Profile avatar | size | 36px |
| Profile avatar | border-radius | `var(--radius-full)` |
| Profile name | font-size | `var(--text-body-size)` — 14px |
| Profile name | font-weight | `500` |
| Profile name | color | `var(--color-text-primary)` |
| Icon button | size | 40px |
| Icon button | border-radius | `var(--radius-md)` |
| Icon button icon | size | 20px |
| Icon button icon | color | `var(--color-text-secondary)` |
| Notification badge | size | 18px |
| Notification badge | background | `var(--color-error)` |
| Notification badge | color | `var(--color-text-inverse)` |
| Notification badge | font-size | `var(--text-xs-size)` — 12px |
| Notification badge | border-radius | `var(--radius-full)` |
| Actions gap | gap | `var(--space-sm)` — 12px |
| Chevron | size | 16px |
| Chevron | color | `var(--color-text-muted)` |
| **Dropdown** | | |
| Dropdown container | background | `var(--color-surface)` |
| Dropdown container | border-radius | `var(--radius-lg)` — 12px |
| Dropdown container | box-shadow | `var(--shadow-lg)` |
| Dropdown container | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Dropdown container | min-width | 280px (notifications), 200px (profile) |
| Dropdown container | padding | `var(--space-xs)` — 8px |
| Dropdown header | padding | `var(--space-sm) var(--space-md)` — 12px 16px |
| Dropdown title | font-size | `var(--text-h4-size)` — 14px |
| Dropdown title | font-weight | `var(--text-h4-weight)` — 600 |
| "Mark all as read" | font-size | `var(--text-xs-size)` |
| "Mark all as read" | color | `var(--color-nav-active)` — teal |
| Notification item | padding | `var(--space-sm) var(--space-md)` — 12px 16px |
| Notification item | border-radius | `var(--radius-md)` |
| Notification icon | size | 32px (container), 16px (icon) |
| Notification icon | background | `var(--color-bg)` |
| Notification icon | border-radius | `var(--radius-full)` |
| Notification text | font-size | `var(--text-small-size)` — 13px |
| Notification meta | font-size | `var(--text-xs-size)` — 12px |
| Notification meta | color | `var(--color-text-muted)` |
| Notification unread dot | size | 8px |
| Notification unread dot | background | `var(--color-nav-active)` — teal |
| "Show all" button | uses `btn--primary btn--sm` with teal override |
| Dropdown divider | border-top | `var(--border-width) var(--border-style) var(--color-border)` |
| Dropdown divider | margin | `var(--space-xs) 0` |
| Profile dropdown item | padding | `var(--space-xs) var(--space-md)` — 8px 16px |
| Profile dropdown item | font-size | `var(--text-body-size)` |
| Profile dropdown item | color | `var(--color-text-primary)` |
| Profile dropdown item | border-radius | `var(--radius-md)` |
| Profile dropdown item icon | size | 16px |
| Profile dropdown item icon | color | `var(--color-text-secondary)` |
| Profile dropdown item icon-to-text gap | gap | `var(--space-sm)` — 12px |
| Dropdown user section | padding | `var(--space-sm) var(--space-md)` |
| Dropdown avatar | size | 32px |
| Dropdown user name | font-size | `var(--text-body-size)` |
| Dropdown user name | font-weight | `600` |

## Layout Rules
- Top nav spans full width minus sidebar width
- `left: var(--nav-sidebar-width)` when sidebar is expanded, `left: var(--nav-sidebar-collapsed)` when collapsed
- Flex row with `justify-content: flex-end` (actions right-aligned)
- Dropdowns positioned absolute, anchored to the trigger button
- Notifications dropdown: right-aligned, positioned below the bell icon
- Profile dropdown: right-aligned, positioned below the profile button

## States

**Default:**
Clean white bar with subtle bottom border.

**Icon button hover:**
Background `var(--color-surface-active)`. Transition: `var(--transition-fast)`.

**Profile hover:**
Subtle background `var(--color-bg)` on the profile button area.

**Dropdown open:**
Trigger shows active state. Dropdown slides in with `var(--transition-base)` and slight translateY(-4px → 0).

**Notification unread:**
Small teal dot indicator. Text uses `font-weight: 500`.

**Notification hover:**
Background `var(--color-bg)`.

**Profile item hover:**
Background `var(--color-bg)`.

**Log Out hover:**
Color shifts to `var(--color-error)`.

## Theme Toggle
The theme toggle button (`#theme-toggle`) switches between light and dark mode:
- **Light mode:** displays the moon icon (`data-lucide="moon"`).
- **Dark mode:** displays the sun icon (`data-lucide="sun"`).
- Clicking the button sets `data-theme="dark"` on the `<html>` element (or removes it for light mode).
- The selected theme is persisted in `localStorage`.

## Mobile Search

On mobile, the desktop search bar is hidden and replaced with a search icon button (`.top-nav__search-mobile`). Tapping it opens a full-width search overlay pinned to the top of the screen.

### Structure
```html
<!-- Mobile search icon (hidden on desktop, visible on mobile) -->
<button class="top-nav__search-mobile" aria-label="Search" onclick="openMobileSearch()">
  <i data-lucide="search"></i>
</button>

<!-- Overlay + search bar (placed outside top-nav) -->
<div class="mobile-search-overlay" id="searchOverlay" onclick="closeMobileSearch()"></div>
<div class="mobile-search" id="mobileSearch">
  <input type="text" class="mobile-search__input" placeholder="Search...">
  <button class="mobile-search__close" aria-label="Close search" onclick="closeMobileSearch()">
    <i data-lucide="x"></i>
  </button>
</div>
```

### Mobile Search Tokens

| Element | Property | Token |
|---------|----------|-------|
| Search icon button | size | 36–40px |
| Search icon button | display | `none` (desktop), `flex` (mobile < 640px) |
| Search overlay | background | `rgba(0, 0, 0, 0.5)` |
| Search bar | background | `var(--color-surface)` |
| Search bar | box-shadow | `var(--shadow-lg)` |
| Search input | height | 40px |
| Search input | border-radius | `var(--radius-full)` |
| Search input | background | `var(--color-bg)` |
| Search input focus | border-color | `var(--color-border-focus)` |
| Close button | size | 36–40px |

### JavaScript
```js
function openMobileSearch() {
  document.getElementById('mobileSearch').classList.add('is-open');
  document.getElementById('searchOverlay').classList.add('is-visible');
  document.querySelector('.mobile-search__input').focus();
}
function closeMobileSearch() {
  document.getElementById('mobileSearch').classList.remove('is-open');
  document.getElementById('searchOverlay').classList.remove('is-visible');
}
```

## Responsive Behavior

**Mobile (< 640px):**
Top nav spans full width (no sidebar offset), padding reduced to `var(--space-sm)`. Key changes:
- **Nav items become icon-only:** Text labels (wrapped in `<span>`) are hidden. Buttons collapse to 36px square icon-only. This is why text labels must always be wrapped in `<span>` — bare text nodes cannot be hidden with CSS.
- **Hamburger button** appears on the left to open the mobile drawer sidebar
- **Desktop search bar** hidden — replaced with search icon that opens a full-width overlay
- **Profile name and chevron** hidden — avatar only
- **Actions gap** reduced to `var(--space-2xs)`

**Tablet (640px - 1024px):**
Top nav adjusts to sidebar collapsed width offset. Profile name may be hidden depending on available space.

**Desktop (> 1024px):**
Full layout with profile name visible. Hamburger button and mobile search icon hidden.

**Extra small (< 375px):**
Padding further reduced to `var(--space-sm)`. Content wrapper uses minimal padding.

## Accessibility
- **Role:** `<header>` for the bar, `role="dialog"` for notifications, `role="menu"` for profile dropdown
- **Keyboard:** `Tab` to reach triggers, `Enter`/`Space` to open, `Escape` to close, arrow keys within dropdown
- **ARIA:** `aria-haspopup`, `aria-expanded`, `aria-label` on triggers
- **Focus trap:** When dropdown is open, focus stays within until closed
- **Screen reader:** Badge count announced via `aria-label="2 notifications"`

## Do's and Don'ts

**Do:**
- Show unread notification count in badge
- Use teal for notification accents (matching sidebar active color)
- Keep "Show all" as the bottom action in notifications
- Group profile actions logically (account items, then logout)

**Don't:**
- Show more than 5 notifications in the dropdown — use "Show all" for the rest
- Use `<a>` tags with `top-nav__item` classes for navigation — use `btn--text` and `btn--text-active` button variants instead
- Use indigo for notification highlights — use teal to match nav system
