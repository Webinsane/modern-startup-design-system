# Empty States

## Overview
Shown when a list, table, or content area has no data to display. Communicates what the area is for, why it's empty, and what action the user can take. Supports full-size and compact variants, an optional dashed-border frame, and semantic icon tints (info, success, warning, error).

## Structure

### Default (card-wrapped)
```html
<div class="card">
  <div class="empty-state">
    <div class="empty-state__icon"><i data-lucide="inbox" style="width: 64px; height: 64px;"></i></div>
    <h3 class="empty-state__title">No items yet</h3>
    <p class="empty-state__desc">This area will populate once records are created. Use the button below to add your first entry.</p>
    <button class="btn btn--primary btn--md"><i data-lucide="plus"></i> Create New</button>
  </div>
</div>
```

### Bordered (dashed border, no card wrapper)
```html
<div class="empty-state empty-state--bordered">
  <div class="empty-state__icon"><i data-lucide="upload" style="width: 64px; height: 64px;"></i></div>
  <h3 class="empty-state__title">Drop files here</h3>
  <p class="empty-state__desc">Drag and drop files into this area, or click to browse. Accepts images, PDFs, and documents up to 25 MB.</p>
  <button class="btn btn--outline btn--md"><i data-lucide="folder-open"></i> Browse Files</button>
</div>
```

### Compact (smaller icon, tighter spacing for inline panels)
```html
<div class="card">
  <div class="empty-state empty-state--compact">
    <div class="empty-state__icon"><i data-lucide="search"></i></div>
    <h3 class="empty-state__title">No results found</h3>
    <p class="empty-state__desc">Try adjusting your search terms or removing filters to see more results.</p>
    <button class="btn btn--outline btn--sm">Clear Filters</button>
  </div>
</div>
```

### Compact with icon tint
```html
<!-- Info tint -->
<div class="empty-state empty-state--compact empty-state--info">
  <div class="empty-state__icon"><i data-lucide="calendar-days"></i></div>
  <h3 class="empty-state__title">No upcoming events</h3>
  <p class="empty-state__desc">Your schedule is clear. Events and meetings will appear here once they are booked.</p>
</div>

<!-- Success tint — all-clear / caught-up state -->
<div class="empty-state empty-state--compact empty-state--success">
  <div class="empty-state__icon"><i data-lucide="check-circle"></i></div>
  <h3 class="empty-state__title">All caught up</h3>
  <p class="empty-state__desc">You've resolved every notification. New alerts will appear here when they arrive.</p>
</div>

<!-- Warning tint — incomplete / needs attention -->
<div class="empty-state empty-state--compact empty-state--warning">
  <div class="empty-state__icon"><i data-lucide="alert-triangle"></i></div>
  <h3 class="empty-state__title">Setup incomplete</h3>
  <p class="empty-state__desc">Finish configuring this integration to start receiving data. One required step remains.</p>
  <button class="btn btn--primary btn--sm">Complete Setup</button>
</div>

<!-- Error tint — failed / unreachable -->
<div class="empty-state empty-state--compact empty-state--error">
  <div class="empty-state__icon"><i data-lucide="wifi-off"></i></div>
  <h3 class="empty-state__title">Unable to load data</h3>
  <p class="empty-state__desc">Something went wrong while fetching records. Check your connection and try again.</p>
  <button class="btn btn--outline btn--sm"><i data-lucide="refresh-cw"></i> Retry</button>
</div>
```

### Bordered compact (empty table / list placeholder)
```html
<div class="empty-state empty-state--bordered empty-state--compact">
  <div class="empty-state__icon"><i data-lucide="users"></i></div>
  <h3 class="empty-state__title">No team members</h3>
  <p class="empty-state__desc">Invite people to collaborate on this project. Members will be listed here.</p>
  <button class="btn btn--primary btn--sm"><i data-lucide="user-plus"></i> Invite Members</button>
</div>
```

## Tokens Used

### Container

