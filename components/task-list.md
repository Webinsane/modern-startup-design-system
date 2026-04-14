# Task List

## Overview
Kanban-style task list column with category header, task count, and stacked task cards. Each task card features a priority/category color bar, title, description, assignee avatars, status badge, and metadata row with counts and date. Used for project boards, sprint planning, and task management views.

## Structure
```html
<div class="task-list">
  <div class="task-list__header">
    <div class="task-list__header-left">
      <span class="task-list__indicator"></span>
      <h3 class="task-list__title">BACKLOG</h3>
    </div>
    <div class="task-list__header-actions">
      <button class="task-list__action" aria-label="Add task"><i data-lucide="plus"></i></button>
      <button class="task-list__action" aria-label="More options"><i data-lucide="more-horizontal"></i></button>
    </div>
  </div>
  <div class="task-list__meta">
    <span class="task-list__count">3 Tasks</span>
    <span class="task-list__updated">Updated 4 hours ago</span>
  </div>

  <div class="task-list__cards">

    <article class="task-card">
      <div class="task-card__color-bar task-card__color-bar--low"></div>
      <div class="task-card__body">
        <span class="task-card__category task-card__category--low">LOW PRIORITY</span>
        <h4 class="task-card__title">Review Pull Requests</h4>
        <p class="task-card__desc">Reviewing incoming code changes for quality and consistency. Check...</p>
        <div class="task-card__assignees-row">
          <div class="avatar-stack">
            <img class="avatar-stack__img" src="assets/avatars/avatar-a03.png" alt="Assignee">
            <img class="avatar-stack__img" src="assets/avatars/avatar-b12.png" alt="Assignee">
          </div>
          <span class="tag tag--neutral">Under Review</span>
        </div>
      </div>
      <div class="task-card__footer">
        <div class="task-card__stats">
          <span class="task-card__stat"><i data-lucide="message-square"></i> 8</span>
          <span class="task-card__stat"><i data-lucide="paperclip"></i> 4</span>
          <span class="task-card__stat"><i data-lucide="copy"></i> 8</span>
        </div>
        <span class="task-card__date">17/09/2024</span>
      </div>
    </article>

    <article class="task-card">
      <div class="task-card__color-bar task-card__color-bar--info"></div>
      <div class="task-card__body">
        <span class="task-card__category task-card__category--info">ON BOARDING</span>
        <h4 class="task-card__title">Setup Dev Environment</h4>
        <p class="task-card__desc">Configuring local development tools and access credentials. Define...</p>
        <div class="task-card__assignees-row">
          <div class="avatar-stack">
            <img class="avatar-stack__img" src="assets/avatars/avatar-a15.png" alt="Assignee">
          </div>
          <span class="tag tag--neutral">Pending</span>
        </div>
      </div>
      <div class="task-card__footer">
        <div class="task-card__stats">
          <span class="task-card__stat"><i data-lucide="message-square"></i> 3</span>
          <span class="task-card__stat"><i data-lucide="paperclip"></i> 1</span>
          <span class="task-card__stat"><i data-lucide="copy"></i> 2</span>
        </div>
        <span class="task-card__date">20/09/2024</span>
      </div>
    </article>

  </div>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Task list container | background | transparent (cards provide surface) |
| Task list container | width | 320px fixed on desktop, 100% on mobile |
| Header title | font-size | `var(--text-h3-size)` |
| Header title | font-weight | `var(--text-h3-weight)` |
| Header title | color | `var(--color-text-primary)` |
| Header title | letter-spacing | 0.05em (uppercase) |
| Header indicator | width | 4px, height 24px |
| Header indicator | background | `var(--color-secondary)` |
| Header indicator | border-radius | `var(--radius-full)` |
| Action buttons | width/height | 36px |
| Action buttons | background | `var(--color-surface-alt)` |
| Action buttons | border-radius | `var(--radius-md)` |
| Action buttons | color | `var(--color-text-secondary)` |
| Meta text | font-size | `var(--text-xs-size)` |
| Meta text | color | `var(--color-text-muted)` |
| Task card | background | `var(--color-surface)` |
| Task card | border-radius | `var(--radius-lg)` |
| Task card | border | 1px dashed `var(--color-border)` |
| Task card | box-shadow | `var(--shadow-card)` |
| Color bar | height | 6px |
| Color bar | border-radius | `var(--radius-lg) var(--radius-lg) 0 0` (top corners match card) |
| Color bar (low) | background | `var(--color-success)` — green |
| Color bar (high) | background | `var(--color-error)` — red |
| Color bar (medium) | background | `var(--color-warning)` — yellow |
| Color bar (info) | background | `var(--color-info)` — blue |
| Color bar (urgent) | background | `var(--color-accent)` — orange |
| Category label | font-size | `var(--text-xs-size)` |
| Category label | font-weight | 600 |
| Category label | letter-spacing | 0.05em |
| Category label (low) | color | `var(--color-success)` |
| Category label (high) | color | `var(--color-error)` |
| Category label (medium) | color | `var(--color-warning)` |
| Category label (info) | color | `var(--color-info)` |
| Category label (urgent) | color | `var(--color-accent)` |
| Card title | font-size | `var(--text-h3-size)` |
| Card title | font-weight | `var(--text-h3-weight)` |
| Card title | color | `var(--color-text-primary)` |
| Card description | font-size | `var(--text-small-size)` |
| Card description | color | `var(--color-text-secondary)` |
| Card description | max lines | 2 (line-clamp) |
| Avatar stack images | width/height | 32px |
| Avatar stack images | border-radius | `var(--radius-full)` |
| Avatar stack overlap | margin-left | -8px (not first) |
| Avatar stack border | border | 2px solid `var(--color-surface)` |
| Status tag | font-size | `var(--text-xs-size)` |
| Status tag | padding | `var(--space-2xs) var(--space-xs)` |
| Status tag | border-radius | `var(--radius-sm)` |
| Status tag | background | `var(--color-surface-alt)` |
| Status tag | color | `var(--color-text-secondary)` |
| Footer | border-top | 1px dashed `var(--color-border)` |
| Footer | padding-top | `var(--space-sm)` |
| Stat icons | width/height | 14px |
| Stat text | font-size | `var(--text-xs-size)` |
| Stat text | color | `var(--color-text-muted)` |
| Date text | font-size | `var(--text-xs-size)` |
| Date text | color | `var(--color-text-muted)` |
| Cards gap | gap | `var(--space-md)` |

## Layout Rules
- Task list column is 320px wide on desktop
- Cards stack vertically with `var(--space-md)` (16px) gap
- Internal card padding: `var(--space-md)` (16px) on body and footer
- Color bar spans full width at top of card with no internal padding
- Footer separates from body with dashed border
- Assignee row uses flex with space-between to push status badge right
- Multiple columns sit side-by-side in a horizontal scroll or grid for kanban boards

## States

**Default:**
Card has dashed border, subtle shadow, color bar at top.

**Hover:**
Shadow elevates to `var(--shadow-md)`, slight translate(-2px). Transition: `var(--transition-fast)`.

**Dragging:**
Shadow elevates to `var(--shadow-lg)`, opacity 0.9, slight rotation (2deg). Card appears lifted from the list.

**Active/Selected:**
Background shifts to `var(--color-surface-active)`. Border becomes solid instead of dashed.

**Empty list:**
Show centered illustration with muted text "No tasks yet" and a ghost add button.

## Responsive Behavior

**Mobile (< 640px):**
Single column, full width. Task list fills viewport width with horizontal padding `var(--space-md)`. Kanban columns stack vertically or become swipeable tabs.

**Tablet (640px - 1024px):**
Two columns visible. Remaining columns accessible via horizontal scroll.

**Desktop (> 1024px):**
Full kanban board with 3–4 columns visible. Each column 320px.

## Accessibility
- **Role:** `<article>` for each task card, column uses `role="list"` with cards as `role="listitem"`
- **Keyboard:** Cards are focusable. Arrow keys navigate between cards. Enter opens task detail. Drag and drop via keyboard with Space to grab, arrows to move, Space to drop.
- **Screen reader:** Card title is accessible name. Category and status announced. Stat counts have sr-only labels (e.g., "8 comments, 4 attachments, 8 subtasks").
- **Focus visible:** 2px outline `var(--color-secondary)` with 2px offset

## Variants

**Priority colors:**
- Low priority — green bar (`--color-success`)
- Medium priority — yellow bar (`--color-warning`)
- High priority — red bar (`--color-error`)
- Info/Onboarding — blue bar (`--color-info`)
- Urgent — orange bar (`--color-accent`)

**Compact card:**
Omits description and stat row. Shows only color bar, title, avatar stack, and status badge. For dense board views.

**With progress bar:**
Adds a thin progress bar between body and footer showing subtask completion percentage.

## Do's and Don'ts

**Do:**
- Always include the color bar — it provides immediate visual priority scanning
- Use dashed borders on cards — this is the distinctive visual treatment for task cards
- Keep descriptions to 2 lines max with ellipsis overflow
- Show assignee avatars to indicate ownership at a glance
- Use consistent category label colors matching the color bar

**Don't:**
- Mix solid and dashed border styles within the same board
- Use more than 5 priority color levels
- Stack more than 3 assignee avatars — use a "+N" overflow indicator for larger teams
- Omit the footer metadata row — dates and counts provide essential context
