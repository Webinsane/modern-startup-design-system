# Navigation — In-Page Patterns

## Overview
In-page navigation patterns including view toggles (Card/Calendar/Floorplan), tab groups (Month/Week/Day), and content filter pills (Following/My Conversations/My Inbox). For the main application sidebar and top bar, see `sidebar-nav.md` and `top-nav.md`.

## Structure
```html
<!-- View toggles -->
<nav class="view-toggles" role="tablist">
  <button class="view-toggle view-toggle--active" role="tab" aria-selected="true">
    <i data-lucide="layout-grid"></i>
    Card View
  </button>
  <button class="view-toggle" role="tab" aria-selected="false">
    <i data-lucide="calendar-days"></i>
    Calendar View
  </button>
  <button class="view-toggle" role="tab" aria-selected="false">
    <i data-lucide="building"></i>
    Floorplan View
  </button>
</nav>

<!-- Tab group -->
<nav class="tabs" role="tablist">
  <button class="tab tab--active" role="tab">Month</button>
  <button class="tab" role="tab">Week</button>
  <button class="tab" role="tab">Day</button>
</nav>

<!-- Content filter pills -->
<nav class="pill-nav" role="tablist">
  <button class="pill pill--active">Following</button>
  <button class="pill pill--outline">My Conversations</button>
  <button class="pill pill--outline">My Inbox</button>
</nav>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| View toggle (active) | background | `var(--color-primary)` |
| View toggle (active) | color | `var(--color-text-inverse)` |
| View toggle (active) | border-radius | `var(--radius-full)` |
| View toggle (active) | padding | `var(--space-xs) var(--space-md)` |
| View toggle (inactive) | color | `var(--color-text-secondary)` |
| View toggle (inactive) | background | `transparent` |
| Tab (active) | background | `var(--color-primary)` |
| Tab (active) | color | `var(--color-text-inverse)` |
| Tab (active) | border-radius | `var(--radius-full)` |
| Tab (inactive) | background | `var(--color-bg)` |
| Tab (inactive) | color | `var(--color-text-secondary)` |
| Tab (inactive) | border-radius | `var(--radius-full)` |
| Tab group | gap | `var(--space-2xs)` — 4px |
| Pill (active) | background | `var(--color-primary)` |
| Pill (active) | color | `var(--color-text-inverse)` |
| Pill (outlined) | background | `transparent` |
| Pill (outlined) | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Pill (outlined) | color | `var(--color-text-primary)` |
| All pills/tabs | font-size | `var(--text-xs-size)` |
| All pills/tabs | font-weight | `var(--text-xs-weight)` — 500 |

## Layout Rules
- View toggles: horizontal flex, `var(--space-2xs)` gap between items
- Tab groups: horizontal flex, `var(--space-2xs)` gap, contained in a pill-shaped container with `var(--color-bg)` background
- Content filter pills: horizontal flex, `var(--space-xs)` gap

## States

**Default:**
Active item filled with primary color. Inactive items are text-only or outlined.

**Hover:**
Inactive items show background `var(--color-bg)` or `var(--color-primary-light)`.

**Focus visible:**
2px outline `var(--color-primary)` with 2px offset.

## Responsive Behavior

**Mobile (< 640px):**
- **View toggles** become icon-only — wrap text in `<span>` and hide on mobile
- **Content tabs** (underline style) become horizontally scrollable: `overflow-x: auto` with hidden scrollbar (`scrollbar-width: none`, `::-webkit-scrollbar { display: none }`). Padding reduces to `var(--space-md)`, font-size to `var(--text-small-size)`, item padding to `12px var(--space-sm)`
- **Tab groups** (pill style) may also scroll horizontally if they overflow

**Desktop (> 1024px):**
Full text labels visible. No scroll needed.

## Accessibility
- **Role:** `role="tablist"` on container, `role="tab"` on items
- **Keyboard:** Arrow keys navigate between tabs, `Enter`/`Space` activates
- **ARIA:** `aria-selected="true"` on active item
- **Screen reader:** Current selection announced

## Related Components
- **Sidebar navigation:** See `components/sidebar-nav.md`
- **Top navigation bar:** See `components/top-nav.md`

## Do's and Don'ts

**Do:**
- Keep all in-page nav items fully rounded (pill shape)
- Use indigo (`var(--color-primary)`) for in-page active states
- Show icons alongside text in view toggles

**Don't:**
- Use teal for in-page nav — teal is for sidebar/top-nav only
- Mix rounded and square nav items
- Show more than 5 items in a horizontal tab group
