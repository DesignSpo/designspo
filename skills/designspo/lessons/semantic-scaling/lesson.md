---
title: Semantic Scaling
category: Design Systems
alt: A spacing scale in two columns: primitive values from 12px to 32px, each drawn as a bar, and the semantic names xs, sm, md, lg and xl, with an arrow from each value to its name. Before, xl points to 28px. After, xl points to 32px instead, and 28px stays in the scale.
---

When we create a scaling system, we start by defining the raw values (4px, 8px, 12px, etc.) and then give those values names, like small, medium, and large. These are called semantic values because their names have meaning.

We separate our raw numbers from our semantic values (also called tokens) for two reasons.

One, it’s far easier to remember “small, medium, and large” than it is to remember the exact pixel values. That’s even more true if we scale by a ratio, like the golden ratio. If our smallest pixel value is 4px, the next one in the golden ratio would be about 6.5px (4 × 1.618). So it’s easier to remember “extra small” and “small” than 4px and 6.5px.

Two, we can freely change our semantic tokens without changing the raw values. Maybe we want “extra large” to be 32px instead of 28px. Instead of erasing 28px from our scale, we can simply map the “extra large” token onto a different value in our scale. That way, anything else still using the 28px value is unaffected.

Separating raw values (also called primitive tokens) from semantic tokens is common in web design for these reasons. The values are easier to remember, and the design system is much more flexible as a result.
