# Search & Filter Bar

## Overview
Page-level toolbars for searching, filtering, and sorting content. Five variants support different page types — from simple search bars to full-featured filter toolbars with active filter tags, date ranges, pill filters, and sort controls. Composes buttons, tags/badges, pill filters, and view toggles from the design system. All variants stack vertically on mobile.

## Variants

### A — Default (Title + Date Range + Filters)
Classic two-row layout with hero title, view toggles, date range, filter button with count badge, and primary CTA. Best for booking and scheduling pages.

```html
<div class="filter-bar" role="search">
  <div class="filter-bar__top">
    <h1 class="filter-bar__title">Bookings</h1>
    <div class="view-toggle" role="tablist">
      <button class="view-toggle__item view-toggle__item--active" aria-pressed="true">
        <i data-lucide="layout-grid"></i> <span>Grid</span>
      </button>
      <button class="view-toggle__item" aria-pressed="false">
        <i data-lucide="calendar"></i> <span>Calendar</span>
      </button>
      <button class="view-toggle__item" aria-pressed="false">
        <i data-lucide="map"></i> <span>Map</span>
      </button>
    </div>
  </div>
  <div class="filter-bar__bottom">
    <div class="filter-bar__date">
      <span class="filter-bar__date-label">From</span>
      <input type="date" class="filter-bar__date-input" value="2026-03-21">
    </div>
    <div class="filter-bar__date">
      <span class="filter-bar__date-label">To</span>
      <input type="date" class="filter-bar__date-input" value="2026-03-28">
    </div>
    <button class="filter-bar__filter-btn">
      <i data-lucide="sliders-horizontal"></i> Filters <span class="filter-bar__badge">3</span>
    </button>
    <div class="filter-bar__search">
      <button class="btn btn--primary btn--md"><i data-lucide="search"></i> Apply</button>
    </div>
  </div>
  <div class="filter-bar__count">Showing 36 results</div>
</div>
```

### B — Search-Centric (Search + Filter + Sort + Pills)
Search input as the primary control, with filter/sort buttons and inline pill filters. Best for listing pages (members, products, content).

```html
<div class="filter-bar" role="search">
  <div class="filter-bar__top">
    <h1 class="filter-bar__title">Team Members</h1>
    <div class="filter-bar__search">
      <button class="btn btn--primary btn--md"><i data-lucide="plus"></i> Invite</button>
    </div>
  </div>
  <div class="filter-bar__bottom">
    <div class="filter-bar__search-wrap">
      <span class="filter-bar__search-icon"><i data-lucide="search"></i></span>
      <input type="text" class="filter-bar__search-input" placeholder="Search by name, email, or role...">
    </div>
    <button class="filter-bar__filter-btn">
      <i data-lucide="sliders-horizontal"></i> Filters
    </button>
    <button class="filter-bar__sort-btn">
      <i data-lucide="arrow-up-down"></i> Name
    </button>
    <span class="filter-bar__divider"></span>
    <div class="pill-filter">
      <button class="pill-filter__item pill-filter__item--active">All</button>
      <button class="pill-filter__item">Active</button>
      <button class="pill-filter__item">Pending</button>
    </div>
  </div>
  <div class="filter-bar__count">24 members</div>
</div>
```

### C — Active Filters (Search + Removable Tags)
Search with a row of removable filter tags showing active filters. Filter button uses `--active` modifier when filters are applied. Tags support semantic color variants. Includes "Clear all" action.

```html
<div class="filter-bar" role="search">
  <div class="filter-bar__top">
    <h1 class="filter-bar__title">Events</h1>
    <div class="view-toggle" role="tablist">
      <button class="view-toggle__item view-toggle__item--active" aria-pressed="true">
        <i data-lucide="layout-grid"></i> <span>Cards</span>
      </button>
      <button class="view-toggle__item" aria-pressed="false">
        <i data-lucide="list"></i> <span>List</span>
      </button>
    </div>
  </div>
  <div class="filter-bar__bottom">
    <div class="filter-bar__search-wrap">
      <span class="filter-bar__search-icon"><i data-lucide="search"></i></span>
      <input type="text" class="filter-bar__search-input" placeholder="Search events...">
    </div>
    <button class="filter-bar__filter-btn filter-bar__filter-btn--active">
      <i data-lucide="sliders-horizontal"></i> Filters <span class="filter-bar__badge">4</span>
    </button>
    <button class="filter-bar__sort-btn">
      <i data-lucide="arrow-up-down"></i> Date
    </button>
  </div>
  <div class="filter-bar__active-filters">
    <span class="filter-bar__active-label">Active:</span>
    <span class="tag tag--confirmed">
      <i data-lucide="check-circle-2"></i> Confirmed
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <span class="tag tag--info">
      <i data-lucide="tag"></i> Workshop
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <span class="tag tag--pending">
      <i data-lucide="calendar"></i> Mar 21 – 28
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <span class="tag tag--removable">
      <i data-lucide="users"></i> 10+ attendees
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <button class="filter-bar__clear-all">Clear all</button>
  </div>
  <div class="filter-bar__count">Showing 12 of 48 events</div>
</div>
```

