---
name: style-the-defaults-first
title: Style the default elements first
category: Design Systems
summary: Set global styles for body text, headings, links and lists before writing classes, so plain elements look right without one and classes only handle what's different.
applies_to: [body text, headings, links, lists, global styles, CSS classes]
source: https://designspo.co/style-the-defaults-first/
---

# Style the default elements first

Global styles for body text, headings, links and lists can cover most of a site before you add a single class. When those defaults are set well, a plain paragraph or a basic list looks right the moment it's added to a page. Classes then only handle what's different, like a card or a special heading, which cuts down the number of classes because nobody rebuilds the same basic styles on every element.

## Rule

Style the plain HTML elements (`body`, `h1` to `h6`, `p`, `a`, `ul`, `ol`, `li`) globally before creating classes. Add a class only to elements that should look different from those defaults.

## How to apply

1. In the global stylesheet (or the builder's theme styles), set the body font, size, line height and color.
2. Style `h1` to `h6` with the heading font, sizes, weights and spacing.
3. Style links (`a`, plus `:hover` and `:focus-visible`) and lists (`ul`, `ol`, `li`), including their markers and spacing.
4. Add a plain heading, paragraph, link and list to a test page and check they look finished without any class.
5. Remove classes that only repeat the defaults, like `.title`, `.text`, `.link` or `.list`, and keep classes for elements that are truly different.

```css
/* Defaults: plain elements look right with no class */
body { font: 400 1rem/1.5 Inter, sans-serif; color: #45556C; }
h1, h2, h3 { font-family: "Bricolage Grotesque", sans-serif; color: #0F172B; line-height: 1.1; }
h1 { font-size: 2rem; }
a { color: #0C41DF; text-underline-offset: 0.2em; }
ul { padding-left: 1.25em; }
li + li { margin-top: 0.25em; }

/* Classes only for what's different */
.callout { padding: 0.75em 1em; border-radius: 8px; background: #E7EDFE; font-weight: 600; }
```

## Check your work

- [ ] A heading, paragraph, link and list with no classes look finished on a blank page.
- [ ] No classes exist only to repeat the default styles of a tag.
- [ ] The classes that remain each change something about the default, like a card, a callout or a special heading.

## When to break it

- When the site sits inside another system whose base styles you can't control, like an embed or a third-party theme, scope the defaults to a wrapper class instead of styling the bare tags.

## Before and after

- **Classes first:** a heading, paragraph, link, list and callout, each with its own class: `.title`, `.text`, `.link`, `.list` and `.callout`.
- **Defaults first:** the same column looks identical, but the heading, paragraph, link and list are styled by their tags alone (`h1`, `p`, `a`, `ul`), and only the callout keeps a class.

| Classes first (`before.png`) | Defaults first (`after.png`) |
| --- | --- |
| ![Classes first: a heading, paragraph, link, list and callout, each with its own class: `.title`, `.text`, `.link`, `.list` and `.callout`.](before.png) | ![Defaults first: the same column looks identical, but the heading, paragraph, link and list are styled by their tags alone (`h1`, `p`, `a`, `ul`), and only the callout keeps a class.](after.png) |

## Files

- `before.png` and `after.png`: screenshots of the two states, **Classes first** and **Defaults first**.
- `demo.html`: a self-contained page that shows the lesson working. Open it in a browser.
- `lesson.md`: the lesson as written on designspo.co, word for word.
