# Schedule Card

## Overview
Day-view schedule card displaying meetings with time ranges, events with avatar and type badge, and absences with stacked avatar groups. Used in calendar day views, team dashboards, and scheduling panels. The card is divided into sections — each with a grey uppercase label header, count, and trailing icon. An `--important` variant provides a green-tinted header for high-priority items. Event rows support an optional description line below the name.

## Structure

```html
<div class="day-card">
  <div class="day-card__header">
    <div class="day-card__date-wrapper">
      <div class="day-card__date-icon"><i data-lucide="calendar"></i></div>
      <h2 class="day-card__date">March 23, 2026</h2>
    </div>
    <button class="day-card__more" aria-label="More options">
      <i data-lucide="more-horizontal"></i>
    </button>
  </div>

  <!-- Important Section: green tinted header for high-priority items -->
  <div class="day-card__section">
    <div class="section-header section-header--important">
      <span class="section-header__label">Important (1)</span>
      <i data-lucide="alert-circle" class="section-header__icon"></i>
    </div>
    <div class="event-row">
      <div class="event-row__left">
        <img class="event-row__avatar" src="assets/avatars/avatar-b12.png" alt="Kai Nakamura">
        <div>
          <span class="event-row__name">Kai Nakamura</span>
          <div class="event-row__desc">Final day before parental leave</div>
        </div>
      </div>
      <span class="event-badge event-badge--vacation">
        <i data-lucide="palm-tree"></i> Leave
      </span>
    </div>
  </div>

  <!-- Meetings Section: grey header, left-bordered items with time ranges -->
  <div class="day-card__section">
    <div class="section-header section-header--meetings">
      <span class="section-header__label">Meetings (2)</span>
      <i data-lucide="video" class="section-header__icon"></i>
    </div>
    <div class="meeting-item">
      <div class="meeting-item__title">Stakeholder Review</div>
      <div class="meeting-item__time">11:00 am <span class="meeting-item__sep">—</span> 12:00 pm</div>
    </div>
    <div class="meeting-item">
      <div class="meeting-item__title">Design Critique — Q2 Layouts</div>
      <div class="meeting-item__time">3:00 pm <span class="meeting-item__sep">—</span> 4:00 pm</div>
    </div>
  </div>

  <!-- Events Section: grey header, avatar row with event-type badge -->
  <div class="day-card__section">
    <div class="section-header section-header--events">
      <span class="section-header__label">Events (1)</span>
      <i data-lucide="party-popper" class="section-header__icon"></i>
    </div>
    <div class="event-row">
      <div class="event-row__left">
        <img class="event-row__avatar" src="assets/avatars/avatar-a15.png" alt="Nadia Osei">
        <div>
          <span class="event-row__name">Nadia Osei</span>
          <div class="event-row__desc">Turning 30 — team cake at 3pm</div>
        </div>
      </div>
      <span class="event-badge event-badge--birthday">
        <i data-lucide="cake"></i> Birthday
      </span>
    </div>
  </div>

  <!-- Absences Section: grey header, stacked avatar group with overflow count -->
  <div class="day-card__section">
    <div class="section-header section-header--absences">
      <span class="section-header__label">Absences (8)</span>
      <i data-lucide="calendar-x" class="section-header__icon"></i>
    </div>
    <div class="absence-row">
      <div class="absence-row__left">
        <div class="avatar-group">
          <img class="avatar-group__item" src="assets/avatars/avatar-b03.png" alt="User">
          <img class="avatar-group__item" src="assets/avatars/avatar-a08.png" alt="User">
          <span class="avatar-group__initials avatar-group__initials--orange">HG</span>
          <img class="avatar-group__item" src="assets/avatars/avatar-a22.png" alt="User">
          <span class="avatar-group__initials avatar-group__initials--yellow">TP</span>
          <span class="avatar-group__count">+3</span>
        </div>
      </div>
      <span class="event-badge event-badge--holiday">
        <i data-lucide="snowflake"></i> Public Holiday
      </span>
    </div>
  </div>
</div>
```

## Tokens Used

### Card Container

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | border-radius | `var(--radius-xl)` |
| Container | box-shadow | `var(--shadow-md)` |
| Container | padding | `var(--space-xl)` |
| Container | width | `100%` |
| Date icon | color | `var(--color-text-muted)` |
| Date icon | flex-shrink | 0 |
| Date icon `[data-lucide]` | size | 22px |
| Date text | font-size | `var(--text-h2-size)` |
| Date text | font-weight | `var(--text-h2-weight)` |
| Header bottom border | border-bottom | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Menu button | size | 32px |
| Menu button | border-radius | `var(--radius-full)` |
| Menu button hover | background | `var(--color-surface-alt)` |

### Section Headers

| Element | Property | Token |
|---------|----------|-------|
| All section headers | padding | `var(--space-xs) var(--space-sm)` |
| All section headers | border-radius | `var(--radius-md)` |
| All section headers | margin-bottom | `var(--space-md)` |
| Label text | font-size | `var(--text-xs-size)` |
| Label text | font-weight | 700 |
| Label text | letter-spacing | 0.05em |
| Label text | text-transform | uppercase |
| Meetings header | background | `var(--color-surface-alt)` |
| Meetings label | color | `var(--color-text-secondary)` |
| Meetings icon | color | `var(--color-text-muted)` |
| Events header | background | `var(--color-surface-alt)` |
| Events label | color | `var(--color-text-secondary)` |
| Events icon | color | `var(--color-text-muted)` |
| Absences header | background | `var(--color-surface-alt)` |
| Absences label | color | `var(--color-text-secondary)` |
| Absences icon | color | `var(--color-text-muted)` |
| Important header | background | `var(--color-success-light)` |
| Important label | color | `var(--color-success-text)` |
| Important icon | color | `var(--color-success)` |
| Section icon | size | 20px |

