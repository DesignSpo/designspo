---
name: give-states-their-own-tokens
title: Give states their own tokens
category: Design Systems
summary: Define tokens for interaction states, like bg-brand_hover and bg-brand_disabled, so every component uses the same hover, active, disabled and error colors instead of shades picked by eye.
applies_to: [buttons, links, inputs, hover states, active states, disabled states, error states]
source: https://designspo.co/give-states-their-own-tokens/
---

# Give states their own tokens

Buttons, links and inputs change when people interact with them: they have hover, active, disabled and error states, and each state needs colors too. When those colors are picked by eye each time, every component ends up with a slightly different hover shade. State tokens fix this: a token like `bg-brand_hover` holds the hover color for brand buttons, so every button that uses it darkens by the same amount, and new components react the same way as the old ones with no extra decisions.

## Rule

Give each interaction state its own color token next to the base token, like `bg-brand` and `bg-brand_hover`, and style every component's states with those tokens, never with a color chosen for one component.

## How to apply

1. List the interactive components: buttons, links, inputs and anything else with states.
2. For each base color token they use, like `bg-brand`, add tokens for its states: `_hover`, `_active`, `_disabled`. Add error tokens for inputs, like `border-error` and `text-error`.
3. Point each state token at a step of the palette, so every hover changes by the same amount.
4. Replace hand-picked state colors and one-off opacity tricks in component styles with the state tokens.
5. Use the same tokens when you build new components.

```css
:root {
  --bg-brand: var(--brand-500);
  --bg-brand_hover: var(--brand-700);
  --bg-brand_disabled: var(--brand-200);
  --text-on-brand_disabled: var(--brand-50);
}

.button { background: var(--bg-brand); }
.button:hover { background: var(--bg-brand_hover); }

.button:disabled,
.button[aria-disabled="true"] {
  background: var(--bg-brand_disabled);
  color: var(--text-on-brand_disabled);
}
```

## Check your work

- [ ] Every `:hover`, `:active`, disabled and error style uses a state token, not a raw color or an ad-hoc opacity.
- [ ] All brand-colored components show the same hover color and the same disabled look.
- [ ] Each state token is defined once, next to its base token.

## When to break it

- A component on a different background, like a button on a dark section, may need its own set, such as `bg-inverse_hover`. Define those as tokens too.

## Before and after

- **Before:** three brand buttons, Sign up, Subscribe and Buy now, share `bg-brand` for their default state, but their hover and disabled colors were picked by eye: three different hover blues and three different disabled looks.
- **After:** `bg-brand_hover` and `bg-brand_disabled` give all three buttons the same hover and disabled colors.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: three brand buttons, Sign up, Subscribe and Buy now, share `bg-brand` for their default state, but their hover and disabled colors were picked by eye: three different hover blues and three different disabled looks.](before.png) | ![After: `bg-brand_hover` and `bg-brand_disabled` give all three buttons the same hover and disabled colors.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