### D — Compact (Embeddable in panels & cards)
Single-row, reduced padding, no card shadow. For embedding inside other containers like card headers, sidebars, or modal content areas.

```html
<div class="filter-bar filter-bar--compact" role="search">
  <div class="filter-bar__bottom">
    <div class="filter-bar__search-wrap">
      <span class="filter-bar__search-icon"><i data-lucide="search"></i></span>
      <input type="text" class="filter-bar__search-input" placeholder="Search...">
    </div>
    <span class="filter-bar__divider"></span>
    <div class="pill-filter">
      <button class="pill-filter__item pill-filter__item--active">All</button>
      <button class="pill-filter__item">Open</button>
      <button class="pill-filter__item">Closed</button>
    </div>
    <button class="filter-bar__filter-btn">
      <i data-lucide="sliders-horizontal"></i> Filters
    </button>
  </div>
</div>
```

### E — Borderless (Blends with page background)
No card wrapper — transparent background, no border or shadow. Blends directly into the page. Good for activity logs, settings pages, or when the filter bar sits above a table that provides its own container.

```html
<div class="filter-bar filter-bar--borderless" role="search">
  <div class="filter-bar__top">
    <h1 class="filter-bar__title">Activity Log</h1>
  </div>
  <div class="filter-bar__bottom">
    <div class="filter-bar__search-wrap">
      <span class="filter-bar__search-icon"><i data-lucide="search"></i></span>
      <input type="text" class="filter-bar__search-input" placeholder="Search activity...">
    </div>
    <div class="filter-bar__date">
      <span class="filter-bar__date-label">From</span>
      <input type="date" class="filter-bar__date-input" value="2026-03-01">
    </div>
    <div class="filter-bar__date">
      <span class="filter-bar__date-label">To</span>
      <input type="date" class="filter-bar__date-input" value="2026-03-25">
    </div>
    <button class="filter-bar__filter-btn">
      <i data-lucide="sliders-horizontal"></i> Filters
    </button>
    <button class="btn btn--outlined btn--md"><i data-lucide="download"></i> Export</button>
  </div>
  <div class="filter-bar__active-filters">
    <span class="filter-bar__active-label">Showing:</span>
    <span class="tag tag--confirmed">
      <i data-lucide="log-in"></i> Sign-ins
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <span class="tag tag--info">
      <i data-lucide="shield"></i> Admin actions
      <button class="tag__remove" aria-label="Remove filter"><i data-lucide="x"></i></button>
    </span>
    <button class="filter-bar__clear-all">Clear all</button>
  </div>
  <div class="filter-bar__count">142 entries</div>
</div>
```

## Slot Reference

All slots are optional. Combine them based on page needs:

| Slot | Element | Used in Variants |
|------|---------|-----------------|
| Title row | `.filter-bar__top` with `.filter-bar__title` | A, B, C, E |
| View toggles | `.view-toggle` inside `__top` | A, C |
| CTA button | `.btn` inside `.filter-bar__search` in `__top` | A, B |
| Search input | `.filter-bar__search-wrap` in `__bottom` | B, C, D, E |
| Date range | `.filter-bar__date` in `__bottom` | A, E |
| Filter button | `.filter-bar__filter-btn` in `__bottom` | All |
| Sort button | `.filter-bar__sort-btn` in `__bottom` | B, C |
| Divider | `.filter-bar__divider` | B, D |
| Pill filters | `.pill-filter` in `__bottom` or below | B, D |
| Active filter tags | `.filter-bar__active-filters` | C, E |
| Result count | `.filter-bar__count` | All |

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | padding | `var(--space-lg)` — 20px |
| Container | border-radius | `var(--radius-lg)` |
| Container | box-shadow | `var(--shadow-card)` |
| Container | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Page title | font-size | `var(--text-hero-size)` — 32px |
| Page title | font-weight | `var(--text-hero-weight)` — 700 |
| Page title | color | `var(--color-text-primary)` |
| Search input | height | 40px |
| Search input | background | `var(--color-bg)` |
| Search input | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Search input | border-radius | `var(--radius-md)` |
| Search input | padding-left | 36px (icon space) |
| Search input focus | border-color | `var(--color-border-focus)` |
| Search input focus | box-shadow | `0 0 0 3px var(--color-focus-ring)` |
| Search icon | color | `var(--color-text-muted)` |
| Search icon | size | 16px |
| Date picker label | font-size | `var(--text-xs-size)` |
| Date picker label | color | `var(--color-text-muted)` |
| Date picker label | text-transform | uppercase |
| Date picker input | height | 40px |
| Date picker input | border-radius | `var(--radius-md)` |
| Filter button | height | 40px |
| Filter button | border-radius | `var(--radius-full)` |
| Filter button | color | `var(--color-text-secondary)` |
| Filter button | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Filter button (active) | background | `var(--color-surface)` |
| Filter button (active) | color | `var(--color-secondary)` |
| Filter button (active) | border-color | `var(--color-secondary)` |
| Filter badge | background | `var(--color-secondary)` |
| Filter badge | color | `var(--color-text-on-colored)` |
| Filter badge | border-radius | `var(--radius-full)` |
| Filter badge | min-width | 20px |
| Sort button | same as filter button |
| Divider | background | `var(--color-border-light)` |
| Divider | width | 1px, height 24px |
| Active tag (default) | background | `var(--color-surface-active)` |
| Active tag (default) | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Active tag (status) | background | `var(--color-success-light)` |
| Active tag (status) | color | `var(--color-success)` |
| Active tag (category) | background | `var(--color-secondary-light)` |
| Active tag (category) | color | `var(--color-secondary)` |
| Active tag (date) | background | `var(--color-pending-light)` |
| Active tag (date) | color | `var(--color-pending-on-light)` |
| Active tag | border-radius | `var(--radius-full)` |
| Active tag | font-size | `var(--text-xs-size)` |
| Active tag icon | size | 12px (remove), 14px (label icon via tag) |
| Clear all button | color | `var(--color-secondary)` |
| Clear all hover | background | `var(--color-secondary-light)` |
| Result count | font-size | `var(--text-small-size)` |
| Result count | color | `var(--color-text-muted)` |
| Compact inputs | height | 36px |

