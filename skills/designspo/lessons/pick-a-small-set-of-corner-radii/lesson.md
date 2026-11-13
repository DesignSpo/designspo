---
title: Pick a small set of corner radii
category: Design Systems
alt: A newsletter signup card with a New tag, an email input and a Subscribe button. Before, every part has its own corner radius, from 2px to 16px, so the input is rounder than the card and the button beside it is nearly square. After, three values, a medium radius on the card, a small one on the input and fully rounded corners on the button and tag.
---

Corner radius is how rounded an element’s corners are. When every component gets its own value, like 5px on buttons, 7px on cards and 10px on inputs, the site can start to look slightly inconsistent. Most visitors couldn’t tell you why, but they will still feel it.

Instead, pick three or four radius values and use only those. You might use a small radius for inputs, a medium one for cards and a fully rounded one for pill buttons and tags. Store each value as a token, a named variable like `--radius-md`, so you can reuse it everywhere and change it in one place later.
