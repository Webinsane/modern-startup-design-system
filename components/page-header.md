# Page Header

## Overview
Unified page header system with composable slots. All variants share the same structural foundation — each slot is independently optional. Combine breadcrumbs, title row, tabs, and controls to build headers for listing pages, detail pages, settings, and dashboards.

## Slot Architecture

Every page header follows this top-to-bottom slot order:

1. **Breadcrumbs** (optional) — navigation trail
2. **Title Row** — title + subtitle on the left, action buttons on the right
3. **Controls** (optional) — search input, filter buttons, sort, pill filters
4. **Tabs** (optional) — secondary navigation for sub-views, sits flush at the bottom edge

## Structure
```html
<div class="page-header">
  <div class="page-header__inner">
    <!-- Slot 1: Breadcrumbs (optional) -->
    <nav class="breadcrumbs" aria-label="Breadcrumb">
      <a href="#" class="breadcrumbs__item">Home</a>
      <span class="breadcrumbs__sep"><i data-lucide="chevron-right"></i></span>
      <a href="#" class="breadcrumbs__item">Section</a>
      <span class="breadcrumbs__sep"><i data-lucide="chevron-right"></i></span>
      <span class="breadcrumbs__item breadcrumbs__item--current">Current Page</span>
    </nav>

    <!-- Slot 2: Title Row (always present) -->
    <div class="page-header__title-row">
      <div class="page-header__title-group">
        <h1 class="page-header__title">Page Title</h1>
        <p class="page-header__subtitle">Optional description text.</p>
        <!-- OR for detail pages, use meta row instead of subtitle -->
        <div class="page-header__meta">
          <span class="page-header__meta-item"><i data-lucide="calendar"></i> Mar 28, 2026</span>
          <span class="page-header__meta-item"><i data-lucide="map-pin"></i> Room 4B</span>
          <span class="tag tag--confirmed">Confirmed</span>
        </div>
      </div>
      <div class="page-header__actions">
        <button class="btn btn--ghost btn--md"><i data-lucide="settings"></i> Manage</button>
        <button class="btn btn--primary btn--md"><i data-lucide="plus"></i> Create</button>
      </div>
    </div>

    <!-- Slot 3: Controls (optional) -->
    <div class="page-header__controls">
      <div class="page-header__search">
        <span class="page-header__search-icon"><i data-lucide="search"></i></span>
        <input type="text" class="page-header__search-input" placeholder="Search...">
      </div>
      <div class="page-header__filters">
        <button class="filter-bar__filter-btn"><i data-lucide="sliders-horizontal"></i> Filters (2)</button>
        <div class="pill-filter">
          <button class="pill-filter__item pill-filter__item--active">All</button>
          <button class="pill-filter__item">Category</button>
        </div>
      </div>
      <div class="page-header__sort">
        <button class="btn btn--ghost btn--sm"><i data-lucide="arrow-up-down"></i> Sort</button>
      </div>
    </div>
  </div>

  <!-- Slot 4: Tabs (optional — outside __inner, flush with edges) -->
  <div class="page-header__tabs">
    <div class="content-tabs">
      <a href="#" class="content-tabs__item content-tabs__item--active">Tab One</a>
      <a href="#" class="content-tabs__item">Tab Two</a>
      <a href="#" class="content-tabs__item">Tab Three</a>
    </div>
  </div>
</div>
```

## Variants

