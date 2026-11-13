---
name: build-dark-mode-by-swapping-token-values
title: Build dark mode by swapping token values
category: Design Systems
summary: Style components with semantic tokens like bg-surface and text-primary, then build dark mode by changing what those tokens point to instead of restyling each component.
applies_to: [dark mode, themes, colors, cards, sections, CSS custom properties]
source: https://designspo.co/build-dark-mode-by-swapping-token-values/
---

# Build dark mode by swapping token values

Dark mode is much easier to build when components use semantic tokens: tokens named for their job, like `text-primary` or `bg-surface`, that point to an actual color. Dark mode then mostly means changing what those tokens point to: `bg-surface` might be a very light gray in light mode and a very dark gray in dark mode, while every card and section that uses it stays exactly the same. Hardcoded colors make dark mode hard to add later, since each one has to be found and changed by hand.

## Rule

Style components only with semantic color tokens. Build dark mode by giving those tokens new values for the dark theme, not by adding dark-mode styles to each component.

## How to apply

1. Define the palette once as primitive tokens, like `--neutral-50` to `--neutral-950`.
2. Define semantic tokens named for their job, like `--bg-surface`, `--text-primary` and `--border-subtle`, that point to primitives.
3. Replace every hardcoded color in component styles with a semantic token.
4. Redefine the semantic tokens for dark mode, under a `prefers-color-scheme` media query, a theme attribute, or both.
5. Leave the component styles untouched.

```css
:root {
  --neutral-50: #F8FAFC;
  --neutral-900: #0F172B;

  --bg-surface: var(--neutral-50);
  --text-primary: var(--neutral-900);
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg-surface: var(--neutral-900);
    --text-primary: var(--neutral-50);
  }
}

/* The same rule in both modes */
.card {
  background: var(--bg-surface);
  color: var(--text-primary);
}
```

## Check your work

- [ ] Component styles contain no raw colors, only semantic tokens.
- [ ] Dark mode is defined only by new values for the semantic tokens.
- [ ] Switching themes changes every card and section without editing any component rule.
- [ ] Text stays readable against its background in both modes.

## When to break it

- Images, logos and illustrations may need dark versions of their own; swapping tokens won't change them.
- A brand color, like a button's blue, can keep the same value in both modes if it still has enough contrast.

## Before and after

- **Light mode:** a blog card styled with `bg-surface` and `text-primary`, which point to `neutral-50` and `neutral-900`.
- **Dark mode:** the same card and the same tokens, now pointing to `neutral-900` and `neutral-50`, so the card turns dark without any change to its own styles.

| Light mode (`before.png`) | Dark mode (`after.png`) |
| --- | --- |
| ![Light mode: a blog card styled with `bg-surface` and `text-primary`, which point to `neutral-50` and `neutral-900`.](before.png) | ![Dark mode: the same card and the same tokens, now pointing to `neutral-900` and `neutral-50`, so the card turns dark without any change to its own styles.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Light mode** and **Dark mode**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
