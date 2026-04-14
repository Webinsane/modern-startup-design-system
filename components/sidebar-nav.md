# Sidebar Navigation

## Overview
Primary application navigation sidebar with two modes: collapsed (icon-only) and expanded (full labels with sub-navigation). Supports expandable sections, active sub-tabs, and bottom-pinned utility links.

## Structure

### Collapsed Sidebar
```html
<aside class="sidebar-nav sidebar-nav--collapsed" aria-label="Main navigation">
  <div class="sidebar-nav__logo">
    <img src="..." alt="Company" class="sidebar-nav__logo-img">
  </div>

  <nav class="sidebar-nav__menu">
    <!-- Regular item — icon only, hover background highlight, no tooltip -->
    <a href="#" class="sidebar-nav__item sidebar-nav__item--active" aria-label="Home" aria-current="page">
      <i data-lucide="home"></i>
    </a>

    <!-- Submenu item — icon + CSS chevron arrow, flyout on hover -->
    <!-- Uses <div> (not <a>) because it contains nested <a> links in the flyout -->
    <div class="sidebar-nav__item sidebar-nav__item--has-submenu" aria-label="Insights">
      <i data-lucide="bar-chart-3"></i>
      <!-- Small CSS chevron rendered via ::after pseudo-element on --has-submenu -->
      <!-- ::after is a triangle using border trick, colored --white-alpha-40, turns white on hover -->

      <!-- Flyout panel — revealed on hover via opacity/visibility/transform transition (fade + slide-right) -->
      <!-- ::before on flyout creates an invisible bridge zone so mouse can travel from icon to flyout -->
      <div class="sidebar-nav__flyout">
        <div class="sidebar-nav__flyout-title">Insights</div>
        <a href="#" class="sidebar-nav__flyout-link">Overview</a>
        <a href="#" class="sidebar-nav__flyout-link sidebar-nav__flyout-link--active">Live Network</a>
        <a href="#" class="sidebar-nav__flyout-link">To-Do's</a>
      </div>
    </div>

    <!-- Regular items -->
    <a href="#" class="sidebar-nav__item" aria-label="Data Lake">
      <i data-lucide="database"></i>
    </a>
    <a href="#" class="sidebar-nav__item" aria-label="Collaboration">
      <i data-lucide="users"></i>
    </a>

    <div class="sidebar-nav__divider"></div>
    <span class="sidebar-nav__label">Apps</span>
    <a href="#" class="sidebar-nav__item" aria-label="App 1">
      <i data-lucide="layout-grid"></i>
    </a>
  </nav>

  <div class="sidebar-nav__footer">
    <a href="#" class="sidebar-nav__item" aria-label="Settings">
      <i data-lucide="settings"></i>
    </a>
    <a href="#" class="sidebar-nav__item" aria-label="Info">
      <i data-lucide="info"></i>
    </a>
  </div>
</aside>
```

