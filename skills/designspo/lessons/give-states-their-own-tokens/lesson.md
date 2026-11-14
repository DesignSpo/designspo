---
title: Give states their own tokens
category: Design Systems
alt: Three brand buttons, Sign up, Subscribe and Buy now, in their default, hover and disabled states. Before, only the default state has a token, and each button’s hover and disabled colors were picked by eye, so they all differ. After, the tokens bg-brand_hover and bg-brand_disabled give every button the same hover and disabled colors.
---

Buttons, links and inputs change when people interact with them. They have hover, active, disabled and error states, and each of those needs colors too. If you pick those colors by eye every time, every component can end up with a slightly different hover shade.

State tokens can fix this. For example, a token like `bg-brand_hover` holds the hover color for brand buttons, so every button that uses it darkens by the same amount. The same idea works for disabled and error colors. Once these tokens exist, new components react the same way as the old ones, with no extra decisions.
