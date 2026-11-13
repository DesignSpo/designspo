---
name: stop-hardcoding-values
title: Stop hardcoding values
category: Design Systems
summary: "Use the design system's token, like var(--brand-500), instead of typing a raw value like #0C41DF into an element, even when only one element needs it."
applies_to: [colors, sizes, spacing, buttons, component styles, CSS custom properties]
source: https://designspo.co/stop-hardcoding-values/
---

# Stop hardcoding values

A hardcoded value is a color or size typed straight into one element, like `#0C41DF` on a single button. It works at first, but hardcoded values don't update when you make a change: update the color of your buttons and any button you forget keeps the old one, so the site ends up with two slightly different versions. A token gives the same value, updates everywhere when it changes, and its name, like `brand-500`, says more than a hex code to anyone reading the styles later.

## Rule

If the design system has a token for a value, use the token, even for a single element. Never type a raw color or size that an existing token already holds.

## How to apply

1. Find the token definitions, usually CSS custom properties on `:root` in a global stylesheet or theme file.
2. Search the component styles for raw hex codes, `rgb()` and `hsl()` colors, and pixel values.
3. Replace each raw value that matches a token's value with `var(--token-name)`.
4. Treat a raw value that's close to a token but not equal, like `#0D42E0` beside `#0C41DF`, as a copy that drifted: use the token.
5. In page builders, pick the variable from the picker instead of typing or pasting the hex.

```css
:root {
  --brand-500: #0C41DF;
}

/* Before: each button has its own copy of the blue, and one has drifted */
.signup-button { background: #0C41DF; }
.buy-button { background: #2F60F4; }

/* After: one token, so both match today and both update when it changes */
.signup-button,
.buy-button { background: var(--brand-500); }
```

## Check your work

- [ ] No component style contains a raw color or size that matches a token's value.
- [ ] Changing a token's value changes every element that should follow it; nothing keeps the old value.
- [ ] Styles read as intent, like `var(--brand-500)`, rather than bare numbers.

## When to break it

- A genuine one-off with no token, like the exact width of a decorative shape, can stay a plain value.
- Third-party embeds you can't restyle.

## Before and after

- **Before:** no tokens at all. Each button has its own hex code typed in, and the copies have drifted: `#0C41DF` on Sign up and `#2F60F4` on Buy now, so the two blues don't match.
- **After:** both buttons use the `brand-500` token (`#0C41DF`), so they match.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: no tokens at all. Each button has its own hex code typed in, and the copies have drifted: `#0C41DF` on Sign up and `#2F60F4` on Buy now, so the two blues don't match.](before.png) | ![After: both buttons use the `brand-500` token (`#0C41DF`), so they match.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
