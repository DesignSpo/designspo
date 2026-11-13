---
name: document-your-design-system
title: Document your design system
category: Design Systems
summary: Put every token, class and component on a few plain reference pages, each with its name and a short note on when to use it, so nobody has to guess.
applies_to: [design system docs, style guides, tokens, classes, components]
source: https://designspo.co/document-your-design-system/
---

# Document your design system

A design system that lives only in someone's head breaks the moment someone else edits the site, or when its author comes back months later. People guess which color or class to use, and small differences creep in. A few reference pages that show every token, class and component, each with its name and a note on when to use it, fix that. They don't need to be fancy: a plain page people can find beats a polished document nobody opens.

## Rule

Keep a findable reference page (or a few) that shows every token, class and component with its name and a one-line note on when to use it. Update it whenever the system changes.

## How to apply

1. Create a style guide page somewhere people already look: a page on the site itself (hidden from navigation and search engines), the project README, or the team wiki.
2. Add a section for each part of the system: color swatches, type sizes, the spacing scale, and components like buttons.
3. For each item, show it rendered, then its exact name (`brand-500`, `heading-l`, `space-24`, `btn--outline`) and a short note on when to use it ("Buttons", "Page titles", "Card gaps", "Other actions").
4. Build the page from the real tokens and classes, so it can't drift from what the site uses.
5. Link to it from wherever people edit the site, and add new tokens or components to it as part of creating them.

```html
<section>
  <h2>Colors</h2>
  <figure>
    <div style="background: var(--brand-500); width: 48px; height: 48px"></div>
    <figcaption><strong>brand-500</strong><br>Buttons and links</figcaption>
  </figure>
</section>

<section>
  <h2>Buttons</h2>
  <figure>
    <a class="btn btn--outline" href="#">Learn more</a>
    <figcaption><strong>btn--outline</strong><br>Every action except the main one</figcaption>
  </figure>
</section>
```

## Check your work

- [ ] Every token, class and component in use appears on a reference page.
- [ ] Each item shows its exact name and a short note on when to use it.
- [ ] The page is linked from where people edit the site, and someone new can find it in under a minute.
- [ ] Nothing on the page is out of date: names and values match the live tokens and classes.

## When to break it

- A one-page site with a handful of styles can keep its notes in the stylesheet as comments; a separate page starts paying off once more than one person edits the site.

## Before and after

- **Before:** the styles in use on a site with no style guide: three near-identical blues under the classes `.blue`, `.blue-2` and `.primary`, type sizes of 32, 30, 17 and 16px, spacing of 22, 24, 25 and 64px, and three classes for the same button (`.btn`, `.button`, `.cta-btn`).
- **After:** a plain style guide page with fewer values, each with its name and when to use it: `brand-500` for buttons, `heading-l` for page titles, `space-24` for card gaps, `btn` for the main action and `btn--outline` for other actions. The near-duplicates merge into the value they repeat.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: the styles in use on a site with no style guide: three near-identical blues under the classes `.blue`, `.blue-2` and `.primary`, type sizes of 32, 30, 17 and 16px, spacing of 22, 24, 25 and 64px, and three classes for the same button (`.btn`, `.button`, `.cta-btn`).](before.png) | ![After: a plain style guide page with fewer values, each with its name and when to use it: `brand-500` for buttons, `heading-l` for page titles, `space-24` for card gaps, `btn` for the main action and `btn--outline` for other actions. The near-duplicates merge into the value they repeat.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
