---
title: Build dark mode by swapping token values
category: Design Systems
alt: A blog card styled with the tokens bg-surface and text-primary. In light mode, bg-surface points to neutral-50 and text-primary to neutral-900. In dark mode, the same two tokens point to neutral-900 and neutral-50, and the card turns dark without any change to the card itself.
---

Dark mode is much easier to build when your components use semantic tokens. A semantic token is named for its job, like `text-primary` or `bg-surface`, and it points to an actual color, like a dark navy or a light gray.

With tokens like these, changing a design to dark mode mostly means changing what each token points to. For example, `bg-surface` might be a very light gray in light mode and a very dark gray in dark mode, while every card and section that uses it stays exactly the same. Hardcoded colors, on the other hand, tend to make dark mode hard to add later, since each one has to be found and changed by hand.
