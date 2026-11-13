---
title: Stop hardcoding values
category: Design Systems
alt: A Sign up button and a Buy now button. Before, each has its own hex code typed in, #0C41DF on Sign up and a drifted #2F60F4 on Buy now, so the two blues don't match. After, both take their color from one brand-500 token, #0C41DF, and match.
---

A hard-coded value is a color or size typed straight into one element, like `#0C41DF` on a single button. It works at first, but as your website gets bigger these hard-coded values won’t get updated if you decide to make a change. When you update the color of your buttons, for example, the site can end up with two slightly different versions if you forget one.

If your system has a token (a named variable) for that value, use it, even for a single element. `var(--brand-500)` gives you the same blue as `#0C41DF`, and it updates automatically when the token changes. It also makes your intent clearer to anyone reading the styles later, since a name like `brand-500` says more than a hex code.
