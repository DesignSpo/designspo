---
title: Set type sizes as tokens
category: Design Systems
alt: Intro paragraphs from three pages, Home, Pricing and Blog. Before, each page has its own font size typed in, 17px, 16px and 18px, so the same kind of paragraph looks slightly different on each. After, all three take their size from one body-md token set to 16px.
---

When font sizes are chosen by eye on each page, they slowly drift apart. One page uses 17px for body text, another uses 16px, and a third uses 18px for the same kind of paragraph. Each section looks fine when you're building it, but as visitors navigate through your website they notice the inconsistency.

Instead, we can define a set of type tokens to control font size, like `text-sm`, `text-md`, `text-lg` and `text-xl`, and pick from them everywhere. Headings, labels and body text then stay in one family of sizes. If you later decide body text should be a little larger, you can change `text-base` once, and every paragraph on the site updates with it.

If you want a different scale for headings and body copy, you can still build it from this core set of utility tokens. `text-xl` might translate to `heading-md`, for example. This keeps your entire type system consistent while still giving you easily readable semantic tokens.
