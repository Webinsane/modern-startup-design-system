# Page Layout

## Overview
Defines the structural patterns for assembling full pages. Two primary layouts: **dashboard grid** (card grid, used for overview/listing pages) and **detail page** (main content + sidebar, used for event/resource/article detail pages).

## Layout Patterns

### 1. Dashboard / Listing Page
```
┌─────────────────────────────────────────────┐
│ Top Nav                                     │
├──────┬──────────────────────────────────────┤
│      │ Page Title                            │
│ Side │ ┌────┐ ┌────┐ ┌────┐                │
│ bar  │ │Card│ │Card│ │Card│                 │
│      │ └────┘ └────┘ └────┘                │
│      │ ┌────┐ ┌────┐ ┌────┐                │
│      │ │Card│ │Card│ │Card│                 │
│      │ └────┘ └────┘ └────┘                │
└──────┴──────────────────────────────────────┘
```

### 2. Detail Page (from dashboard.png)
```
┌─────────────────────────────────────────────┐
│ Top Nav                                     │
├──────┬──────────────────────────────────────┤
│      │ ← Back          Card View | Cal View │
│ Side │ ┌──────────────────┬────────────────┐│
│ bar  │ │  Hero Image +    │ Discount Code  ││
│      │ │  Title + Meta    │ Total + CTA    ││
│      │ ├──────────────────┼────────────────┤│
│      │ │  What's on?      │ 284 Attendees  ││
│      │ │  Body text...    │ • Name / Role  ││
│      │ │                  │ • Name / Role  ││
│      │ │  What You'll     │ • Name / Role  ││
│      │ │  Learn           │                ││
│      │ │  ✓ Item  ✓ Item  │                ││
│      │ └──────────────────┴────────────────┘│
└──────┴──────────────────────────────────────┘
```

## Structure — Detail Page
```html
<div class="page-layout">
  <!-- Sidebar nav (fixed) -->
  <aside class="sidebar-nav">...</aside>

  <!-- Top nav (fixed) -->
  <header class="top-nav">...</header>

  <!-- Main content area -->
  <div class="main-content">
    <!-- Page toolbar -->
    <div class="page-toolbar">
      <button class="page-toolbar__back">
        <i data-lucide="arrow-left"></i>
        Back
      </button>
      <nav class="view-toggles">
        <button class="view-toggle view-toggle--active">Card View</button>
        <button class="view-toggle">Calendar View</button>
      </nav>
    </div>

    <!-- Two-column detail layout -->
    <div class="detail-layout">
      <div class="detail-layout__main">
        <!-- Hero, body sections, checklists -->
      </div>
      <div class="detail-layout__sidebar">
        <!-- Discount widget, Attendees widget -->
      </div>
    </div>
  </div>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| **Page shell** | | |
| Main content area | margin-left | `var(--nav-sidebar-width)` or `var(--nav-sidebar-collapsed)` |
| Main content area | padding-top | `var(--top-nav-height)` |
| Main content padding | padding | `var(--space-xl)` — 24px |
| **Page toolbar** | | |
| Toolbar | margin-bottom | `var(--space-xl)` — 24px |
| Toolbar | display | `flex`, `justify-content: space-between`, `align-items: center` |
| Back button | font-size | `var(--text-body-size)` |
| Back button | color | `var(--color-text-secondary)` |
| Back button icon | size | 16px |
| Back button gap | gap | `var(--space-xs)` — 8px |
| **Detail layout** | | |
| Detail container | display | `flex` |
| Detail container | gap | `var(--detail-gap)` — 24px |
| Main column | flex | `1 1 0`, `min-width: 0` |
| Sidebar column | width | `var(--detail-sidebar-width)` — 340px |
| Sidebar column | flex-shrink | `0` |
| **Section spacing** | | |
| Between sections | margin-top | `var(--section-gap)` — 32px |
| Section title to content | margin-bottom | `var(--section-title-gap)` — 16px |
| Section title | font-size | `var(--text-h3-size)` — 16px |
| Section title | font-weight | `var(--text-h3-weight)` — 600 |
| Body text | font-size | `var(--text-body-size)` — 14px |
| Body text | line-height | `var(--text-body-lh)` — 1.5 |
| Body text | color | `var(--color-text-secondary)` |
| Body text max-width | max-width | `var(--detail-content-max)` — 720px |
| **Sidebar widgets** | | |
| Between sidebar widgets | gap | `var(--space-lg)` — 20px |
| Widget card | background | `var(--color-surface)` |
| Widget card | border-radius | `var(--radius-lg)` |
| Widget card | border | `var(--border-width) var(--border-style) var(--color-border)` |
| Widget card | padding | `var(--space-lg)` — 20px |
| Widget card | box-shadow | `var(--shadow-md)` |

## Responsive Behavior

**Mobile (< 640px):**
Detail layout stacks vertically — sidebar below main content. Full-width everything. Toolbar back button only (view toggles hidden or overflow scroll).

**Tablet (640-1024px):**
Detail layout stacks vertically. Sidebar goes full-width below main. Nav sidebar hidden.

**Desktop (> 1024px):**
Full two-column detail layout. Sidebar fixed-width on right.

## Strict Rules for Page Assembly

1. **Every page has three shells:** sidebar nav (fixed left), top nav (fixed top), main content (offset by both)
2. **Content wrapper required:** Page content (below top nav and tabs) MUST be inside a `.content-wrapper` with `max-width: var(--max-width)` (1200px), left-aligned (no centering). The top nav and content tabs stay full-width/fluid — only the page body is constrained. This prevents components from stretching uncomfortably wide on large screens.
3. **Dashboard pages** use `grid` with `repeat(3, 1fr)` on desktop, `repeat(2, 1fr)` on tablet, `1fr` on mobile
4. **Detail pages** use `flex` with main column flexible and sidebar fixed-width
5. **The page toolbar** (back + view toggles) always sits between the top nav and the content
6. **Section spacing** between content blocks is always `var(--section-gap)` (32px)
7. **Sidebar widgets** stack vertically with `var(--space-lg)` (20px) gap
8. **Body text** never exceeds `var(--detail-content-max)` (720px) for readability
9. **Main content padding** is always `var(--space-xl)` (24px) on desktop, `var(--space-md)` (16px) on mobile

## Do's and Don'ts

**Do:**
- Use the detail layout for any single-item view (event, resource, article, booking)
- Keep sidebar widgets in a fixed-width column — they should not stretch
- Add back button on all detail pages for navigation
- Match the view toggles from the search/filter bar component on listing pages

**Don't:**
- Mix dashboard grid and detail layout on the same page
- Let body text stretch full-width without max-width constraint
- Put more than 3 widget cards in the sidebar — it should not outgrow the main content
- Forget the page toolbar on detail pages