| Variant | Slots used | Use case |
|---------|-----------|----------|
| **Base** | Title + subtitle | Simple section headers |
| **WithActions** | Title + actions | Primary listing pages |
| **WithBreadcrumbs** | Breadcrumbs + title + actions | Nested pages (settings, sub-sections) |
| **WithTabs** | Title + actions + tabs | Pages with sub-views |
| **WithControls** | Title + search + filters + sort | Filterable listing pages |
| **Full** | All slots | Complex listing pages with filters and sub-views |
| **Detail Page** | Breadcrumbs + title + meta + actions + tabs | Entity detail pages (event, project, room) |

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | border-radius | `var(--radius-lg)` |
| Container | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Container | box-shadow | `var(--shadow-card)` |
| Inner padding | padding | `var(--space-lg) var(--space-xl)` — 20px 24px |
| **Breadcrumbs** | | |
| Breadcrumb item | font-size | `var(--text-small-size)` — 13px |
| Breadcrumb item | color | `var(--color-text-muted)` |
| Breadcrumb hover | color | `var(--color-secondary)` |
| Current breadcrumb | color | `var(--color-text-primary)` |
| Current breadcrumb | font-weight | `500` |
| Separator icon | size | 14px |
| Separator | color | `var(--color-text-muted)` |
| Breadcrumbs gap | gap | `var(--space-2xs)` — 4px |
| Breadcrumbs margin | margin-bottom | `var(--space-sm)` — 12px |
| **Title Row** | | |
| Title | font-size | `var(--text-hero-size)` — 32px |
| Title | font-weight | `var(--text-hero-weight)` — 700 |
| Title | color | `var(--color-text-primary)` |
| Subtitle | font-size | `var(--text-body-size)` — 14px |
| Subtitle | color | `var(--color-text-secondary)` |
| Subtitle | margin-top | `var(--space-2xs)` — 4px |
| Title-to-actions gap | gap | `var(--space-md)` — 16px |
| Actions gap | gap | `var(--space-sm)` — 12px |
| **Meta Row** (detail pages) | | |
| Meta row | margin-top | `var(--space-xs)` — 8px |
| Meta row gap | gap | `var(--space-md)` — 16px |
| Meta item | font-size | `var(--text-small-size)` — 13px |
| Meta item | color | `var(--color-text-muted)` |
| Meta item icon | size | 14px |
| Meta item icon-to-text gap | gap | `var(--space-2xs)` — 4px |
| **Controls Row** | | |
| Controls | margin-top | `var(--space-lg)` — 20px |
| Controls gap | gap | `var(--space-md)` — 16px |
| Search input | height | 36px |
| Search input | background | `var(--color-bg)` |
| Search input | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Search input | border-radius | `var(--radius-md)` |
| Search input focus | border-color | `var(--color-border-focus)` |
| Search icon | size | 16px |
| Search icon | color | `var(--color-text-muted)` |
| Filter button | follows `filter-bar__filter-btn` pattern |
| Pill filters | follows `pill-filter` / `pill-filter__item` pattern |
| Sort button | follows `btn--ghost btn--sm` |
| **Tabs Slot** | | |
| Tabs wrapper | border-top | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Tab items | follow `content-tabs` / `content-tabs__item` pattern |

## Layout Rules
- `.page-header` is the outer container with border-radius and shadow
- `.page-header__inner` holds all content with horizontal padding; tabs sit outside it for edge-to-edge alignment
- Title row uses `display: flex; justify-content: space-between; align-items: flex-start` — actions stay top-right
- Controls row uses flex with auto-margin on sort to push it right
- Search input is flex `1` with `min-width: 200px; max-width: 320px`
- Tabs are separated from inner content by a top border

## States

**Default:**
Clean white card surface. Breadcrumb links are muted, current page is bolder.

**Breadcrumb hover:**
Color shifts to `var(--color-secondary)`.

**Search focus:**
Border becomes `var(--color-border-focus)` with focus ring.

**Active tab:**
Blue underline indicator via `content-tabs__item--active`.

## Responsive Behavior

**Mobile (< 640px):**
- Inner padding reduces to `var(--space-md)`
- Title row stacks vertically (column direction)
- Title shrinks from `var(--text-hero-size)` to `var(--text-h1-size)`
- Actions span full width
- Controls stack vertically, search takes full width
- Sort button loses auto margin-left
- Tabs scroll horizontally if many items

**Tablet (640px – 1024px):**
Horizontal layout preserved. Search may be narrower.

**Desktop (> 1024px):**
Full layout as designed.

## Accessibility
- **Breadcrumbs:** Wrap in `<nav>` with `aria-label="Breadcrumb"`
- **Current page:** Use `aria-current="page"` on the last breadcrumb item
- **Search:** Associate with a visually hidden `<label>` or use `aria-label`
- **Tabs:** Follow `content-tabs` accessibility pattern (see `top-nav-tabs.md`)
- **Heading level:** Use `<h1>` for the page title; ensure only one `<h1>` per page

## Do's and Don'ts

**Do:**
- Keep breadcrumb trails short (3–4 levels max)
- Use a single primary action button; additional actions should be ghost or outlined
- Place the most important action rightmost in the actions group
- Use the meta row (with icons) for entity detail pages instead of a plain subtitle

**Don't:**
- Nest a page header inside another page header
- Use more than 6 tabs — consolidate views or use a different navigation pattern
- Put form fields in the title row — use the controls slot instead
- Omit the title — it's the only required slot
