---
name: when-to-use-design-tokens
title: When to use design tokens
category: Design Systems
summary: "Use design tokens for the colors, spacing and sizes that repeat across a design, and give uses like button backgrounds and highlights their own tokens that point at the shared ones."
applies_to: [colors, spacing, sizing, buttons, design systems, CSS custom properties]
source: https://designspo.co/when-to-use-design-tokens/
---

# When to use design tokens

A design token is a name paired with a value, like `background-color` set to `#fff` or `padding-large` set to `24px`. Tokens keep a complex, evolving design simple: a value that comes up again and again is defined once, so changing it in one place changes it across the whole site, and nobody has to remember hex codes or how much padding a button got. They're for repeated decisions, not one-offs.

## Rule

Use a token for every value that repeats across the design: the colors of backgrounds, text, buttons and borders, and the padding, gaps and section margins of the spacing system. When a component shares a value with something that changes on a different schedule, like a button in the brand color, give the component its own token whose value is the shared token.

## How to apply

1. Find the values that repeat: colors (backgrounds, text, buttons, borders) and spacing and sizing (padding, gaps between elements, section margins).
2. Define each one once as a base token named for what it is, usually as CSS custom properties on `:root` in a global stylesheet or theme file.
3. Where a component reuses a base value but may change on its own, add a component token whose value is the base token. Buttons are the usual case: they change after an A/B test far more often than the brand color does.
4. Replace raw hex codes and pixel values in component styles with tokens.
5. Leave values that are used in only one place as plain values.

```css
:root {
  /* Base tokens: each value defined once */
  --brand-color: #0C41DF;
  --space-small: 12px;
  --space-large: 24px;

  /* Tokens for each use: follow the brand color, but can be changed on their own */
  --button-bg: var(--brand-color);
  --highlight: var(--brand-color);
}

.button {
  background: var(--button-bg); /* not #0C41DF */
  padding: var(--space-small) var(--space-large);
}

a,
.menu-item {
  color: var(--highlight);
}
```

## Check your work

- [ ] Component styles have no raw hex codes, and no pixel values that repeat elsewhere: colors and spacing come from tokens.
- [ ] Each repeated value is defined once, as a base token.
- [ ] Buttons use their own token (like `--button-bg`) whose value is the brand token, rather than the brand token or a hex code.
- [ ] Changing the brand token changes the buttons too; changing the button token changes only the buttons.
- [ ] Values used in only one place are left as plain values.

## When to break it

- One-off decisions: a value used in a single place doesn't need a token.
- Add a token per use (like `button-bg` or `highlight`), not per component: the link and the menu item share `highlight`, because they change together.

## Before and after

- **Before:** a "Get started" button, a "Learn more" link and a "Lessons" menu item, each with the hex code `#0C41DF` typed in.
- **After:** a `brand-color` token holds `#0C41DF`. The button takes its color from a `button-bg` token, and the link and menu item from a `highlight` token, both set to `brand-color`. Everything looks exactly the same as before.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a "Get started" button, a "Learn more" link and a "Lessons" menu item, each with the hex code `#0C41DF` typed in.](before.png) | ![After: a `brand-color` token holds `#0C41DF`. The button takes its color from a `button-bg` token, and the link and menu item from a `highlight` token, both set to `brand-color`. Everything looks exactly the same as before.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
