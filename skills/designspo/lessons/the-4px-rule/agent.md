---
name: the-4px-rule
title: The 4px Rule
category: Layout
summary: Make every size, padding, margin and gap divisible by 4px (0.25rem), so values are quick to choose and remember and everything fits on a grid of 4×4 squares.
applies_to: [spacing, sizing, padding, margins, gaps, component dimensions, design tokens]
source: https://designspo.co/the-4px-rule/
---

# The 4px Rule

The 4px rule says every element, padding, margin and spacing or sizing value should be divisible by 4. It's simple to remember (count up or down by 4), it's divisible without giving too many options (no choosing between 28px and 30px), and it keeps the layout visually consistent, because everything fits on a grid of 4×4 squares. Since modern sites size in rem (1rem is usually 16px), it's really the 0.25rem rule. Ready-made systems like Untitled UI use it.

## Rule

Use only multiples of 4px (0.25rem) for widths, heights, padding, margins and gaps. To get the next size, count up or down by 4.

## How to apply

1. Define a spacing scale in 4px steps as tokens in rem, in the global tokens file.
2. Replace values that aren't divisible by 4 with the nearest step: 7px becomes 8px, 22px becomes 24px, 46px becomes 48px.
3. Size components from the scale: if medium padding is 16px, small is 12px and large is 20px.
4. For type, skip steps so headings stand out from body text (a 16px paragraph needs a 28px or 32px heading, not 20px), with a custom type scale that still uses multiples of 4.
5. Handle screen sizes at breakpoints, with a tighter max-width at each, so no layout gets lost in the margins.

```css
:root {
  --space-1: 0.25rem;  /* 4px */
  --space-2: 0.5rem;   /* 8px */
  --space-3: 0.75rem;  /* 12px */
  --space-4: 1rem;     /* 16px */
  --space-5: 1.25rem;  /* 20px */
  --space-6: 1.5rem;   /* 24px */
  --space-12: 3rem;    /* 48px */
}

.card { padding: var(--space-6); }                      /* 24px, not 22px */
.card__title { margin-bottom: var(--space-2); }         /* 8px, not 7px */
.card__button { height: var(--space-12); }              /* 48px, not 46px */
```

## Check your work

- [ ] Every width, height, padding, margin and gap is a multiple of 4px (0.25rem). 1px borders are the only exception.
- [ ] Spacing values come from the scale's tokens, not raw numbers.
- [ ] With a 4px grid laid over a screenshot, element edges sit on grid lines.
- [ ] Heading sizes are far enough from the body size to stand out.

## When to break it

- Where smooth responsiveness matters more than a perfectly clean layout, like web apps: the 4px rule is adaptive, so it snaps to breakpoints instead of scaling. Use values tied to the viewport width with clamp() instead.
- Type scales: 4px steps give a weak sense of scale, so skip steps or use a scale that grows by a percentage.

## Before and after

- **Before:** a newsletter card with a Subscribe button, labelled like a spec: 22px of padding, a 7px gap under the title and a 46px button. None of them is divisible by 4, so the labels are red.
- **After:** the values snap to the nearest multiple of 4, 24px, 8px and 48px, and the labels turn blue.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a newsletter card with a Subscribe button, labelled like a spec: 22px of padding, a 7px gap under the title and a 46px button. None of them is divisible by 4, so the labels are red.](before.png) | ![After: the values snap to the nearest multiple of 4, 24px, 8px and 48px, and the labels turn blue.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
