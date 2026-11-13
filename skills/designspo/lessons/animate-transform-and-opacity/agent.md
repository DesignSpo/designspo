---
name: animate-transform-and-opacity
title: Animate transform and opacity
category: Interaction
summary: Animate transform and opacity instead of width, height, top or left, so the browser skips layout on every frame and animations stay smooth on slower devices.
applies_to: [animations, transitions, sliders, drawers, modals, hover effects]
source: https://designspo.co/animate-transform-and-opacity/
---

# Animate transform and opacity

Some CSS properties are much easier for the browser to animate than others. Animating `width`, `height`, `top` or `left` makes the browser recalculate the layout of the page on every frame, and on slower devices that extra work can make the animation stutter. `transform` and `opacity` work differently: the browser can animate them without touching the layout, so they tend to stay smooth even on older phones.

## Rule

Whenever you can, animate only `transform` and `opacity`: move elements with translate, resize them with scale and fade them with opacity. To slide a card to the right, animate `transform: translateX()` and leave `left` alone.

## How to apply

1. Find animations and transitions: `@keyframes`, `transition` declarations and animation library calls.
2. Replace animated `top`, `left`, `right`, `bottom` and `margin` with `transform: translate()`, or the `translate` property.
3. Replace animated `width` and `height` with `transform: scale()` where the content can scale without distorting.
4. Fade with `opacity`.
5. List the properties in each transition (`transition: transform 300ms`) instead of `all`, so a layout property can't slip in.

```css
/* Before: animating left makes the browser redo layout on every frame */
.card { position: relative; left: 0; transition: left 300ms ease; }
.card.is-moved { left: 240px; }

/* After: transform moves the card without touching layout */
.card { transition: transform 300ms ease, opacity 300ms ease; }
.card.is-moved { transform: translateX(240px); }
.card.is-hidden { opacity: 0; }
```

## Check your work

- [ ] No `transition` or `@keyframes` animates `width`, `height`, `top`, `left`, `right`, `bottom` or `margin`.
- [ ] No transition uses `all`.
- [ ] Elements that move use `translate`, elements that grow use `scale`, and elements that appear or disappear fade with `opacity`.
- [ ] A performance recording of the animation shows no layout work on each frame.

## When to break it

- Some effects, like an accordion opening, can't use scale without squashing their content. If you must animate height, keep it short and on small elements.
- Colors and shadows don't affect layout, so short transitions on `background-color` or `box-shadow` for hover states are usually fine.

## Before and after

- **Before:** a card slides to the right by animating `left`, easing in and out. A slow device is simulated with dropped frames: the card stalls, then jumps, so the trail of squares marking where it was at each eighth of the animation has a big hole in the middle.
- **After:** the same eased slide with `transform: translateX()`. Every frame is drawn, so the card moves smoothly and the trail bunches up at both ends and spreads out evenly through the middle.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a card slides to the right by animating `left`, easing in and out. A slow device is simulated with dropped frames: the card stalls, then jumps, so the trail of squares marking where it was at each eighth of the animation has a big hole in the middle.](before.png) | ![After: the same eased slide with `transform: translateX()`. Every frame is drawn, so the card moves smoothly and the trail bunches up at both ends and spreads out evenly through the middle.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
