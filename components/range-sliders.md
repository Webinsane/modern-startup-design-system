# Range Sliders

## Overview
Range sliders with optional tick marks, PX input pairing, and accent fill with tooltip. Three variants: default (grey thumb), active (dark thumb), and accent (colored fill with value tooltip).

## Structure
```html
<div class="range-slider">
  <div class="range-slider__track-wrapper">
    <div class="range-slider__track">
      <div class="range-slider__track-fill" style="width: 50%"></div>
    </div>
    <input type="range" class="range-slider__input" min="0" max="100" value="50" />
  </div>
</div>
```

### With PX Input
```html
<div class="range-slider-row">
  <div class="range-slider">
    <div class="range-slider__track-wrapper">
      <div class="range-slider__track">
        <div class="range-slider__track-fill" style="width: 50%"></div>
      </div>
      <input type="range" class="range-slider__input" min="0" max="100" value="50" />
    </div>
  </div>
  <div class="px-input">
    <input type="text" class="px-input__field" value="50" />
    <span class="px-input__unit">px</span>
  </div>
</div>
```

### With Tick Marks
```html
<div class="range-slider">
  <div class="range-slider__track-wrapper">
    <div class="range-slider__track">
      <div class="range-slider__track-fill" style="width: 50%"></div>
    </div>
    <input type="range" class="range-slider__input" min="0" max="100" value="50" />
  </div>
  <div class="range-slider__ticks">
    <span>0</span><span>25</span><span>50</span><span>75</span><span>100</span>
  </div>
</div>
```

### Dark Variant
```html
<div class="range-slider range-slider--dark">...</div>
```

## Tokens Used

| Element | Property | Token |
|---------|----------|-------|
| Track | background | `var(--color-border-light)` |
| Track | height | `4px` |
| Track | border-radius | `9999px` |
| Fill | background | `var(--color-primary)` |
| Thumb | size | `16px` |
| Thumb | background | `var(--color-white)` |
| Thumb | border | `2px solid var(--color-border)` |
| Thumb | border-radius | `50%` |
| Dark thumb | background | `var(--color-black)` |
| PX input | border | `1px solid var(--color-border)` |
| PX input | border-radius | `var(--radius-md)` |

## Layout Rules
- `.range-slider` is full width within its container
- `.range-slider-row` pairs slider and PX input in a flex row
- Track fill width is set inline via `style="width: X%"` and synced with JS
- Tick marks are evenly distributed with `justify-content: space-between`

## Accessibility
- Built on native `<input type="range">` for keyboard support (arrow keys)
- Add `aria-label` or visible `<label>` for screen readers
- PX input should sync bidirectionally with the slider value

## Do's and Don'ts

**Do:**
- Sync the fill width with the thumb position via JavaScript
- Use tick marks for sliders with meaningful intervals
- Pair with a PX input when exact values matter

**Don't:**
- Use for selecting from discrete categories — use radio buttons or a select
- Omit min/max labels when the range isn't obvious
- Use the dark variant on dark backgrounds
