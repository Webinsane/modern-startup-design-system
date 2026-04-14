---
name: modern-startup-app
description: >
  Design system for building modern startup dashboards and booking platforms.
  Clean, professional, whitespace-forward visual style with dark mode support.
  Read this file first before writing any frontend code.
---

# Modern Startup App — Design System

## Design Philosophy

Clean, functional interfaces with generous whitespace. 14px body text, Plus Jakarta Sans,
weight and size contrast create hierarchy. Purple-indigo marks interactive states. Cards
are the primary container — white on cool gray background. Status uses colored left
borders (3px indigo = pending, green = confirmed) and semantic pill badges. Dense enough
for power users, breathable enough to feel modern.

## Before You Write Any Code

1. Read `tokens/tokens.css` — these are your ONLY allowed values
2. Read the relevant component spec in `components/` for what you're building
3. Check `examples/*.html` for working implementation patterns
4. NEVER hardcode colors, spacing, font sizes, or shadows — always use CSS variables

## Design Tokens

```html
<link rel="stylesheet" href="tokens/tokens.css">
```

### Color System

| Token | Value | Usage |
|-------|-------|-------|
| `--color-bg` | `#F5F6FA` | Page background |
| `--color-surface` | `#FFFFFF` | Card/container backgrounds |
| `--color-surface-raised` | `#FFFFFF` | Elevated elements, modals |
| `--color-surface-active` | `#F0EAFF` | Active/selected highlight |
| `--color-border` | `#E5E7EB` | Borders, dividers |
| `--color-border-focus` | `#6366F1` | Focused input borders |
| `--color-border-accent` | `#6366F1` | Left accent — pending |
| `--color-border-success` | `#22C55E` | Left accent — confirmed |
| `--color-text-primary` | `#1F2937` | Headings, primary content |
| `--color-text-secondary` | `#6B7280` | Body text, descriptions |
| `--color-text-muted` | `#9CA3AF` | Captions, metadata |
| `--color-text-inverse` | `#FFFFFF` | Text on dark backgrounds |
| `--color-text-link` | `#6366F1` | Links, interactive text |
| `--color-primary` | `#6366F1` | Primary actions — indigo |
| `--color-primary-hover` | `#4F46E5` | Primary hover state |
| `--color-primary-light` | `#EEF2FF` | Primary tinted backgrounds |
| `--color-accent` | `#F97316` | Highlights — orange |
| `--color-success` | `#22C55E` | Confirmed, success |
| `--color-success-light` | `#F0FDF4` | Success backgrounds |
| `--color-warning` | `#EAB308` | Pending, warning |
| `--color-warning-light` | `#FEFCE8` | Warning backgrounds |
| `--color-error` | `#EF4444` | Error, destructive |
| `--color-error-light` | `#FEF2F2` | Error backgrounds |
| `--color-nav-active` | `#0D9488` | Sidebar active — teal |
| `--color-nav-active-bg` | `#E6F7F5` | Sidebar active background |
| `--color-nav-hover-bg` | `#F0FDFA` | Sidebar hover background |

### Typography

**Fonts:** `'Plus Jakarta Sans'` for display + body, `'JetBrains Mono'` for code.

| Token | Size | Weight | Usage |
|-------|------|--------|-------|
| `--text-hero` | 32px | 700 | Page titles |
| `--text-h1` | 24px | 700 | Section titles |
| `--text-h2` | 20px | 700 | Post titles |
| `--text-h3` | 16px | 600 | Card titles |
| `--text-h4` | 14px | 600 | Subsection labels |
| `--text-body` | 14px | 400 | Body text |
| `--text-small` | 13px | 400 | Secondary info |
| `--text-xs` | 12px | 500 | Tags, badges, timestamps |

### Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `--space-2xs` | 4px | Icon padding |
| `--space-xs` | 8px | Tag padding, icon-to-text |
| `--space-sm` | 12px | Between list items |
| `--space-md` | 16px | Card padding, table rows |
| `--space-lg` | 20px | Card gaps, section internal |
| `--space-xl` | 24px | Section spacing, column gaps |
| `--space-2xl` | 32px | Major section breaks |
| `--space-3xl` | 40px | Page-level spacing |

### Border & Shape

| Token | Value |
|-------|-------|
| `--radius-sm` | 4px — inputs |
| `--radius-md` | 8px — cards, buttons |
| `--radius-lg` | 12px — modals |
| `--radius-xl` | 16px — panels |
| `--radius-full` | 9999px — pills, avatars, ALL buttons |
| `--border-width-thick` | 3px — status left borders |

### Shadows

| Token | Usage |
|-------|-------|
| `--shadow-xs` | Table rows |
| `--shadow-sm` | Buttons |
| `--shadow-md` | Cards |
| `--shadow-lg` | Dropdowns |
| `--shadow-xl` | Modals |

### Motion

| Token | Value |
|-------|-------|
| `--transition-fast` | 120ms |
| `--transition-base` | 200ms |
| `--transition-slow` | 350ms |

## Components (29 total)

