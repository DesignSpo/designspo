---
title: Animate transform and opacity
category: Interaction
alt: A card slides to the right, easing in and out, and leaves a trail of lighter squares where it was at each eighth of the animation. Before, animated with left, it stalls and then jumps, leaving a big hole in the trail. After, animated with transform: translateX(), it moves smoothly and the trail bunches up at both ends and spreads out evenly through the middle.
---

Some CSS properties are much easier for the browser to animate than others. When you animate properties like `width`, `height`, `top` or `left`, the browser recalculates the layout of the page on every frame. That can make the animation stutter or the layout shift.

That’s why most web designers use two properties, `transform` and `opacity`, instead. The browser animates these properties without touching the layout, so they’re smoother and don’t cause layout shifts. So whenever you can, move elements with `translate` and resize them with `scale`. For example, to slide a card to the right, animate `transform: translateX()` and leave `left` alone.
