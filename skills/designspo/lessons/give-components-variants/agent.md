---
name: give-components-variants
title: Use component variants
category: Design Systems
summary: Build the forms of a component, like large, outlined or icon buttons, as variants of one base class plus small modifier classes, instead of separate copies.
applies_to: [buttons, components, CSS classes, design systems]
source: https://designspo.co/give-components-variants/
---

# Use component variants

A button often needs a few forms: a large one for the hero, an outlined one for secondary actions, one with an icon. Built as separate buttons, each copy repeats the shared styles, so changing something they share, like the font or the corner radius, means updating every copy by hand. Built as variants of one component, the base holds everything they share and each variant changes only what's different.

## Rule

Give each component one base class that holds every shared style, and add a small modifier class for each variant that changes only what's different, like the size or the fill. Never copy a component to make a new form of it.

## How to apply

1. Find components that exist as near-copies: several button classes, or card classes that differ in one or two properties.
2. Move everything they share (font, weight, radius, padding, colors, transitions) into one base class, like `.btn`.
3. For each form, add a modifier class that sets only the properties that differ: `.btn--large` for size, `.btn--outline` for the fill, `.btn--icon` for the icon spacing.
4. Use both classes in the markup (`class="btn btn--outline"`) and delete the old copies.
5. In a no-code builder, do the same with a global class for the base and one small class per variant, or with the builder's own component variants.

```css
/* The base: everything the forms share */
.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5em;
  padding: 12px 20px;
  border: 2px solid #0C41DF;
  border-radius: 4px;
  background: #0C41DF;
  color: #fff;
  font: 600 14px/1 Inter, sans-serif;
}

/* Variants: only what's different */
.btn--large { padding: 16px 28px; font-size: 18px; }
.btn--outline { background: transparent; color: #0C41DF; }
.btn--icon svg { width: 1em; height: 1em; }
```

```html
<a class="btn btn--large" href="/signup">Sign up</a>
<a class="btn btn--outline" href="/tour">Take the tour</a>
```

## Check your work

- [ ] Every form of the component uses the base class plus at most a modifier or two.
- [ ] Modifier classes don't repeat the base's font, radius or other shared properties.
- [ ] Changing the font or radius in the base class changes every variant at once.
- [ ] No separate copies of the component (like `.hero-button` next to `.btn`) are left.

## When to break it

- When a variant needs to override most of the base, it's a different component: give it its own base class.

## Before and after

- **Before:** a large, an outlined and an icon button, each its own class (`.hero-btn`, `.outline-btn`, `.icon-btn`), and each one setting the font and radius again.
- **After:** a `.btn` base class sets the font and radius, and three variants, `.btn--large`, `.btn--outline` and `.btn--icon`, change only the size, the fill or the icon. The buttons look the same as before.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a large, an outlined and an icon button, each its own class (`.hero-btn`, `.outline-btn`, `.icon-btn`), and each one setting the font and radius again.](before.png) | ![After: a `.btn` base class sets the font and radius, and three variants, `.btn--large`, `.btn--outline` and `.btn--icon`, change only the size, the fill or the icon. The buttons look the same as before.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