### Expanded Sidebar ('Route' Approach)
```html
<aside class="sidebar-nav sidebar-nav--expanded" aria-label="Main navigation">
  <div class="sidebar-nav__header">
    <img src="..." alt="" class="sidebar-nav__logo-img">
    <span class="sidebar-nav__company-name">Company Name</span>
  </div>

  <nav class="sidebar-nav__menu">
    <a href="#" class="sidebar-nav__item sidebar-nav__item--active" aria-current="page">
      <i data-lucide="home"></i>
      <span>Home</span>
      <i data-lucide="chevron-down" class="sidebar-nav__chevron"></i>
    </a>

    <!-- Active sub-tabs (visible when parent is active) -->
    <div class="sidebar-nav__subtabs">
      <a href="#" class="sidebar-nav__subitem">Overview</a>
      <a href="#" class="sidebar-nav__subitem sidebar-nav__subitem--active">Live Network</a>
      <a href="#" class="sidebar-nav__subitem">To-Do's</a>
    </div>

    <a href="#" class="sidebar-nav__item">
      <i data-lucide="bar-chart-3"></i>
      <span>Insights</span>
      <i data-lucide="chevron-right" class="sidebar-nav__chevron"></i>
    </a>

    <a href="#" class="sidebar-nav__item">
      <i data-lucide="database"></i>
      <span>Data Lake</span>
      <i data-lucide="chevron-right" class="sidebar-nav__chevron"></i>
    </a>

    <a href="#" class="sidebar-nav__item">
      <i data-lucide="message-circle"></i>
      <span>Collaboration</span>
      <i data-lucide="chevron-down" class="sidebar-nav__chevron"></i>
    </a>

    <div class="sidebar-nav__divider"></div>
    <span class="sidebar-nav__label">Apps</span>

    <a href="#" class="sidebar-nav__item">
      <i data-lucide="layout-grid"></i>
      <span>Demand Planning</span>
    </a>
    <a href="#" class="sidebar-nav__item sidebar-nav__item--add">
      <i data-lucide="plus"></i>
      <span>Add Module</span>
    </a>
  </nav>

  <div class="sidebar-nav__footer">
    <a href="#" class="sidebar-nav__item">
      <i data-lucide="settings"></i>
      <span>Settings</span>
    </a>
    <a href="#" class="sidebar-nav__item">
      <i data-lucide="info"></i>
      <span>Info</span>
    </a>
  </div>
</aside>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Sidebar container | width (collapsed) | `var(--nav-sidebar-collapsed)` — 64px |
| Sidebar container | width (expanded) | `var(--nav-sidebar-width)` — 240px |
| Sidebar container | background | `var(--color-surface)` |
| Sidebar container | border-right | `var(--border-width) var(--border-style) var(--color-border)` |
| Sidebar container | height | `100vh` |
| Sidebar container | position | `fixed` |
| Header | padding | `var(--space-xl)` — 24px top |
| Header to menu gap | spacing | `var(--space-2xl)` — 32px |
| Company name | font-size | `var(--text-h4-size)` — 14px |
| Company name | font-weight | `var(--text-h4-weight)` — 600 |
| Company name | color | `var(--color-text-primary)` |
| Nav item | padding | `var(--space-xs) var(--space-md)` — 8px 16px |
| Nav item | font-size | `var(--text-body-size)` — 14px |
| Nav item | font-weight | `500` |
| Nav item | color | `var(--color-text-secondary)` |
| Nav item | border-radius | `var(--radius-md)` — 8px |
| Nav item icon | size | 20px |
| Nav item icon-to-text gap | gap | `var(--space-sm)` — 12px |
| Between nav items | gap | `var(--space-2xs)` — 4px |
| Active item | background | `var(--color-nav-active-bg)` — light teal |
| Active item | color | `var(--color-nav-active)` — teal |
| Active item icon | color | `var(--color-nav-active)` |
| Hover item | background | `var(--color-nav-hover-bg)` — very light teal |
| Active sub-tab | color | `var(--color-nav-active)` — teal |
| Active sub-tab | font-weight | `600` |
| Inactive sub-tab | color | `var(--color-text-secondary)` |
| Sub-tab | padding-left | `var(--space-2xl)` — 32px (indented under parent) |
| Sub-tab | padding-vertical | `var(--space-2xs)` — 4px |
| Sub-tab | font-size | `var(--text-body-size)` — 14px |
| Between sub-tabs | gap | `var(--space-2xs)` — 4px |
| Section label ("Apps") | font-size | `var(--text-xs-size)` — 12px |
| Section label | font-weight | `var(--text-xs-weight)` — 500 |
| Section label | color | `var(--color-text-muted)` |
| Section label | text-transform | uppercase |
| Section label | letter-spacing | 0.05em |
| Section label | padding | `var(--space-xs) var(--space-md)` |
| Divider | border-top | `var(--border-width) var(--border-style) var(--color-border)` |
| Divider | margin | `var(--space-md) 0` — 16px |
| Footer | margin-top | auto (pushed to bottom) |
| Footer | padding-bottom | `var(--space-lg)` — 20px |
| Chevron icon | size | 16px |
| Chevron icon | color | `var(--color-text-muted)` |
| Logo image | size (collapsed) | 32px |
| Logo image | size (expanded) | 28px |
| Submenu chevron (`::after`) | color (default) | `var(--white-alpha-40)` — semi-transparent |
| Submenu chevron (`::after`) | color (hover) | `white` |
| Flyout panel | transition | opacity/visibility/transform (fade + slide-right) |
| Flyout bridge (`::before`) | purpose | invisible hover bridge zone between icon and flyout |

## Layout Rules — from annotated spacing guides
- **24px** (`var(--space-xl)`) — top padding above company logo
- **32px** (`var(--space-2xl)`) — below company name to first nav item
- **20px** (`var(--space-lg)`) — between main nav groups/sections
- **16px** (`var(--space-md)`) — divider margin, sub-tab section spacing
- **20px** (`var(--space-lg)`) — bottom padding
- Sidebar is full height (`100vh`), fixed position
- Footer items (Settings, Info) pinned to bottom via `margin-top: auto`
- Collapsed: icon centered horizontally, hover shows background highlight only (no tooltip). Submenu items show a flyout panel on hover.
- Expanded: icon + text in flex row, chevron pushed to end via `margin-left: auto`

## States

**Default:**
White background sidebar with gray text items.

**Hover:**
Background shifts to `var(--color-nav-hover-bg)` (very light teal). Transition: `var(--transition-fast)`.

**Active (current page):**
Background `var(--color-nav-active-bg)` (light teal tint), text and icon color `var(--color-nav-active)` (teal). Chevron rotates to down.

**Active sub-tab:**
Text color `var(--color-nav-active)` (teal), font-weight 600. No background change.

**Expanded section:**
Chevron rotates from right to down. Sub-tabs slide in with `var(--transition-base)`.

**Collapsed hover (regular item):**
Background shifts to hover color. No tooltip — just a background highlight.

**Collapsed hover (submenu item):**
Background shifts to hover color, the CSS chevron `::after` turns from `--white-alpha-40` to white. The flyout panel appears to the right via `opacity`/`visibility`/`transform` transition (fade + slide). An invisible bridge zone (`::before` on the flyout) allows the mouse to travel from the icon to the flyout without it closing.

## Mobile Drawer Variant

On mobile, the sidebar is replaced by a full-height drawer that slides in from the left, triggered by a hamburger button in the top nav. The drawer uses the same dark background as the collapsed sidebar.

### Structure
```html
<!-- Hamburger button (inside top-nav, hidden on desktop) -->
<button class="top-nav__hamburger" aria-label="Open menu" onclick="openMobileDrawer()">
  <i data-lucide="menu"></i>