### Meeting Items

| Element | Property | Token |
|---------|----------|-------|
| Container | padding-left | `var(--space-md)` |
| Container | border-left | `var(--border-width-thick) var(--border-style) var(--color-secondary)` |
| Title | font-size | `var(--text-h4-size)` |
| Title | font-weight | `var(--text-h4-weight)` |
| Time | font-size | `var(--text-small-size)` |
| Time | color | `var(--color-text-muted)` |

### Event Rows

| Element | Property | Token |
|---------|----------|-------|
| Avatar | size | 36px |
| Avatar | border-radius | `var(--radius-full)` |
| Name | font-size | `var(--text-body-size)` |
| Name | font-weight | `var(--text-h4-weight)` |
| Description | font-size | `var(--text-small-size)` |
| Description | color | `var(--color-text-muted)` |
| Description | margin-top | 2px |

### Event Badges

| Element | Property | Token |
|---------|----------|-------|
| All badges | padding | `var(--space-2xs) var(--space-sm)` |
| All badges | border-radius | `var(--radius-full)` |
| All badges | font-size | `var(--text-xs-size)` |
| All badges | font-weight | `var(--text-xs-weight)` |
| Badge icon | size | 14px |
| Birthday | background | `#FDE8F0` |
| Birthday | color | `#C44D7B` |
| Public Holiday | background | `#E8E0F8` |
| Public Holiday | color | `#7C5CBF` |
| Vacation | background | `var(--color-success-light)` |
| Vacation | color | `var(--color-success-text)` |

### Avatar Group (in absences)

| Element | Property | Token |
|---------|----------|-------|
| Avatar item | size | 36px |
| Avatar item | border-radius | `var(--radius-full)` |
| Avatar item | border | `2px solid var(--color-surface)` |
| Overlap | margin-left | -8px (after first) |
| Initials fallback | font-size | `var(--text-xs-size)` |
| Initials fallback | font-weight | 700 |
| Initials `--blue` | background | `var(--color-blue-50)` |
| Initials `--yellow` | background | `var(--color-yellow)` |
| Initials `--green` | background | `var(--color-green)` |
| Initials `--pink` | background | `var(--color-pink)` |
| Initials `--orange` | background | `var(--color-orange)` |
| Count text | font-size | `var(--text-body-size)` |
| Count text | font-weight | 600 |

## Layout Rules
- Card width: `100%` (fills its grid/container column)
- Section spacing: `var(--space-lg)` (20px) between sections
- Meeting items: `var(--space-sm)` (12px) between each
- Section headers: `var(--space-md)` (16px) margin below
- Avatar group overlap: -8px with 2px white border ring
- Event rows: avatar (36px) + name on left, badge on right, space-between

## States

**Default:**
White background, rounded corners, subtle shadow.

**Hover (menu button):**
Background shifts to `var(--color-surface-alt)`, color to `var(--color-text-primary)`. Transition: `var(--transition-fast)`.

## Responsive Behavior

**Mobile (< 640px):**
Card goes full-width. Avatar groups may truncate to fewer visible avatars with adjusted count.

**Tablet (640px - 1024px):**
Card fills its container column. Works in single or two-column layouts.

**Desktop (> 1024px):**
Card fills its grid column. Place in multi-column grids to control width via grid tracks.

## Accessibility
- **Role:** Use `<article>` for self-contained card
- **Keyboard:** Menu button focusable via `Tab`, activated with `Enter`/`Space`
- **Screen reader:** Date announced as heading. Section labels provide context. Avatar groups use `aria-label` for count.
- **Focus visible:** 2px outline with 2px offset on interactive elements
- **Color:** Event type badges always include text labels, never rely on color alone

## Sub-components

**Section header variants:**
- `section-header--meetings` — Grey background, video icon
- `section-header--events` — Grey background, party-popper icon
- `section-header--absences` — Grey background, calendar-x icon
- `section-header--important` — Green tinted background (`var(--color-success-light)`), alert-circle icon

**Event row elements:**
- `event-row__name` — Person name, bold weight
- `event-row__desc` — Optional description line below the name (muted, smaller text). When using a description, wrap `event-row__name` and `event-row__desc` in a `<div>` instead of using a bare `<span>` for the name.

**Event badge types:**
- `event-badge--birthday` — Pink tint with cake icon
- `event-badge--holiday` — Purple tint with snowflake icon
- `event-badge--vacation` — Green tint with palm tree icon

**Avatar initials color variants:**
- `avatar-group__initials--blue` — Blue-50 background
- `avatar-group__initials--yellow` — Yellow background
- `avatar-group__initials--green` — Green background
- `avatar-group__initials--pink` — Pink background
- `avatar-group__initials--orange` — Orange background

## Do's and Don'ts

**Do:**
- Use consistent section header colors across all schedule cards
- Include count numbers in section header labels (e.g., "Meetings (2)")
- Use the blue left border on meeting items to visually group them
- Vary avatar selections across the range for diversity
- Always show event type badge alongside avatar/name in event rows
- Show +N count when more than 5 avatars in a group

**Don't:**
- Show more than 5 avatars in a group before using the +N count
- Use different border-radius values on the card
- Omit the calendar icon next to the date
- Use colored backgrounds for standard section headers — only `--important` gets a colored (green) background
- Mix section header color schemes