| Element | Property | Token |
|---------|----------|-------|
| Container | text-align | `center` |
| Container | padding | `var(--space-2xl)` — 32px |
| Icon wrapper | size | 72px |
| Icon wrapper | margin | `0 auto var(--space-sm)` |
| Icon wrapper | color | `var(--color-text-muted)` |
| Icon wrapper | opacity | `0.5` |
| Title | font-size | `var(--text-h3-size)` |
| Title | font-weight | `var(--text-h3-weight)` |
| Title | color | `var(--color-text-primary)` |
| Title | margin-bottom | `var(--space-2xs)` |
| Description | font-size | `var(--text-small-size)` |
| Description | color | `var(--color-text-secondary)` |
| Description | max-width | 320px |
| Description | margin | `0 auto var(--space-md)` |
| CTA button | follows `btn--primary btn--md` or `btn--outline btn--sm` |

### Compact Variant (`--compact`)

| Element | Property | Token |
|---------|----------|-------|
| Container | padding | `var(--space-lg)` |
| Icon wrapper | size | 40px |
| Icon wrapper | margin-bottom | `var(--space-sm)` |
| Title | font-size | `var(--text-h4-size)` |
| Title | font-weight | `var(--text-h4-weight)` |
| Description | font-size | `var(--text-xs-size)` |
| Description | max-width | 260px |
| Description | margin-bottom | `var(--space-md)` |

### Bordered Variant (`--bordered`)

| Element | Property | Token |
|---------|----------|-------|
| Container | border | `var(--border-width-thick) dashed var(--color-border)` |
| Container | border-radius | `var(--radius-xl)` |
| Container | background | `var(--color-bg)` |

### Icon Tint Variants

| Modifier | Icon color | Opacity |
|----------|-----------|---------|
| `--info` | `var(--color-secondary)` | 0.7 |
| `--success` | `var(--color-success)` | 0.7 |
| `--warning` | `var(--color-warning)` | 0.7 |
| `--error` | `var(--color-error)` | 0.7 |

## Layout Rules
- Centered within parent container
- Vertical stack: icon → title → description → CTA (optional)
- Description text constrained to 320px (260px in compact) for readability
- CTA button is optional — omit it when the user cannot resolve the empty state themselves
- Bordered variant does not need a `.card` wrapper; default and compact do

## States
Single state — always visible when content is empty.

## Responsive Behavior
Stays centered and stacked at all breakpoints. No layout changes needed. Padding and icon size scale down naturally in compact variant.

## Accessibility
- **Role:** `role="status"` with `aria-live="polite"` if content may appear dynamically
- **Screen reader:** Title and description provide context for why the area is empty
- **CTA:** Clearly labeled action button
- **Color:** Icon tints are decorative — the title and description convey meaning without relying on color

## Sub-components

**Size variants:**
- Default — 64px icon, `var(--space-2xl)` padding, `h3`-sized title
- `empty-state--compact` — 40px icon, `var(--space-lg)` padding, `h4`-sized title

**Frame variants:**
- Default — no border, meant to sit inside a `.card`
- `empty-state--bordered` — dashed border with `var(--color-bg)` background, standalone

**Icon tint variants:**
- `empty-state--info` — Blue icon, informational context (empty calendar, no data yet)
- `empty-state--success` — Green icon, all-clear state (caught up, completed)
- `empty-state--warning` — Yellow icon, needs attention (incomplete setup)
- `empty-state--error` — Red icon, failure state (load error, connection lost)

## Do's and Don'ts

**Do:**
- Keep text concise and actionable
- Include a clear CTA when the user can resolve the empty state
- Use compact variant inside sidebar panels, table bodies, and inline sections
- Use bordered variant for drop zones and standalone placeholder areas
- Choose an icon tint that matches the semantic meaning of the empty state

**Don't:**
- Show empty states for briefly loading content (use skeleton instead)
- Use sad or negative imagery — keep it neutral and helpful
- Combine bordered + card wrapper — pick one framing approach
- Use icon tints without matching the meaning (e.g., success tint for an error state)
