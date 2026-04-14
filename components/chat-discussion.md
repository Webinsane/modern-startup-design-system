# Chat & Discussion Board

## Overview
Threaded conversation UI for community discussion boards. Features a main post with nested comment replies, user avatars, action buttons, and a comment input field.

## Structure
```html
<article class="discussion">
  <header class="discussion__header">
    <span class="discussion__breadcrumb">Modern Startup — Discussion Board</span>
  </header>

  <div class="discussion__post">
    <img src="assets/avatars/avatar-a15.png" class="discussion__avatar discussion__avatar--lg" alt="Philip Smith">
    <div class="discussion__content">
      <h1 class="discussion__title">Check out our new office!</h1>
      <span class="discussion__meta">1 month ago by <a href="#">Philip Smith</a></span>
      <p class="discussion__body">I'm new to Kalkio! Hello everyone...</p>
      <div class="discussion__tags">
        <a href="#" class="tag tag--category">Interior Design</a>
        <a href="#" class="tag tag--category">Office</a>
        <a href="#" class="tag tag--category">2021 to rule</a>
      </div>
      <div class="discussion__actions">
        <button class="discussion__action"><i data-lucide="thumbs-up"></i> 3 likes</button>
        <button class="discussion__action"><i data-lucide="message-circle"></i> 7 replies</button>
        <button class="btn btn--outlined btn--sm">Comment</button>
        <button class="btn btn--outlined btn--sm">Follow</button>
      </div>
    </div>
  </div>

  <div class="discussion__replies">
    <div class="discussion__reply">
      <img src="assets/avatars/avatar-b12.png" class="discussion__avatar" alt="Vicente Reyes">
      <div class="discussion__reply-content">
        <span class="discussion__reply-meta">Vicente Reyes · 3 months ago</span>
        <p class="discussion__reply-body">It's looking top notch. Can't wait to check it live in person.</p>
      </div>
      <div class="discussion__reply-actions">
        <button><i data-lucide="thumbs-up"></i></button>
        <button><i data-lucide="message-circle"></i></button>
        <button><i data-lucide="link"></i></button>
      </div>
    </div>
  </div>

  <div class="discussion__comment-input">
    <input type="text" class="form-field__input" placeholder="Write a comment...">
    <button class="btn btn--primary btn--md">Comment</button>
  </div>
</article>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Container | background | `var(--color-surface)` |
| Container | border-radius | `var(--radius-lg)` |
| Container | padding | `var(--space-xl)` — 24px |
| Breadcrumb | font-size | `var(--text-small-size)` |
| Breadcrumb | color | `var(--color-primary)` |
| Post title | font-size | `var(--text-h2-size)` — 20px |
| Post title | font-weight | `var(--text-h2-weight)` — 700 |
| Post avatar (large) | size | 48px |
| Post avatar (large) | border-radius | `var(--radius-full)` |
| Reply avatar | size | 32px |
| Reply avatar | border-radius | `var(--radius-full)` |
| Meta text (author, time) | font-size | `var(--text-xs-size)` |
| Meta text | color | `var(--color-text-muted)` |
| Body text | font-size | `var(--text-body-size)` |
| Body text | color | `var(--color-text-primary)` |
| Body text | line-height | `var(--text-body-lh)` — 1.5 |
| Post to replies gap | spacing | `var(--space-lg)` — 20px |
| Between replies | spacing | `var(--space-sm)` — 12px |
| Title to meta gap | spacing | `var(--space-xs)` — 8px |
| Meta to body gap | spacing | `var(--space-sm)` — 12px |
| Body to tags gap | spacing | `var(--space-lg)` — 20px |
| Tags to actions gap | spacing | `var(--space-xl)` — 24px |
| Comment input section | margin-top | `var(--space-lg)` — 20px |
| Comment input section | padding-top | `var(--space-lg)` — 20px |
| Comment input section | border-top | `var(--border-width) var(--border-style) var(--color-border-light)` |
| Comment input field | height | 40px |
| Comment button | height | 40px (matches input height) |
| Actions row | align-items | `center` |
| Page bottom padding | padding-bottom | `var(--space-xl)` — 24px |
| Reply action icons | gap | `var(--space-xs)` — 8px |
| Action icon button | color | `var(--color-text-muted)` |
| Link text | color | `var(--color-text-link)` |
| Mention (@name) | color | `var(--color-text-link)` |

## Layout Rules
- Spacing values:
  - 24px top/bottom padding on main container
  - 17px between breadcrumb and avatar (use 16px / `var(--space-md)`)
  - 20px between post body and tags
  - 24px between tags/actions and replies section
  - 16px between replies
  - 12px between individual reply items
  - 20px above comment input (`var(--space-lg)`), with a top border separator
  - 24px bottom padding
- Avatar + content in horizontal flex with `var(--space-sm)` gap
- Reply actions (like, reply, copy link) aligned to the right
- `.discussion__actions` uses `align-items: center` to vertically center action buttons and text
- **Comment input height alignment:** Both `.form-field__input` and `.btn` inside `.discussion__comment-input` are set to 40px height. The button uses `display: inline-flex; align-items: center` to vertically center its label. Use `.btn--md` on the comment button to match the 40px input height.
- Tags in the discussion use `.tag--category` modifier for proper transparent-background styling

## States

**Default:**
Clean white background with subtle borders between reply groups.

**Hover on reply actions:**
Icon color shifts to `var(--color-primary)`. "Copy Link" and "Unlike" show as tooltips with primary background.

**Active action:**
"Unlike" button shows as filled primary pill. "Copy Link" shows as tooltip/popover.

**Comment input focus:**
Border changes to `var(--color-border-focus)`.

## Responsive Behavior

**Mobile (< 640px):**
Full-width. Reply actions stack below content. Avatars reduce to 28px.

**Desktop (> 1024px):**
Max-width container centered. Full avatar sizes.

## Accessibility
- **Role:** `<article>` for main post and each reply
- **Keyboard:** `Tab` through action buttons and comment input
- **Screen reader:** Post title announced as heading; replies use `aria-label` with author name
- **Focus visible:** 2px outline `var(--color-primary)`
- **Comment input:** `aria-label="Write a comment"`

## Do's and Don'ts

**Do:**
- Show relative timestamps ("3 months ago")
- Make @mentions clickable links
- Show action counts (3 likes, 7 replies)

**Don't:**
- Nest replies more than 1 level deep visually
- Auto-expand all replies — paginate after ~10
- Use different avatar sizes within the same reply thread
