---
title: Relational Spacing
category: Layout
alt: A signup form with a heading, Name and Email fields and a Subscribe button, each gap tinted by relationship. Before, the gaps were picked one by one, so labels sit 4 or 12px from their inputs, fields 14 or 28px apart, and the heading only 18px above the form. After, every sibling gap is 8px, every neighbor gap 16px and the parent gap under the heading 32px.
---

When you design a website, the spacing between two elements tells the visitor how closely related they are to one another. For example, a form field and its label should be spaced close together. Two columns in a section might be spaced farther apart.

Because of this, it’s often useful to create “relational spacing rules” for your design. Instead of only using utility classes like gap-small, it can be helpful to map those classes onto certain relationships, like “siblings,” “neighbors,” or “parents.” This keeps the spacing of your design consistent across sections and pages. If two pairs of elements are related in the same way, they should have the same spacing. For example, two buttons in a call to action might have the same spacing as a form field and its button. Two cards might have the same spacing as a headline and a paragraph.

By giving these relationships semantic names, we make it easier to keep our spacing system consistent. Of course, we don’t have to use names like sibling, neighbor, parent, etc. We can also use a more conventional and scalable naming method like spacing-1, spacing-2, etc. But the more meaningful the names are, the more likely we are to remember each relationship later.
