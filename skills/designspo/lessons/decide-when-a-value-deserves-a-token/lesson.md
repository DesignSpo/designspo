---
title: Decide when a value deserves a token
category: Design Systems
alt: A hero section with a headline, a line of text, a Start learning button and a decorative circle, with the values that style it labelled beside it. Before, every value is a token, including shape-size and shape-offset for the circle, which is the only place they’re used. After, section-padding, text-body and brand-500 stay tokens, and the circle keeps its 212px size and -24px offset as plain custom values.
---

Tokens, the named values in your design system, are useful, but turning everything into a token can make your design system harder to use. A token for a 13px gap that appears in only one place is one more name to remember and one more option to scroll past.

I like to use a simple test: if a value appears in three or more places, or you’d want to change it everywhere at once, make it a token. For example, your brand color and your standard section padding clearly qualify. A one-off value tied to a single component, like the exact width of a decorative shape, should usually stay in that component’s styles.