Read the spec in `components/` before using any component. All component CSS lives in `components.css` — link to it alongside `tokens/tokens.css`.

### Navigation & Layout

| Component | File | What it does |
|-----------|------|-------------|
| Sidebar Nav | `sidebar-nav.md` | App sidebar: collapsed (icon-only) and expanded, teal active states |
| Top Nav | `top-nav.md` | Top bar: search, notifications dropdown, profile menu |
| Top Nav Tabs | `top-nav-tabs.md` | Content tabs below top nav (Today / This Week / Calendar) |
| Navigation | `navigation.md` | In-page nav: view toggles, tab groups, pill filters |
| Page Layout | `page-layout.md` | Dashboard grid vs detail page (main + sidebar) |
| Page Header | `page-header.md` | Breadcrumbs, page title, action buttons |

### Data & Content

| Component | File | What it does |
|-----------|------|-------------|
| Cards | `cards.md` | Room/event/discussion cards, dashboard widgets |
| Tables | `tables.md` | Bookings/visitors table with row highlighting |
| Schedule Cards | `schedule-cards.md` | Day-view schedule: meetings, events, absences |
| Stat Cards | `stat-cards.md` | Dashboard metric cards with charts and trend badges |
| Content Sections | `content-sections.md` | Body text, section headings, two-column checklists |
| Chat Discussion | `chat-discussion.md` | Discussion board with threaded replies |
| Task List | `task-list.md` | Kanban column with priority bars and assignees |
| Pagination | `pagination.md` | Page nav: Previous/Next, numbered, ellipsis |
| Empty States | `empty-states.md` | Empty content placeholder with CTA |

### Forms & Inputs

| Component | File | What it does |
|-----------|------|-------------|
| Buttons | `buttons.md` | Pill buttons: Large/Medium/Small/Tiny, filled + outlined |
| Toggles | `toggles.md` | On/off toggle switches in three sizes with labels |
| Range Sliders | `range-sliders.md` | Slider inputs with value display, ticks, and tooltips |
| Tags & Badges | `tags-badges.md` | Status badges, category tags, removable filters |
| Forms | `forms.md` | Text inputs, date pickers, checkboxes, radios, dropdowns |
| Search Filter Bar | `search-filter-bar.md` | Search, date pickers, view toggles, active filters |

### Widgets & Patterns

| Component | File | What it does |
|-----------|------|-------------|
| Avatars | `avatars.md` | Circular avatars, stacked groups. **72 photos** in `assets/avatars/` (a01–a36, b01–b36) |
| Attendees | `attendees.md` | Sidebar widget: attendee count + profile list |
| Booking Sidebar | `booking-sidebar.md` | Booking form: services, discount, total |
| Discount Widget | `discount-widget.md` | Discount code input, total price, CTAs |
| Alerts | `alerts.md` | Inline notification banners: success, error, warning, info |
| Toasts | `toasts.md` | Floating notification toasts with actions and variants |
| Modals | `modals.md` | Modal dialogs with backdrop, header, body, footer |
| Tooltip | `tooltip.md` | Hover tooltips with arrow positioning |

## Layout Rules

- **Max content width:** `--max-width: 1200px`
- **Sidebar:** 240px expanded, 64px collapsed
- **Top nav:** 56px height
- **Grid:** CSS Grid, `--grid-gap: 20px`
- **Content wrapper:** `.content-wrapper` with `max-width: var(--max-width)`, left-aligned. Top nav and tabs stay full-width.
- **Breakpoints:** Mobile < 640px (1 col) | Tablet 640–1024px (2 col) | Desktop > 1024px (full + sidebar)
- **Z-index:** Nav (100) > Dropdowns (200) > Modals (300) > Toasts (400) > Tooltips (500)
- **Page background:** Always `var(--color-bg)` — cards sit on this

## Strict Rules

1. **Use tokens only.** Never hardcode colors or spacing — always `var(--token)`.
2. **Semantic HTML.** Use `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`.
3. **Mobile-first.** Base styles for mobile, `@media (min-width: ...)` for larger.
4. **Accessible.** Keyboard-navigable, WCAG AA contrast, alt text, form labels.
5. **No framework classes.** No Tailwind, Bootstrap. Tokens + custom CSS only.
6. **Match the component specs.** `components/*.md` and `examples/*.html` are the source of truth.
7. **All buttons are pills.** `border-radius: var(--radius-full)`.
8. **Status cards need left borders.** 3px left border (indigo = pending, green = confirmed).
9. **Navigation uses teal, not indigo.** Sidebar/top-nav active = `var(--color-nav-active)`. In-page nav = `var(--color-primary)`.

## Before You Write Any Code

```html
<link rel="stylesheet" href="tokens/tokens.css">
<link rel="stylesheet" href="components.css">
```

Always link both files. `tokens.css` provides design tokens, `components.css` provides all component styles. Only add inline CSS for page-specific layout.

## Reference

- Tokens: `tokens/tokens.css`
- Component CSS: `components.css`
- Component specs: `components/*.md`
- Working examples: `examples/*.html`