</button>

<!-- Overlay backdrop -->
<div class="mobile-drawer-overlay" id="mobileOverlay" onclick="closeMobileDrawer()"></div>

<!-- Drawer -->
<aside class="mobile-drawer" id="mobileDrawer" aria-label="Mobile navigation">
  <div class="mobile-drawer__header">
    <button class="mobile-drawer__close" aria-label="Close menu" onclick="closeMobileDrawer()">
      <i data-lucide="x"></i>
    </button>
  </div>
  <nav class="mobile-drawer__menu">
    <a href="#" class="mobile-drawer__item mobile-drawer__item--active">
      <i data-lucide="home"></i> Dashboard
    </a>
    <a href="#" class="mobile-drawer__item">
      <i data-lucide="users"></i> Audience
    </a>
    <!-- Expanded sub-items shown inline -->
    <div class="mobile-drawer__submenu">
      <a href="#" class="mobile-drawer__subitem mobile-drawer__subitem--active">Contacts</a>
      <a href="#" class="mobile-drawer__subitem">Lists</a>
    </div>
    <div class="mobile-drawer__divider"></div>
    <a href="#" class="mobile-drawer__item">
      <i data-lucide="settings"></i> Settings
    </a>
  </nav>
  <div class="mobile-drawer__footer">
    <a href="#" class="mobile-drawer__item">
      <i data-lucide="log-out"></i> Log Out
    </a>
  </div>
