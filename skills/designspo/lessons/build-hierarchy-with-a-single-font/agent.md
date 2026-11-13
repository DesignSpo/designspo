---
name: build-hierarchy-with-a-single-font
title: Creating hierarchy with a single typeface
category: Hierarchy
summary: Create typographic contrast with size, weight, letter case and shade within one font family, instead of adding a second typeface for it.
applies_to: [typography, headings, body text, labels, font loading]
source: https://designspo.co/build-hierarchy-with-a-single-font/
---

# Creating hierarchy with a single typeface

You don't need two typefaces to create contrast. One font family can do all the work through size, weight, letter case and shade: a large bold heading, regular body text and a small uppercase line all look clearly different, even in the same font. Many clean sites use a single family in three or four weights, which keeps the page consistent and helps it load faster, since there are fewer font files to download.

## Rule

Use one font family in three or four weights, and build hierarchy with size, weight, letter case and shade. If you add a second typeface, use it for headings only and keep everything else in the main family.

## How to apply

1. List the font families and weights the site loads: `@font-face` rules, font service links and `font-family` declarations.
2. Choose one family for everything and limit it to three or four weights, like 400, 600 and 700.
3. Make each text style differ from its neighbors in more than one way: headings large and bold, body text regular in a softer shade, small labels uppercase with letter spacing.
4. Remove the font files and weights the page no longer uses.

```css
body { font-family: Inter, system-ui, sans-serif; }

h2 {
  font-size: 2.5rem;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: #0f172b;
}

p {
  font-size: 1rem;
  font-weight: 400;
  color: #45556c;
}

.eyebrow {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #0c41df;
}
```

## Check your work

- [ ] The site loads one font family, or two with the second used only for headings.
- [ ] No more than three or four weights of the main family are loaded.
- [ ] Headings, body text and small labels each differ in at least two of size, weight, case and shade.
- [ ] In a screenshot, the heading, body text and small label are clearly different at a glance.

## When to break it

- A second typeface for headings only is a common addition, as long as everything else stays in the main family.
- Code samples can use a monospace font.

## Before and after

- **Two fonts:** a sale card reading "Spring sale", "Every plan is 20% off this week." and "Offer ends Sunday", with a serif heading and a serif italic last line beside sans-serif body text, all at about the same size, so the hierarchy is weak.
- **One font:** the same card set entirely in Inter, with a large bold heading, regular gray body text and a small blue uppercase line.

| Two fonts (`before.png`) | One font (`after.png`) |
| --- | --- |
| ![Two fonts: a sale card reading "Spring sale", "Every plan is 20% off this week." and "Offer ends Sunday", with a serif heading and a serif italic last line beside sans-serif body text, all at about the same size, so the hierarchy is weak.](before.png) | ![One font: the same card set entirely in Inter, with a large bold heading, regular gray body text and a small blue uppercase line.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Two fonts** and **One font**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
