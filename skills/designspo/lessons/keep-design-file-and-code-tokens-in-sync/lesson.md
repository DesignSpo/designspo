---
title: Keep design file and code tokens in sync
category: Design Systems
alt: Figma and CSS token lists side by side, with a line joining each pair. Before, they have drifted far apart: Figma’s brand-500 and brand-hover are blue but the CSS still has orange for both, and bg-surface is still called --surface in the CSS, so three of the four pairs are marked as not matching. After, the CSS was updated to match, and all four names and colors are the same in both.
---

Many designers keep tokens in two places: as variables in a design tool like Figma, and as CSS variables on the live site. If the two drift apart, designs will stop matching what actually gets built. A color renamed in Figma but not in the CSS, for example, can lead to guesswork and small mismatches.

So it’s best practice to use the same token names in both places and update them together. When you add or change a token, change it in the design file and on the site in the same sitting. It also helps to do a quick side-by-side check before each new project. Comparing the two lists only takes a few minutes, and it can save a lot of rework later.
