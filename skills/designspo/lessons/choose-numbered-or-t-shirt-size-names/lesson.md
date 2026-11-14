---
title: Working with numbered and t-shirt size names
category: Design Systems
alt: A spacing token table with sizes of 4, 8, 16 and 32px, and a new 12px size being added between 8 and 16px. With t-shirt sizes, the tokens are named space-sm to space-xl and the new size has no obvious name, so it reads space- followed by a red question mark. With numbers, they are named space-4 to space-32 and the new one is simply space-12.
---

Tokens are the reusable values in your design system, and each one needs a unique name. For sizing there’s typically two common approaches. T-shirt names, like `sm`, `md` and `lg`, which are easy to remember and numbered names, like `space-4` and `space-8`, which often match the actual value in pixels (sometimes converted from rem units).

Both approaches are good but each comes with a trade-off. T-shirt names are harder to extend. If you need a size between `md` and `lg`, there’s no obvious name for it so you’ll have to update the sizing system directly. That can mean medium has a different value than it did before, which can break the rest of your design. Numbered names extend easily, since you can add `space-12` between `space-8` and `space-16`, but they say less about how a value is meant to be used. For example, should my card’s padding have `padding-12` or `padding-16`? Either can work well, but understanding their tradeoffs is important before you decide to commit to one.
