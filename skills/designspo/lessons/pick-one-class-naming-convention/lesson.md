---
title: Pick one class naming convention
category: Design Systems
alt: A Global classes panel with six class names. Before, they mix naming styles: blueButton, btn-primary, CardWrapper, card__title, featuredCard and nav_link2. After, they all follow one pattern, BEM: btn, btn--primary, card, card__title, card--featured and nav__link.
---

When class names like `blueButton`, `btn-primary` and `card__title` all exist on the same site, trying to find the right class becomes difficult. You won’t usually remember what a class is called, so you end up creating a new one, and the list keeps growing.

Instead, pick one naming convention and follow it everywhere. BEM (short for Block, Element, Modifier) is a popular choice for this. It names a block, like `card`, then the parts inside it with two underscores, like `card__title`, and its variations with two dashes, like `card--featured`. Simple dashed names can work well too. Whichever you choose, write the rules down in your system docs, so everyone who works on the site names things the same way.
