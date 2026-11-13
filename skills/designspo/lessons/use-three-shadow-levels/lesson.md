---
title: Use three shadow levels
category: Design Systems
alt: A project card, a Sort by dropdown menu and a Publish changes dialog. Before, all three have the same light shadow, so the dialog looks no higher than the card. After, three shadow levels from left to right, each labelled, Level 1 with a subtle shadow on the card, Level 2 with a medium one on the menu and Level 3 with a strong one on the dialog, all tinted with a dark brand blue.
---

Shadows show how high an element sits above the page. A card resting on the page needs only a faint shadow, while a modal (a popup that floats over everything) needs a much stronger one. When shadows are picked by eye each time, the same kind of element can end up at different heights on different pages.

Most sites can get by with three shadow levels: a subtle one for cards, a medium one for dropdowns and menus, and a strong one for modals. Define them as tokens, like `--shadow-sm`, `--shadow-md` and `--shadow-lg`, so the same height always gets the same shadow. It may also help to tint your shadows with a dark shade of your brand color, which often looks more natural than pure black.
