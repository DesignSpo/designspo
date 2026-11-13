---
name: consistent-spacing-rules
title: Consistent Spacing Rules
category: Layout
summary: Take every size and space from one scale, built with a ratio or a fixed step, and give every component of a kind the same spacing rules, instead of eyeballing each one.
applies_to: [spacing, padding, gaps, cards, components, spacing scales, design tokens]
source: https://designspo.co/consistent-spacing-rules/
---

# Consistent Spacing Rules

An easy way to make a layout more consistent is to apply one set of spacing rules to every element. Every component follows the same rules (all cards have the same padding, for example), and every size and space comes from a single scale. A scale gives the site a mathematical consistency that's hard to reach by eyeballing, and it makes the sizes easier to remember.

## Rule

Build one spacing scale, with either a ratio or a fixed step, and use only its values. Give every component of the same kind the same spacing rules.

## How to apply

1. Choose how the scale grows:
   - By a ratio: multiply each step by 1.25 (the major third), 1.5 (the perfect fifth) or 1.618 (the golden ratio). From 4px at 1.5x: 4, 6, 9, 13.5px.
   - By a fixed step: add the same amount each time, like the 4px rule (4, 8, 12, 16px), the 8px rule, or, less commonly, the 2px rule.
2. Store the scale as tokens in rem, based on the browser's default font size (usually 16px), so 4px is 0.25rem.
3. Write each component's spacing rules with scale tokens only (card padding, the gap between a title and its text), and reuse them for every instance.
4. Replace eyeballed values with the nearest step.

```css
:root {
  /* Fixed step: +4px (0.25rem) */
  --space-1: 0.25rem; /* 4px */
  --space-2: 0.5rem;  /* 8px */
  --space-3: 0.75rem; /* 12px */
  --space-4: 1rem;    /* 16px */
  --space-6: 1.5rem;  /* 24px */
}

/* One set of rules for every card */
.card { padding: var(--space-6); }
.card__icon { margin-bottom: var(--space-4); }
.card__title { margin-bottom: var(--space-2); }
.card__text { margin-bottom: var(--space-4); }
```

## Check your work

- [ ] Every padding, margin and gap is a token from the one scale, with no raw pixel values.
- [ ] Components of the same kind share the same spacing: every card has the same padding and the same gaps inside.
- [ ] The scale follows one rule: a single ratio or a single fixed step.
- [ ] Scale values are in rem.

## When to break it

- A variant that's meant to look different, like a compact card, can have its own rules, as long as its values still come from the same scale.

## Before and after

- **Before:** two feature cards with eyeballed spacing. One is cramped into its corner with 10px of padding, the other has 30 to 40px, and the gaps inside swing from 4 to 30px, so the icons, titles, text and links sit at different heights and the cards end at different heights.
- **After:** both cards follow the same rules from one scale: 24px of padding, 16px below the icon and below the text, and 8px between the title and the text, so every part lines up across the two cards.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: two feature cards with eyeballed spacing. One is cramped into its corner with 10px of padding, the other has 30 to 40px, and the gaps inside swing from 4 to 30px, so the icons, titles, text and links sit at different heights and the cards end at different heights.](before.png) | ![After: both cards follow the same rules from one scale: 24px of padding, 16px below the icon and below the text, and 8px between the title and the text, so every part lines up across the two cards.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