</aside>
```

### Mobile Drawer Tokens

| Element | Property | Token |
|---------|----------|-------|
| Overlay | background | `rgba(0, 0, 0, 0.5)` |
| Overlay | z-index | `calc(var(--z-modal) + 1)` |
| Overlay | transition | opacity `var(--transition-base)` |
| Drawer | width | `280px`, `max-width: 85vw` |
| Drawer | background | `var(--color-surface-dark)` |
| Drawer | z-index | `calc(var(--z-modal) + 2)` |
| Drawer | transform | `translateX(-100%)` → `translateX(0)` |
| Drawer | transition | transform `var(--transition-base)` |
| Close button | size | 40px |
| Close button | color | `var(--color-white)` |
| Close button | border-radius | `var(--radius-md)` |
| Close button hover | background | `var(--color-dark-item-hover)` |
| Menu item | padding | `var(--space-sm) var(--space-md)` |
| Menu item | font-size | `var(--text-body-size)` |
| Menu item | color | `var(--color-text-on-dark)` |
| Menu item hover | background | `var(--color-dark-item-hover)` |
| Active item | color | `var(--color-text-on-dark-hover)` |
| Active item | font-weight | 600 |
| Sub-item | padding-left | `calc(var(--space-md) + 20px + var(--space-sm))` |
| Sub-item | opacity | 0.6 (inactive), 1 (active/hover) |
| Divider | background | `var(--white-alpha-15)` |
| Hamburger button | size | 40px |
| Hamburger button | icon size | 22px |
| Hamburger button | display | `none` on desktop, `flex` on mobile |

### JavaScript
```js
function openMobileDrawer() {
  document.getElementById('mobileDrawer').classList.add('is-open');
  document.getElementById('mobileOverlay').classList.add('is-visible');
  document.body.style.overflow = 'hidden';
}
function closeMobileDrawer() {
  document.getElementById('mobileDrawer').classList.remove('is-open');
  document.getElementById('mobileOverlay').classList.remove('is-visible');
  document.body.style.overflow = '';
}
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') closeMobileDrawer();
});
```

## Responsive Behavior

**Mobile (< 640px):**
Sidebar hidden. Hamburger button appears in the top nav. Tapping it opens the mobile drawer — a 280px-wide dark panel that slides in from the left with a semi-transparent overlay. Close via X button, overlay tap, or `Escape` key. Body scroll is locked while open.

**Tablet (640-1024px):**
Collapsed mode by default. Expand on hover or toggle button.

**Desktop (> 1024px):**
Expanded mode by default. Toggle button to collapse.

## Accessibility
- **Role:** `<aside>` with `aria-label="Main navigation"`, `<nav>` for menu
- **Keyboard:** `Tab` through items, `Enter`/`Space` to expand sections, `Arrow keys` within menu
- **ARIA:** `aria-current="page"` on active item, `aria-expanded` on expandable sections
- **Collapsed mode:** `aria-label` on every icon-only item
- **Focus visible:** 2px outline `var(--color-nav-active)` with 2px offset

## Variants

**Collapsed:**
64px wide, icon-only. Logo is larger. Two item types: regular items (icon only, hover background highlight) and submenu items (`--has-submenu`) which show a CSS chevron arrow (`::after` pseudo-element) and reveal a flyout panel on hover with title and link items. Flyout transitions in via opacity/visibility/transform (no class toggle).

**Expanded ('Route' approach):**
240px wide, full text labels. Sub-navigation indented below active parent. Expandable sections with chevron.

**Add Module item:**
Uses `plus` icon with muted/dashed styling to indicate it's an action, not a navigation link.

## Do's and Don'ts

**Do:**
- Use teal accent for all sidebar active states (not indigo — indigo is for content actions)
- Keep sub-tabs indented under their parent
- Pin Settings and Info to the bottom
- Show the company name/logo at the top
- Use chevrons to indicate expandable sections

**Don't:**
- Show more than one level of sub-navigation at a time
- Use the sidebar for content actions (that's what buttons are for)
- Mix teal and indigo active states in the sidebar
- Make the sidebar wider than 240px expanded
