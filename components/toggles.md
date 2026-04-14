# Toggles

## Overview
Toggle switches with pill-shaped track and circular knob. Green track when on, grey when off. Three sizes (small, default, large) with labeled and disabled variants.

## Structure
```html
<label class="toggle">
  <input type="checkbox" class="toggle__input" />
  <span class="toggle__track">
    <span class="toggle__knob"></span>
  </span>
</label>
```

### With Label
```html
<div class="toggle-field">
  <label class="toggle">
    <input type="checkbox" class="toggle__input" checked />
    <span class="toggle__track">
      <span class="toggle__knob"></span>
    </span>
  </label>
  <span class="toggle-field__label">Enable notifications</span>
</div>
```

### Size Variants
```html
<!-- Small -->
<label class="toggle toggle--sm">...</label>

<!-- Default -->
<label class="toggle">...</label>

<!-- Large -->
<label class="toggle toggle--lg">...</label>
```

### Disabled
```html
<label class="toggle toggle--disabled">
  <input type="checkbox" class="toggle__input" disabled />
  <span class="toggle__track">
    <span class="toggle__knob"></span>
  </span>
</label>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Track (off) | background | `var(--color-border)` |
| Track (on) | background | `var(--color-success)` |
| Knob | background | `var(--color-white)` |
| Knob | box-shadow | `var(--shadow-sm)` |
| Track | border-radius | `9999px` |
| Knob | border-radius | `50%` |
| Transition | duration | `var(--transition-fast)` |
| Disabled | opacity | `0.5` |

## States
- **Off:** Grey track, knob positioned left
- **On:** Green track, knob slides right via `translateX`
- **Disabled:** 50% opacity, `cursor: not-allowed`

## Accessibility
- Built on native `<input type="checkbox">` for keyboard and screen reader support
- The `<input>` is visually hidden but remains in the DOM
- Use `<label>` wrapping or `for` attribute to associate label text
- Disabled state uses the native `disabled` attribute

## Do's and Don'ts

**Do:**
- Use for binary on/off settings
- Pair with a label that describes the setting
- Use default size for most contexts

**Don't:**
- Use toggles for multi-option selections — use checkboxes or radio buttons
- Use without a label — the toggle alone doesn't communicate its purpose
- Animate color on disabled toggles
