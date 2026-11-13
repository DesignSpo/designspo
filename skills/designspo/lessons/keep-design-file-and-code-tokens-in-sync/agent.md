---
name: keep-design-file-and-code-tokens-in-sync
title: Keep design file and code tokens in sync
category: Design Systems
summary: Use the same token names in the design tool (like Figma variables) and in the CSS, change both in the same sitting, and compare the two lists before each new project.
applies_to: [design tokens, Figma variables, CSS custom properties, design handoff]
source: https://designspo.co/keep-design-file-and-code-tokens-in-sync/
---

# Keep design file and code tokens in sync

Many designers keep tokens in two places: as variables in a design tool like Figma, and as CSS variables on the live site. If the two drift apart, designs stop matching what actually gets built: a color renamed in Figma but not in the CSS leads to guesswork and small mismatches. Using the same names in both places, changing them together and comparing the two lists now and then keeps them matched.

## Rule

Give every token the same name in the design file and in the code (the CSS adds only the `--` prefix), and when you add, rename or change a token, change it in both places in the same sitting.

## How to apply

1. Get both lists: the design tool's variables (from its variables panel or an export) and the CSS custom properties (usually on `:root` in a global stylesheet).
2. Compare them side by side, name by name and value by value.
3. Fix every difference: rename one side to match the other, align the values, and add any token that exists on only one side.
4. Whenever a token changes later, update the design file and the code in the same sitting.
5. Repeat the side-by-side check before each new project. It takes a few minutes and saves rework.

```css
/* Figma variables: brand-500, brand-hover, text-primary, bg-surface */
:root {
  --brand-500: #0C41DF;
  --brand-hover: #072788;
  --text-primary: #0F172B;
  --bg-surface: #F1F5F9;
}
```

## Check your work

- [ ] Every design-tool variable has a CSS custom property with the same name plus `--`, and every CSS token has a design-tool variable.
- [ ] Matching tokens have the same values in both places.
- [ ] No style refers to a token name that the design file doesn't use.

## When to break it

- Tokens that only make sense in code, like z-index layers, can live in the CSS alone; list them in the system's docs so nobody looks for them in the design file.

## Before and after

- **Before:** the two lists have drifted far apart. In Figma, `brand-500` and `brand-hover` are blue, but the CSS still holds an old orange for `--brand-500` and `--brand-hover`, and Figma's `bg-surface` is still `--surface` in the CSS. Only `text-primary` matches.
- **After:** the CSS was updated in the same sitting: both brand colors are the same blue as in Figma, `--surface` is now `--bg-surface`, and all four names and values match.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: the two lists have drifted far apart. In Figma, `brand-500` and `brand-hover` are blue, but the CSS still holds an old orange for `--brand-500` and `--brand-hover`, and Figma's `bg-surface` is still `--surface` in the CSS. Only `text-primary` matches.](before.png) | ![After: the CSS was updated in the same sitting: both brand colors are the same blue as in Figma, `--surface` is now `--bg-surface`, and all four names and values match.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
