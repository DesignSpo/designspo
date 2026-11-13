---
title: Consistent Spacing Rules
category: Layout
alt: Two feature cards, Fast setup and Clear pricing. Before, their spacing was eyeballed, so one card is cramped with 10px of padding while the other has 30 to 40px, the gaps inside swing from 4 to 30px, and nothing lines up across the cards. After, both follow the same rules from one scale, 24px of padding and gaps of 8 and 16px, and the icons, titles, text and links glide into line.
---

An easy way to make your website’s layout more consistent is to apply one set of spacing rules to every element on your website. Every component should follow the same rules (all cards have the same padding, for example), and the sizing and spacing of every element should come from a single scale.

We can create these scales using either a ratio or a fixed size difference. For example, if our smallest size is 4px, our next size would be larger by some ratio, let’s say 1.5x, which gives us 6px. We could also use a fixed size difference, so each step in our scale is equally spaced out. If we start again with 4px, our next size might be 8px, then 12px, etc.

Creating these scales gives our website a mathematical consistency that’s hard to achieve by eyeballing it. It also makes it easier to remember the exact sizes we use on our website.

Common ratios include 1.25x (known as the major third), 1.5x (the perfect fifth), and 1.618x (the golden ratio). Common equal steps are the 4px rule, the 8px rule, and, less commonly, the 2px rule.

Note also that these values are usually converted to rem, a unit based on the browser’s default font size (usually 16px). So 4px would actually be 0.25rem.
