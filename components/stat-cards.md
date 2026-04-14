# Stat Cards

## Overview
Dashboard stat cards displayed in a 4-column grid with period selector. Each card shows a metric value, label, trend badge, and optional chart visualization.

Two height variants prevent empty space at the bottom of cards:
- **Compact** (`.stat-card--compact`) — reduced padding and smaller value; use when the card has only a value + label, no charts or visualizations.
- **Detailed** (`.stat-card--detailed`) — fills height via `min-height` and `justify-content: space-between`; use when the card includes bar charts, donut charts, progress bars, avatar rows, tag rows, or any visual content below the value.

The base `.stat-card` (no modifier) still works, but mixing it with compact or detailed cards in the same row will create uneven heights. Always pick a variant.

## Compact Card Structure
```html
<div class="stat-card stat-card--compact">
  <div class="stat-card__header">
    <span class="stat-card__title">Total Revenue</span>
    <span class="stat-card__badge" style="background: var(--color-success-light); color: var(--color-success);">
      <i data-lucide="trending-up" style="width: 10px; height: 10px; display: inline-block; vertical-align: -1px; margin-right: 2px;"></i>12%
    </span>
  </div>
  <div class="stat-card__value stat-card__value--hero">$48.2k</div>
  <div class="stat-card__label">vs $43.1k last month</div>
</div>
```

Use compact for:
- Simple KPI readouts (revenue, active users, session time)
- Any card with only header → value → label and no visual below
- Rows where all 4 cards are value-only — they'll share the same tight height

## Detailed Card Structure

### With Bar Chart
```html
<div class="stat-card stat-card--detailed">
  <div class="stat-card__header">
    <span class="stat-card__title">Weekly Commits</span>
    <span class="stat-card__badge" style="background: var(--color-success-light); color: var(--color-success);">
      <i data-lucide="trending-up" style="width: 10px; height: 10px; display: inline-block; vertical-align: -1px; margin-right: 2px;"></i>24%
    </span>
  </div>
  <div class="stat-card__value">186</div>
  <div class="stat-card__bars" style="margin-top: var(--space-sm);">
    <div class="stat-card__bar stat-card__bar--muted" style="height:35%"></div>
    <div class="stat-card__bar stat-card__bar--primary" style="height:80%"></div>
    <div class="stat-card__bar stat-card__bar--primary" style="height:100%"></div>
    <!-- ... more bars -->
  </div>
  <div class="stat-card__footer">Mon – Sun</div>
</div>
```

### With Progress Bar
```html
<div class="stat-card stat-card--detailed">
  <div class="stat-card__header">
    <span class="stat-card__title">Sprint Progress</span>
    <span class="tag tag--confirmed" style="font-size: 10px; padding: 2px 8px;">On Track</span>
  </div>
  <div class="stat-card__value">73%</div>
  <div class="progress" style="margin-top: var(--space-sm);">
    <div class="progress__fill progress__fill--green" style="width:73%"></div>
  </div>
  <div class="stat-card__label" style="margin-top: var(--space-xs);">18 of 25 tasks complete</div>
</div>
```

### With Donut Chart
```html
<div class="stat-card stat-card--detailed">
  <div class="stat-card__header">
    <span class="stat-card__title">Task Breakdown</span>
  </div>
  <div class="stat-card__donut" style="margin-top: var(--space-xs);">
    <svg viewBox="0 0 36 36" style="width: 72px; height: 72px; flex-shrink: 0; transform: rotate(-90deg);">
      <circle cx="18" cy="18" r="15.5" fill="none" stroke="var(--color-border-light)" stroke-width="3"></circle>
      <circle cx="18" cy="18" r="15.5" fill="none" stroke="var(--color-success)" stroke-width="3" stroke-dasharray="58 97.4" stroke-linecap="round"></circle>
      <!-- ... more segments -->
    </svg>
    <div class="stat-card__donut-legend">
      <div class="stat-card__legend-item">
        <span class="stat-card__legend-dot" style="background: var(--color-success);"></span> Done — 60%
      </div>
      <!-- ... more legend items -->
    </div>
  </div>
</div>
```

