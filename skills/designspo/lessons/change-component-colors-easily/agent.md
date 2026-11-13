---
name: change-component-colors-easily
title: Change component colors easily
category: Design Systems
summary: Add component color tokens like button-color, card-border and badge-color on top of primitive and semantic tokens, so one component's color changes by re-pointing one token instead of using a raw color.
applies_to: [buttons, cards, badges, color tokens, design systems, theming]
source: https://designspo.co/change-component-colors-easily/
---

# Change component colors easily

Design systems often get abandoned because they stop working: you can't change the color of one component without affecting other things that share its variable, so you use a raw color instead. Then every instance has to be changed by hand, and updating the brand means tracking down everything else that uses that color too. An extra layer of component colors, for a select few components used again and again, fixes this.

## Rule

Build color tokens in three layers: primitive tokens hold raw colors (`brand-500: #0C41DF`), semantic tokens describe how a color is used and point to primitives (`bg-brand: brand-500`), and component tokens point a frequently used component at a semantic token (`button-color: bg-brand`). Change a component's color by re-pointing its component token, never with a raw color.

## How to apply

1. Define primitive tokens for the raw colors, like `--brand-500: #0C41DF` and `--neutral-950: #020618`.
2. Define semantic tokens that describe usage and point to primitives: `--bg-brand` for brand-colored backgrounds, `--bg-inverse` for dark ones.
3. For a few components you use all the time, like buttons, cards and badges, add component tokens that point to semantic tokens: `--button-color`, `--card-border`, `--badge-color`.
4. Style those components with their component tokens only.
5. To change one component's color, point its component token at a different semantic token. To change the brand, point the semantic token at a new primitive.

```css
:root {
  /* Primitives */
  --brand-500: #0C41DF;
  --neutral-950: #020618;

  /* Semantic */
  --bg-brand: var(--brand-500);
  --bg-inverse: var(--neutral-950);

  /* Components */
  --button-color: var(--bg-inverse); /* was var(--bg-brand) */
  --card-border: var(--bg-brand);
  --badge-color: var(--bg-brand);
}

.button { background: var(--button-color); }
.card { border: 1px solid var(--card-border); }
.badge { background: var(--badge-color); }
```

## Check your work

- [ ] Buttons, cards and badges take their colors only from their component tokens.
- [ ] Component tokens point to semantic tokens, and semantic tokens point to primitives; no component token holds a raw color.
- [ ] Changing `--button-color` changes only buttons; changing `--bg-brand` changes everything brand-colored.
- [ ] No component instance overrides its color with a raw value.

## When to break it

- Keep component tokens for the select few components used again and again; everything else can use semantic tokens directly.

## Before and after

- **Before:** `button-color`, `card-border` and `badge-color` all point to `bg-brand`, which points to `brand-500`, so the Book a call button, the Pro plan card's border and the New badge are all blue.
- **After:** `button-color` points to `bg-inverse` (`neutral-950`) instead. Only the button turns near-black; the card and the badge stay blue.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: `button-color`, `card-border` and `badge-color` all point to `bg-brand`, which points to `brand-500`, so the Book a call button, the Pro plan card's border and the New badge are all blue.](before.png) | ![After: `button-color` points to `bg-inverse` (`neutral-950`) instead. Only the button turns near-black; the card and the badge stay blue.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
