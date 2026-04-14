# Tables

## Overview
Data tables for displaying structured lists of users, activity, bookings, and other records. Two style variants: **default** (clean rows with hover highlight) and **striped** (alternating row backgrounds). User cells pair an avatar photo with name and optional metadata.

## Structure

### Variant A: Members Table (Default)

```html
<div class="table-container">
  <div class="table-container__header">
    <h3 class="table-container__title">Team Members</h3>
    <button class="btn btn--primary btn--sm"><i data-lucide="user-plus"></i> Invite Member</button>
  </div>
  <table>
    <colgroup>
      <col style="width: 35%;">
      <col style="width: 20%;">
      <col style="width: 15%;">
      <col style="width: 15%;">
      <col style="width: 15%;">
    </colgroup>
    <thead>
      <tr>
        <th>Member</th>
        <th>Role</th>
        <th>Status</th>
        <th>Joined</th>
        <th style="text-align: right;">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <div class="table-cell-user">
            <div class="avatar avatar--md">
              <img src="assets/avatars/avatar-a03.png" alt="Amara Okafor">
            </div>
            <div class="table-cell-user__info">
              <span class="table-cell-user__name">Amara Okafor</span>
              <span class="table-cell-user__meta">amara@example.com</span>
            </div>
          </div>
        </td>
        <td>Design Lead</td>
        <td><span class="tag tag--confirmed">Active</span></td>
        <td>Jan 15, 2025</td>
        <td>
          <div class="table-cell-actions">
            <button class="btn btn--outlined btn--tiny">Edit</button>
          </div>
        </td>
      </tr>
    </tbody>
  </table>
</div>
```

### Variant B: Compact Striped Table

```html
<div class="table-container">
  <div class="table-container__header">
    <h3 class="table-container__title">Recent Activity</h3>
    <button class="btn btn--outlined btn--sm"><i data-lucide="download"></i> Export</button>
  </div>
  <table class="table--striped">
    <colgroup>
      <col style="width: 25%;">
      <col style="width: 30%;">
      <col style="width: 25%;">
      <col style="width: 20%;">
    </colgroup>
    <thead>
      <tr>
        <th>User</th>
        <th>Action</th>
        <th>Target</th>
        <th>Date</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <div class="table-cell-user">
            <div class="avatar avatar--sm">
              <img src="assets/avatars/avatar-b04.png" alt="Raj Patel">
            </div>
            <span class="table-cell-user__name">Raj Patel</span>
          </div>
        </td>
        <td>Deployed v2.4.1</td>
        <td style="color: var(--color-text-secondary);">Production</td>
        <td style="color: var(--color-text-muted);">Today, 11:15 AM</td>
      </tr>
    </tbody>
  </table>
</div>
```

## User Cell Pattern

The `table-cell-user` pattern is the standard way to display a person in a table row. It pairs an avatar with name and optional secondary info.

```html
<!-- Full user cell (name + email) — use avatar--md -->
<div class="table-cell-user">
  <div class="avatar avatar--md">
    <img src="assets/avatars/avatar-a03.png" alt="Amara Okafor">
  </div>
  <div class="table-cell-user__info">
    <span class="table-cell-user__name">Amara Okafor</span>
    <span class="table-cell-user__meta">amara@example.com</span>
  </div>
</div>

<!-- Compact user cell (name only) — use avatar--sm -->
<div class="table-cell-user">
  <div class="avatar avatar--sm">
    <img src="assets/avatars/avatar-a03.png" alt="Amara Okafor">
  </div>
  <span class="table-cell-user__name">Amara Okafor</span>
</div>
```