## Modifier Classes

| Modifier | Effect |
|----------|--------|
| `filter-bar--compact` | Reduced padding, no shadow, smaller inputs (36px height) |
| `filter-bar--borderless` | Transparent background, no border/shadow, zero horizontal padding |
| `filter-bar__filter-btn--active` | Highlighted filter button when filters are applied |

## Active Filter Tag Variants

Use `.tag` classes from the Tags & Badges component. Add a `.tag__remove` button inside for removable tags.

| Class | Color Scheme | Use For |
|-------|-------------|---------|
| `tag tag--removable` | Grey surface | Generic filters |
| `tag tag--confirmed` | Green (success) | Status filters (confirmed, active, open) |
| `tag tag--info` | Blue (secondary) | Category/type filters |
| `tag tag--pending` | Amber (pending) | Date/time filters |

## Layout Rules
- Two-row layout: `__top` (title + toggles/CTA) and `__bottom` (controls)
- Top row: `display: flex; justify-content: space-between; align-items: center`
- Bottom row: `display: flex; align-items: flex-end; gap: var(--space-md)`
- Search input: `flex: 1` to fill available space
- Date pickers: `flex: 1` to share available space
- Filter/sort buttons and CTA: `flex-shrink: 0`
- Active filters row: `flex-wrap: wrap` to handle many tags
- Divider: vertical 1px line, 24px tall, for visual grouping
- Gap between rows: `var(--space-md)` (16px)
- Gap between controls: `var(--space-md)` (16px)

## States

**Default:** Filter button is outlined neutral. Search input shows placeholder.

**Hover:** Filter/sort buttons show `var(--color-surface-alt)` background. Search input border unchanged.

**Focus:** Search and date inputs get `0 0 0 3px var(--color-focus-ring)` ring.

**Active filters:** Filter button gains `--active` modifier (blue tint). Badge shows count. Active tags row appears below controls.

**Empty state:** When no filters applied, hide the `__active-filters` row and the badge count.

## Responsive Behavior

**Mobile (< 640px):**
- Container padding reduces to `var(--space-md)`
- Title + view toggles stack vertically
- Title shrinks from `var(--text-hero-size)` to `var(--text-h1-size)`
- View toggle spans full width, text labels hidden — icon-only
- Filter row stacks vertically, all controls go full-width
- Dividers hidden
- Active filter tags wrap naturally

**Tablet (640px - 1024px):**
Two-row horizontal layout. Search input may compress slightly. Pill filters may wrap.

**Desktop (> 1024px):**
Full horizontal layout as designed.

## Accessibility
- `role="search"` on the filter container
- View toggles: `role="tablist"` on group, `aria-pressed` on each toggle
- Keyboard: `Tab` through all controls, `Enter`/`Space` to activate
- Search input: associated with visible placeholder text
- Date inputs: paired with visible labels via `for`/`id` or wrapping
- Remove buttons on active tags: `aria-label="Remove filter"` for screen readers
- Focus visible: ring on all interactive elements

## Do's and Don'ts

**Do:**
- Pick the simplest variant that fits the page — don't use Full-Featured everywhere
- Show the filter count badge when filters are active
- Use `--active` modifier on the filter button when filters are applied
- Use semantic tag colors: `--status` for status, `--category` for types, `--date` for time ranges
- Include a "Clear all" action when showing active filter tags
- Use the compact variant when embedding inside other components
- Show result count to give users feedback on their filtering

**Don't:**
- Mix date range inputs and date active tags — pick one approach per page
- Add more than 3-4 view toggle options
- Hide the filter bar on scroll
- Use the borderless variant inside a card (it's meant for page-level use)
- Hardcode widths — let flex handle sizing
- Show active filter tags when no filters are applied
