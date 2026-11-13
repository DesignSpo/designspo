---
name: decide-when-a-value-deserves-a-token
title: Decide when a value deserves a token
category: Design Systems
summary: Make a value a design token only if it appears in three or more places or you'd want to change it everywhere at once, and keep one-off values in the component's own styles.
applies_to: [design tokens, CSS custom properties, colors, spacing, sizes, component styles]
source: https://designspo.co/decide-when-a-value-deserves-a-token/
---

# Decide when a value deserves a token

Tokens, the named values in a design system, are useful, but turning every number into one makes the system harder to use. A token for a 13px gap that appears in only one place is one more name to remember and one more option to scroll past. A simple test decides which values become tokens; the rest stay in the styles of the component that uses them.

## Rule

Make a value a token if it appears in three or more places, or if you'd want to change it everywhere at once. Keep a one-off value tied to a single component, like the exact width of a decorative shape, in that component's styles.

## How to apply

1. List the values in the styles: colors, spacing, sizes, radii.
2. For each one, count where it's used: search the codebase for the raw value, and for the token name if it already is one.
3. Make it a token, or keep it as one, when it's used in three or more places or is a decision you'd change site-wide, like the brand color or the standard section padding.
4. Leave values used once as plain values in the component's own rule.
5. If an existing token is used in only one place and isn't a site-wide decision, move its value into that component and delete the token.

```css
:root {
  /* Used in many places, or changed site-wide */
  --brand-500: #0C41DF;
  --text-body: 1.125rem;
  --section-padding: 96px;
}

.hero {
  padding-block: var(--section-padding);
  gap: 13px; /* used once: no token */
}

.hero p { font-size: var(--text-body); }
.hero .button { background: var(--brand-500); }

.hero__shape {
  width: 212px;  /* decorative, used once: no token */
  right: -24px;  /* decorative, used once: no token */
}
```

## Check your work

- [ ] Every token is used in at least three places, or is a site-wide decision like the brand color.
- [ ] No token exists only for a value used in a single component, like `--gap-13` or `--shape-width`.
- [ ] Values that repeat, like the brand color and section padding, are tokens rather than raw values typed in several places.
- [ ] One-off values sit in the component's own rule, next to where they're used.

## When to break it

- Two values that happen to share a number but mean different things, like a 16px card padding and a 16px icon size, don't belong in one token just because they add up to three uses.
- A one-off value you know other components will need soon, like a new spacing step, can start as a token.

## Before and after

- **Before:** a hero section with every value labelled as a token: `section-padding`, `text-body` and `brand-500`, and also `shape-size` and `shape-offset` for a decorative circle that is the only place they're used.
- **After:** `section-padding`, `text-body` and `brand-500` stay tokens, and the circle keeps its size (`212px`) and offset (`-24px`) as plain custom values in the hero's own styles.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a hero section with every value labelled as a token: `section-padding`, `text-body` and `brand-500`, and also `shape-size` and `shape-offset` for a decorative circle that is the only place they're used.](before.png) | ![After: `section-padding`, `text-body` and `brand-500` stay tokens, and the circle keeps its size (`212px`) and offset (`-24px`) as plain custom values in the hero's own styles.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
