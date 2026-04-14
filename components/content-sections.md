# Content Sections

## Overview
Text-based content blocks used within detail pages. Includes body text paragraphs, section headings, and checklist/feature grids. Used for event descriptions, article content, and "What You'll Learn" sections.

## Structure
```html
<!-- Body text section -->
<section class="content-section">
  <h2 class="content-section__title">What's on?</h2>
  <div class="content-section__body">
    <p>Design is the face of a brand. It showcases its personality and highlights
    the values the brand stands for — sometimes with just a few digital brushstrokes...</p>
  </div>
</section>

<!-- Checklist section -->
<section class="content-section">
  <h2 class="content-section__title">What You'll Learn</h2>
  <ul class="checklist">
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>Illustrator Features</span>
    </li>
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>Inspiration gathering</span>
    </li>
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>File Handoff</span>
    </li>
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>Design tips and tricks</span>
    </li>
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>Client relations</span>
    </li>
    <li class="checklist__item">
      <i data-lucide="check" class="checklist__icon"></i>
      <span>Sketching</span>
    </li>
  </ul>
</section>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| **Section** | | |
| Section spacing | margin-top | `var(--section-gap)` — 32px |
| Section title | font-size | `var(--text-h3-size)` — 16px |
| Section title | font-weight | `var(--text-h3-weight)` — 600 |
| Section title | color | `var(--color-text-primary)` |
| Title to content gap | margin-bottom | `var(--section-title-gap)` — 16px |
| **Body text** | | |
| Paragraph | font-size | `var(--text-body-size)` — 14px |
| Paragraph | line-height | `var(--text-body-lh)` — 1.5 |
| Paragraph | color | `var(--color-text-secondary)` |
| Paragraph max-width | max-width | `var(--detail-content-max)` — 720px |
| Between paragraphs | margin-bottom | `var(--space-md)` — 16px |
| **Checklist** | | |
| Checklist container | display | `grid` |
| Checklist grid | grid-template-columns | `repeat(2, 1fr)` |
| Checklist gap | gap | `var(--space-sm) var(--space-xl)` — 12px 24px |
| Checklist item | display | `flex`, `align-items: center` |
| Checklist item | gap | `var(--space-xs)` — 8px |
| Check icon | size | 16px |
| Check icon | color | `var(--color-text-muted)` |
| Checklist text | font-size | `var(--text-body-size)` — 14px |
| Checklist text | color | `var(--color-text-secondary)` |

## States

**Default:**
Clean text sections with clear heading hierarchy.

**Links in body text:**
Use `var(--color-text-link)` with underline on hover.

## Responsive Behavior

**Mobile (< 640px):**
Checklist becomes single column. Body text full-width.

**Desktop (> 1024px):**
Checklist in two columns. Body text constrained to `var(--detail-content-max)`.

## Accessibility
- **Headings:** Use semantic `<h2>` or `<h3>` depending on page context
- **Checklist:** Use `<ul>` for the list, checkmarks are decorative (`aria-hidden="true"`)
- **Body text:** Proper paragraph `<p>` tags, sufficient line-height for readability

## Do's and Don'ts

**Do:**
- Keep section titles short and descriptive
- Constrain body text width for readability (60-80 characters per line)
- Use the two-column checklist for feature lists, learning outcomes
- Maintain consistent section spacing (32px between sections)

**Don't:**
- Use more than 2 columns for checklists (3+ gets too cramped)
- Center-align body text — always left-aligned
- Skip section headings — every content block needs one
- Use bullet points for the checklist — always use check icons
