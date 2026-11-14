---
title: Combining component classes with utilities
category: Design Systems
alt: A Recent work text block, a small gap, then an ACME rebrand card, with the card’s classes beside what they style. Before, five utility classes sit on the card: padding-lg, border, radius-md and bg-white build its look, and margin-top-sm adds the gap above it. After, those four utilities move into a card component class that combines them with @apply, so the card only needs card and the margin-top-sm utility. The card looks the same in both.
---

There are two common kinds of classes designers frequently use to speed up their workflow. Component classes, like `.card`, which holds all the core styles that make a card look like a card. And utility classes, like `.margin-top-lg`, which just does one small job, like adding a large top margin.

Using both together can keep your design system clean and prevent unnecessary bloat. The component class keeps custom elements consistent, and a utility handles occasional adjustments, like extra space above one card, without creating a whole new class. I find that it’s worth keeping utilities small and tied to your tokens, though. If one element needs five utilities to look right, that’s usually a sign it deserves its own component class.