### With Avatars / Tags
```html
<div class="stat-card stat-card--detailed">
  <div class="stat-card__header">
    <span class="stat-card__title">Open Issues</span>
    <span class="stat-card__badge" style="background: var(--color-error-light); color: var(--color-error);">
      <i data-lucide="trending-up" style="width: 10px; height: 10px; display: inline-block; vertical-align: -1px; margin-right: 2px;"></i>5
    </span>
  </div>
  <div class="stat-card__value">23</div>
  <div style="display: flex; gap: var(--space-xs); margin-top: var(--space-sm);">
    <span class="tag tag--alert" style="font-size: 10px; padding: 2px 8px;">4 Critical</span>
    <span class="tag tag--pending" style="font-size: 10px; padding: 2px 8px;">8 Medium</span>
    <span class="tag tag--info" style="font-size: 10px; padding: 2px 8px;">11 Low</span>
  </div>
</div>
```

Use detailed for:
- Cards with bar charts (`stat-card__bars`)
- Cards with donut charts (`stat-card__donut`)
- Cards with progress bars (`.progress`)
- Cards with avatar groups or tag rows below the value
- Any card that has visual content below the value/label

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Grid | columns | `repeat(4, 1fr)` → 2 at 1024px → 1 at 640px |
| Grid | gap | `var(--space-md)` |
| Card | background | `var(--color-surface)` |
| Card | border-radius | `var(--radius-lg)` |
| Card | box-shadow | `var(--shadow-card)` |
| Card | border | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Card (default) | padding | `var(--space-lg)` |
| Card (compact) | padding | `var(--space-md) var(--space-lg)` |
| Card (detailed) | min-height | `200px` |
| Header | margin-bottom | `var(--space-sm)` (default), `var(--space-2xs)` (compact) |
| Title | font-size | `var(--text-small-size)` |
| Title | font-weight | `500` |
| Title | color | `var(--color-text-secondary)` |
| Value (default) | font-size | `var(--text-h1-size)` |
| Value (compact) | font-size | `var(--text-h2-size)` |
| Value (hero) | font-size | `var(--text-hero-size)` |
| Badge up | color | `var(--color-success)` |
| Badge down | color | `var(--color-error)` |

## Layout Rules
- `.stats-grid` uses CSS grid: 4 columns on desktop, 2 on tablet, 1 on mobile
- Each `.stat-card` is a flex column (`display: flex; flex-direction: column`)
- `--detailed` uses `justify-content: space-between` to spread content vertically and fill height
- `--compact` reduces padding to eliminate bottom whitespace on simple cards
- Section header sits above the grid with title left-aligned and period selector right-aligned

## Choosing a Variant

| Card content | Variant | Why |
|---|---|---|
| Value + label only | `--compact` | Tight padding, no wasted vertical space |
| Value + badge + label | `--compact` | Still minimal content, compact fits |
| Value + bar chart + footer | `--detailed` | Chart fills the extra height |
| Value + progress bar + sublabel | `--detailed` | Progress bar needs room |
| Value + donut + legend | `--detailed` | Donut + legend fills the card |
| Value + avatar row or tag row | `--detailed` | Extra content fills height |

**Rule of thumb:** If the card has anything below `stat-card__label`, use `--detailed`. If it stops at the label, use `--compact`.

## Do's and Don'ts

**Do:**
- Always use `--compact` or `--detailed` — don't leave cards as bare `.stat-card` in a mixed row
- Use consistent variants across a row when possible (all compact OR all detailed)
- Show trend direction with the badge (trending-up/trending-down icon + percentage)
- Keep metric labels short and scannable

**Don't:**
- Mix bare `.stat-card` and `--detailed` in the same grid row (creates uneven heights)
- Use `--compact` on a card that has a chart — it will clip or look cramped
- Use `--detailed` on a value-only card — it will have dead space at the bottom
- Use more than 4 stat cards in a single grid row
- Use stat cards for non-numeric content
- Omit the trend badge — it provides essential context
