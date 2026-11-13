---
name: choose-numbered-or-t-shirt-size-names
title: Working with numbered and t-shirt size names
category: Design Systems
summary: Choose between t-shirt size names (sm, md, lg) and numbered names (space-4, space-8) for size tokens on purpose, knowing that t-shirt names read more easily but numbered names are easier to extend.
applies_to: [design tokens, spacing scales, radius scales, type scales, naming]
source: https://designspo.co/choose-numbered-or-t-shirt-size-names/
---

# Working with numbered and t-shirt size names

Every size token needs a name, and there are two common approaches. T-shirt names like `sm`, `md` and `lg` are easy to remember and read almost like plain English, but they're hard to extend: a size between `md` and `lg` has no obvious name, so the scale has to be renamed. Numbered names like `space-4` and `space-8` usually match the value in pixels and extend easily (`space-12` slots in between `space-8` and `space-16`), but they say less about how a value is meant to be used. Either works; pick one knowing the trade-off, and stick to it.

## Rule

Choose one naming approach per size scale before building on it. Use t-shirt names for short scales that are unlikely to grow, and numbered names for scales that will need sizes in between. Don't mix the two within one scale.

## How to apply

1. List the size scales that need names: spacing, radius, type sizes, shadows.
2. For each scale, ask whether you're likely to add sizes between the existing ones later. Spacing scales usually grow; a radius scale of three values usually doesn't.
3. T-shirt names: use an ordered series (`xs`, `sm`, `md`, `lg`, `xl`, `2xl`).
4. Numbered names: name each token after its value in pixels, even when the value is in rem (`--space-16: 1rem`).
5. Define the tokens in one place, usually CSS custom properties on `:root`, and note the naming approach next to them.

```css
/* T-shirt names: easy to remember, harder to extend */
:root {
  --space-sm: 4px;
  --space-md: 8px;
  --space-lg: 16px;
  --space-xl: 32px;
}

/* Numbered names: match the value, extend easily */
:root {
  --space-4: 0.25rem;  /* 4px */
  --space-8: 0.5rem;   /* 8px */
  --space-12: 0.75rem; /* 12px, added later between 8 and 16 */
  --space-16: 1rem;    /* 16px */
  --space-32: 2rem;    /* 32px */
}
```

## Check your work

- [ ] Each size scale uses one naming approach, not a mix like `space-md` next to `space-12`.
- [ ] Numbered names match their values in pixels: `--space-16` is 16px (or 1rem).
- [ ] T-shirt names run in a clear order, with no improvised in-between names like `md-plus` or `md2`.
- [ ] If a size was added to a t-shirt scale, the scale was renamed in one pass and every usage updated.

## When to break it

- Different scales can use different approaches: numbered spacing and t-shirt radii work fine side by side.
- Because numbered names say less about how a value is used, many systems add named tokens on top, like `--card-padding: var(--space-24)`.

## Before and after

- **T-shirt sizes:** a spacing table with `space-sm`, `space-md`, `space-lg` and `space-xl` (4, 8, 16 and 32px), and a new, highlighted 12px row between `md` and `lg` that has no obvious name: it reads `space-` followed by a red question mark.
- **Numbers:** the same table with `space-4`, `space-8`, `space-16` and `space-32`, and the new row is simply `space-12`.

| T-shirt sizes (`before.png`) | Numbers (`after.png`) |
| --- | --- |
| ![T-shirt sizes: a spacing table with `space-sm`, `space-md`, `space-lg` and `space-xl` (4, 8, 16 and 32px), and a new, highlighted 12px row between `md` and `lg` that has no obvious name: it reads `space-` followed by a red question mark.](before.png) | ![Numbers: the same table with `space-4`, `space-8`, `space-16` and `space-32`, and the new row is simply `space-12`.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **T-shirt sizes** and **Numbers**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
