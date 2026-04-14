# Avatars

## Overview
Circular user profile images used in conversation lists, discussion threads, people counters, and visitor lists. Supports individual and stacked/grouped display. Includes a built-in library of 72 diverse photo avatars for immediate use.

## Avatar Image Library

72 ready-to-use profile photos located in `assets/avatars/`:

| Set | IDs | Count |
|-----|-----|-------|
| Set A | `avatar-a01` to `avatar-a36` | 36 |
| Set B | `avatar-b01` to `avatar-b36` | 36 |

**Usage:** Reference by filename — e.g., `assets/avatars/avatar-a01.png`

When Claude Code or an AI agent needs to populate a UI with realistic user avatars, pick from these IDs. Vary selections across the range for diversity.

## Structure
```html
<!-- Single avatar with photo -->
<div class="avatar avatar--md">
  <img src="assets/avatars/avatar-a01.png" alt="User Name">
</div>

<!-- Single avatar with initials fallback -->
<div class="avatar avatar--md avatar--a">JD</div>

<!-- Avatar group (stacked) -->
<div class="avatar-group">
  <div class="avatar avatar--sm"><img src="assets/avatars/avatar-a01.png" alt="User 1"></div>
  <div class="avatar avatar--sm"><img src="assets/avatars/avatar-a02.png" alt="User 2"></div>
  <div class="avatar avatar--sm"><img src="assets/avatars/avatar-a03.png" alt="User 3"></div>
  <span class="avatar-group__count">+28</span>
</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Avatar | border-radius | `var(--radius-full)` |
| Avatar | border | `2px solid var(--color-surface)` |
| Avatar | object-fit | `cover` |
| Size XS | width/height | 24px |
| Size SM | width/height | 32px |
| Size MD | width/height | 40px |
| Size LG | width/height | 48px |
| Size XL | width/height | 64px |
| Size XXL | width/height | 96px |
| Avatar group overlap | margin-left | `-8px` (after first) |
| Avatar group | container | flex, `align-items: center` |
| Group count | font-size | `var(--text-body-size)` |
| Group count | font-weight | `600` |
| Group count | color | `var(--color-text-primary)` |
| Group count | margin-left | `var(--space-xs)` |

## Size Classes

| Class | Size | Use case |
|-------|------|----------|
| `avatar--xs` | 24px | Inline mentions, compact lists |
| `avatar--sm` | 32px | Avatar groups, table rows, chat replies |
| `avatar--md` | 40px | Default — attendee lists, cards |
| `avatar--lg` | 48px | Prominent display, discussion headers |
| `avatar--xl` | 64px | Profile cards, detail views |
| `avatar--xxl` | 96px | Profile pages, hero sections |

## Layout Rules
- Always circular via `border-radius: var(--radius-full)`
- In groups, overlap by -8px with white border ring (2px) for visual separation
- Count number sits to the right of the stack with `var(--space-xs)` gap
- In table rows and lists, vertically centered with adjacent text

## States

**Default:**
Circular image with white border ring.

**Fallback:**
When no image available, show initials on gradient background. Use color variant classes `avatar--a` through `avatar--f`.

## Accessibility
- **Alt text:** Always include user's name in `alt` attribute
- **Group:** Use `aria-label="28 people in this room"` on the group container
- **Decorative:** If avatar is next to the user's name text, use `alt=""` to avoid redundancy

## Do's and Don'ts

**Do:**
- Use consistent sizes within the same context
- Include the white border ring in grouped avatars
- Provide fallback initials for missing images
- Pick varied avatar IDs (spread across a01–a36, b01–b36) for diverse representation

**Don't:**
- Use square avatars — always circular
- Show more than 5-6 avatars in a stack before showing count
- Use different overlap amounts in different contexts
- Reuse the same avatar ID for different users in the same view
