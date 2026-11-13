---
name: combining-component-classes-with-utilities
title: Combining component classes with utilities
category: Design Systems
summary: Put a component's core styles in one component class and use small, token-based utility classes only for occasional adjustments, like extra space above one card.
applies_to: [CSS classes, components, utility classes, spacing, design systems]
source: https://designspo.co/combining-component-classes-with-utilities/
---

# Combining component classes with utilities

There are two common kinds of classes. A component class, like `.card`, holds all the core styles that make a card look like a card. A utility class, like `.margin-top-lg`, does one small job, like adding a large top margin. Used together, they keep the design system clean: the component class keeps every card consistent, and a utility handles the occasional adjustment without creating a whole new class.

## Rule

Give each component one class that holds its core styles. For one-off adjustments to a single instance, add a small utility class tied to a token instead of creating a new component class. If an element needs about five utilities to look right, give it a component class instead.

## How to apply

1. Put the styles every instance shares (padding, border, radius, background, type) in a component class like `.card`.
2. Keep a short set of utilities that each do one job and use your tokens, such as `.margin-top-lg` set to the large spacing token.
3. When one instance needs a small adjustment, like extra space above one card, add the utility to that element: `class="card margin-top-sm"`. Don't create `.card-spaced` or a similar copy.
4. When an element carries a long list of utilities to get its basic look, move those styles into a component class and keep only the adjustments as utilities.

```css
/* Component class: the core styles every card shares, built from the same tokens */
.card {
  padding: var(--space-lg);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-md);
  background: var(--bg-white);
}

/* Or, with Tailwind, combine the existing utilities into the component class */
.card { @apply padding-lg border radius-md bg-white; }

/* Utility: one small job, tied to a token */
.margin-top-sm { margin-top: var(--space-sm); }
```

```html
<!-- Not this: five utilities to build a card -->
<article class="padding-lg border radius-md bg-white margin-top-sm">…</article>

<!-- This: the component class, plus one utility for the extra space -->
<article class="card margin-top-sm">…</article>
```

## Check your work

- [ ] Each component's core look comes from one component class, the same on every instance.
- [ ] Utility classes each do one job and use token values, not raw numbers.
- [ ] No element needs about five or more utilities to look right.
- [ ] One-off adjustments use a utility rather than a new near-copy of the component class.

## When to break it

- If the same adjustment appears on most instances of a component, it isn't occasional any more: make it part of the component class or a variant.

## Before and after

- **Before:** a card built from five utilities: `padding-lg`, `border`, `radius-md` and `bg-white` for its look, and `margin-top-sm` for the gap above it.
- **After:** those four utilities move into a `.card` component class that combines them with `@apply padding-lg border radius-md bg-white`, so the card only needs `card` and the `margin-top-sm` utility. The card looks the same in both.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a card built from five utilities: `padding-lg`, `border`, `radius-md` and `bg-white` for its look, and `margin-top-sm` for the gap above it.](before.png) | ![After: those four utilities move into a `.card` component class that combines them with `@apply padding-lg border radius-md bg-white`, so the card only needs `card` and the `margin-top-sm` utility. The card looks the same in both.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
