---
title: Style the default elements first
category: Design Systems
alt: A text column with a heading, a paragraph, a link, a bulleted list and a callout, each marked with what styles it. Classes first, every element has its own class: title, text, link, list and callout. Defaults first, the heading, paragraph, link and list are styled by their tags alone, h1, p, a and ul, and only the callout, which is different, keeps a class. The column looks the same in both.
---

Global styles for body text, headings, links and lists can cover most of a site before you add in custom classes. When defaults are styled well, most elements will look good as soon as you add them to the page. You shouldn't have to worry about a ton of custom classes, variables, or tokens for most new layouts.

That’s why it helps to set your default HTML elements first. Classes then only need to handle unique things, like cards, larger paragraphs, or a special heading. This can often cut down on the number of classes you need, since you’re not mapping unique classes to default elements.
