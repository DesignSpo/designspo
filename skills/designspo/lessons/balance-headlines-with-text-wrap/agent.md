---
name: balance-headlines-with-text-wrap
title: Balance headlines with text-wrap
category: Typography
summary: "Add text-wrap: balance to headings so a headline that wraps splits into even lines instead of leaving one word alone."
applies_to: [headings, short intros, captions]
source: https://designspo.co/balance-headlines-with-text-wrap/
---

# Balance headlines with text-wrap

Headlines that wrap onto a second line often leave a single short word hanging out on its own. That unbalances the design and can pull attention toward the least important word in the heading, and manual line breaks don't solve it, because they break again on other screen sizes. The CSS property `text-wrap: balance` tells the browser to even out the line lengths in short blocks of text, so a two-line headline splits into two lines of similar length.

## Rule

Add `text-wrap: balance` once to your heading styles, and to short intros and captions. Don't use manual line breaks to control where a headline wraps.

## How to apply

1. Find the global heading styles: a base or typography stylesheet, a theme file, or a shared heading component.
2. Add `text-wrap: balance` to `h1` through `h6`, and to the classes you use for short intros and captions.
3. Remove `<br>` tags that were added only to control where a headline breaks.
4. You don't need a fallback: all modern browsers support it, and older ones ignore it and wrap as usual.

```css
/* Headings, plus your classes for short intros and captions */
h1, h2, h3, h4, h5, h6,
.intro,
figcaption {
  text-wrap: balance;
}
```

## Check your work

- [ ] The global heading styles (`h1` to `h6`) include `text-wrap: balance`.
- [ ] In screenshots at a phone width and a desktop width, no wrapped headline leaves a single word alone on its last line.
- [ ] No headline contains a `<br>` used only to control where it breaks.
- [ ] Long body paragraphs keep normal wrapping.

## When to break it

- Long paragraphs and body copy: `balance` is meant for short blocks of text like headings, intros and captions, so leave longer text with normal wrapping.

## Before and after

- **Before:** the headline "We build websites that win customers" wraps with "customers" alone on the second line.
- **After:** with `text-wrap: balance`, the same headline splits into two lines of similar length.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: the headline "We build websites that win customers" wraps with "customers" alone on the second line.](before.png) | ![After: with `text-wrap: balance`, the same headline splits into two lines of similar length.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