Pick avatar photos from `assets/avatars/` — IDs `avatar-a01` to `avatar-a36` and `avatar-b01` to `avatar-b36`. Use different IDs for each person in the same table.

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | border-radius | `var(--radius-lg)` |
| Container | padding | `var(--space-lg)` |
| Container | box-shadow | `var(--shadow-card)` |
| Container | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Table | border-collapse | `collapse` |
| Header section | margin-bottom | `var(--space-md)` |
| Header title | font-size | `var(--text-h3-size)` |
| Header title | font-weight | `var(--text-h3-weight)` |
| Column header | font-size | `var(--text-xs-size)` |
| Column header | font-weight | `600` |
| Column header | color | `var(--color-text-muted)` |
| Column header | text-transform | `uppercase` |
| Column header | letter-spacing | `0.03em` |
| Column header | padding | `var(--space-sm)` |
| Column header | border-bottom | `2px solid var(--color-border)` |
| Column header | white-space | `nowrap` |
| Row cell | padding | `var(--space-sm)` |
| Row cell | border-bottom | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Row hover | background | `var(--color-bg)` |
| Striped even rows | background | `var(--color-bg)` |
| Striped hover | background | `var(--color-surface-active)` |
| User cell | gap | `var(--space-sm)` |
| User name | font-weight | `600` |
| User meta | font-size | `var(--text-xs-size)` |
| User meta | color | `var(--color-text-muted)` |
| Action buttons | gap | `var(--space-xs)` |
| Action buttons | white-space | `nowrap` |

## Layout Rules
- Table spans full width of parent container
- Use `<colgroup>` with `<col>` elements to define explicit column widths when needed
- Action column right-aligned
- User cell uses flex row with `var(--space-sm)` gap
- Avatar `avatar--md` (40px) for full user cells, `avatar--sm` (32px) for compact
- Name truncates with ellipsis when column is narrow (`min-width: 0` on info container)

## Style Variants

| Variant | Class | Row style | Best for |
|---------|-------|-----------|----------|
| Default | *(none)* | Clean rows, hover highlight | Members, settings, editable lists |
| Striped | `table--striped` | Alternating `var(--color-bg)` bands | Activity logs, read-only data, reports |

## States

**Default:**
Clean rows with subtle bottom border.

**Hover:**
Row background shifts to `var(--color-bg)` (default) or `var(--color-surface-active)` (striped).

**Empty:**
Centered text "No results found" with muted icon.

## Responsive Behavior

**Mobile (< 640px):**
Wrap `<table>` in a `.table-scroll` div (`overflow-x: auto; -webkit-overflow-scrolling: touch`) so users can swipe to see all columns. Set `min-width` on `<table>` (e.g. 580px) to prevent column crushing. Table header and footer stay outside the scroll wrapper so they remain fixed. Alternatively, convert to stacked card layout for simpler tables.

```html
<div class="table-container">
  <div class="table-container__header">...</div>
  <div class="table-scroll">
    <table style="min-width: 580px;">...</table>
  </div>
  <div class="table-container__footer">...</div>
</div>
```

**Tablet (640–1024px):**
Horizontal scroll via `overflow-x: auto` on `.table-scroll` container.

**Desktop (> 1024px):**
Full table layout as designed.

## Accessibility
- **Role:** Use semantic `<table>`, `<thead>`, `<tbody>`, `<th>`, `<td>`
- **Keyboard:** `Tab` through action buttons within rows
- **Screen reader:** Column headers associated with cells via `<th scope="col">`
- **Sort:** If sortable, use `aria-sort` on `<th>` elements
- **Avatar alt:** Include user's name in `alt` attribute; if name is visible in same row, use `alt=""`

## Do's and Don'ts

**Do:**
- Use `table-cell-user` for any column showing a person
- Pick distinct avatar IDs for each user in the same table
- Right-align action columns and monetary values
- Use `avatar--md` for primary tables, `avatar--sm` for compact/activity tables

**Don't:**
- Mix avatar sizes within the same table
- Use zebra striping on editable tables (use default style instead)
- Make entire rows clickable if they contain individual action buttons
- Show more than 2 action buttons per row — use a "more" menu instead
