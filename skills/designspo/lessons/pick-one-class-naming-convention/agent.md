---
name: pick-one-class-naming-convention
title: Pick one class naming convention
category: Design Systems
summary: Name every CSS class with one convention, such as BEM, and write the rules down, so people can find existing classes instead of creating near-duplicates.
applies_to: [CSS classes, global classes, components, design system docs]
source: https://designspo.co/pick-one-class-naming-convention/
---

# Pick one class naming convention

When class names like `blueButton`, `btn-primary` and `card__title` all exist on the same site, finding the right class becomes difficult. Nobody remembers what a class is called, so they create a new one, and the class list keeps growing. One naming convention, followed everywhere and written down, makes names predictable: if you know the pattern, you can guess the name.

## Rule

Pick one class naming convention and use it for every class on the site. BEM (Block, Element, Modifier) is a popular choice; simple dashed names work too. Write the rules down in the design system docs.

## How to apply

1. Look at the existing classes and choose a convention. If you pick BEM:
   - a block is the component itself: `card`
   - an element is a part inside it, after two underscores: `card__title`
   - a modifier is a variation, after two dashes: `card--featured`
2. Write the rules and a few examples in the design system docs, where everyone who edits the site will find them.
3. Rename classes that break the convention, and update every place they're used in the same change.
4. Before adding a new class, search for an existing one that follows the pattern.

```html
<article class="card card--featured">
  <h3 class="card__title">Brightside rebrand</h3>
  <a class="btn btn--primary" href="/work/brightside">Read the case study</a>
</article>
```

```css
.card { padding: 24px; border-radius: 12px; }
.card__title { font-size: 1.25rem; }
.card--featured { border: 2px solid currentColor; }
```

## Check your work

- [ ] Every class name follows the chosen convention: no camelCase or PascalCase next to dashed or BEM names.
- [ ] Parts and variations of a component share the block's name as a prefix (`card__title`, `card--featured`).
- [ ] No near-duplicates: searching for a component's name finds one family of classes, not several spellings of the same thing (`blueButton` next to `btn-primary`).
- [ ] The convention is written down in the design system docs, with examples.

## When to break it

- Third-party and plugin classes you can't rename keep their own names. Leave them as they are.
- Changing convention on a large live site is risky: apply it to new and refactored code first, then rename the rest in planned batches.

## Before and after

- **Before:** a Global classes panel listing `blueButton`, `btn-primary`, `CardWrapper`, `card__title`, `featuredCard` and `nav_link2`, five different naming styles.
- **After:** the same six classes named with BEM: `btn`, `btn--primary`, `card`, `card__title`, `card--featured` and `nav__link`.

| Before (`before.png`) | After (`after.png`) |
| --- | --- |
| ![Before: a Global classes panel listing `blueButton`, `btn-primary`, `CardWrapper`, `card__title`, `featuredCard` and `nav_link2`, five different naming styles.](before.png) | ![After: the same six classes named with BEM: `btn`, `btn--primary`, `card`, `card__title`, `card--featured` and `nav__link`.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Before** and **After**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
