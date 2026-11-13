---
title: When to use design tokens
category: Design Systems
alt: A Get started button, a Learn more link and a Lessons menu item, all in the brand blue. Before, each has the hex code #0C41DF typed in. After, a brand-color token holds #0C41DF, the button takes its color from a button-bg token and the link and menu item from a highlight token, both set to brand-color.
---

Design tokens are how complex, evolving designs keep their simplicity. They are a combination of a name and a value. Such as "background-color" being some hex code like "#fff" or "padding-large" being equal to "24px".

We want to use design tokens for things that come up again and again in a design, not for one-off decisions. The color of a background, of text, of buttons, of borders, are good examples. We'll likely use these colors many times.

Our spacing and sizing system is another great example. The size of padding, the gap between elements, the margin we give sections should be consistent across our website. If we change one value, like the gap between cards, we generally want that reflected across the website.

This makes keeping our design system updated and building new pages much easier. We no longer have to remember certain hex code values or exactly how much padding we gave a button. We have tokens for that.

Sometimes we have multiple tokens for the same value, but different use cases. For example we might have a token for our main brand color called "brand-color" with a value of "#0C41DF" (DesignSpo's brand color). Our buttons may also use the same color but we shouldn't tie it to the same token. We should create another token, say called "button-color" with the value of "brand-color". That way, we can change the value of button-color in the future without affecting our brand-color, but if we update our brand-color our buttons will also change.

This keeps design choices at the right level of specificity. We change some things like buttons fairly often (when we A/B test for example and find a winner), but we change our main brand color much less often. Creating these multiple layers of design tokens lets us keep the design consistent while still remaining modular.
