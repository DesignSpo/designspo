---
name: use-opacity-to-blend-borders
title: Use opacity to blend borders
category: Color
summary: Use black at 10 to 15% opacity for borders instead of a solid light gray, so one border color blends in on any background.
applies_to: [borders, cards, dividers]
source: https://designspo.co/use-opacity-to-blend-borders/
---

# Use opacity to blend borders

A solid light gray border looks fine on white, but on a colored background it stands out as a pale outline. Black at 10 to 15% opacity blends in with whatever background color an element has, and it works better in most cases. You only need one border color token instead of one per component, and if you change a component's color later, its border still blends in.

## Rule

Draw borders in black at 10 to 15% opacity, like `rgb(0 0 0 / 0.12)`, instead of a solid light gray, and keep that color in one token. In dark mode, use white at a low opacity instead.

## How to apply

1. Find the solid gray border colors on cards, dividers and other components, like `#E5E7EB`, `#DDD` or `lightgray`.
2. Create one border color token set to black at 10 to 15% opacity, usually in `:root` in the global stylesheet.
3. Use that token for all of those borders, whatever the component's background.
4. If the site has a dark mode, set the same token to white at a low opacity wherever dark mode is switched on (a media query or a theme class).

```css
:root {
  --border-color: rgb(0 0 0 / 0.12); /* black at 12% */
}

/* Only if the site has a dark mode: white at a low opacity */
@media (prefers-color-scheme: dark) {
  :root { --border-color: rgb(255 255 255 / 0.12); }
}

.card {
  border: 1px solid var(--border-color);
}
```

## Check your work

- [ ] Borders use one token set to black at 10 to 15% opacity, not solid grays or a separate color per component.
- [ ] In a screenshot, borders on colored backgrounds look like a slightly darker shade of that color, not a pale gray line.
- [ ] If the site has a dark mode, the border token switches to white at a low opacity there.

## When to break it

- Borders that carry meaning, like a red error outline or a focus ring, keep their own solid color.
- If a form field's border is the only thing that shows where the field is, it may need more contrast than 10 to 15% gives. WCAG asks for at least 3:1 there.

## Before and after

- **Before:** a section with a light blue tint holds three cards, white, light blue and blue, that share a solid light gray border (#CAD5E2). It shows as a pale gray ring around the two blue cards.
- **After:** the borders are black at 12% opacity, so each becomes a slightly darker shade of its own card and blends in on all three.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a section with a light blue tint holds three cards, white, light blue and blue, that share a solid light gray border (#CAD5E2). It shows as a pale gray ring around the two blue cards.](before.png) | ![After: the borders are black at 12% opacity, so each becomes a slightly darker shade of its own card and blends in on all three.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
