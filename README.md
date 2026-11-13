# DesignSpo lessons for AI agents

Short, practical web design lessons from [DesignSpo](https://designspo.co), written for AI coding agents like Claude Code, Cursor and Codex. Each lesson is one rule your agent can apply to any website, with steps, generic code, checks, and before and after images.

Install all of them as one skill, or give your agent a single lesson.

## Install the skill

### Claude Code

```
/plugin marketplace add DesignSpo/designspo
/plugin install designspo@designspo
```

Then ask for design work as usual and Claude uses the lessons when they fit, or run `/designspo:designspo` with a task, for example `/designspo:designspo review the pricing page`.

To use it as `/designspo` instead, copy the skill folder into your skills:

```
git clone https://github.com/DesignSpo/designspo.git
cp -r designspo/skills/designspo ~/.claude/skills/
```

### Other agents

Copy `skills/designspo/` into your agent's skills folder. The skill is a plain `SKILL.md` with the lessons beside it, so any agent that supports Agent Skills can use it.

## Give your agent one lesson

Open a lesson from the list below and download its `agent.md` (the download button on the file's page), or paste the file's link into your agent. Each `agent.md` stands on its own.

## What's in each lesson

Each lesson is a folder in [`skills/designspo/lessons/`](skills/designspo/lessons/):

| File | What it is |
| --- | --- |
| `agent.md` | The lesson for agents: the rule, how to apply it, checks, exceptions, and the before and after states |
| `before.png`, `after.png` | Screenshots of the two states, labelled in `agent.md` |
| `demo.html` | A self-contained page that shows the lesson working. Download it and open it in a browser. |
| `lesson.md` | The lesson as written on designspo.co |

## Lessons

<!-- lessons:start -->

### Color

- [Build a palette from one brand color](skills/designspo/lessons/build-a-palette-from-one-brand-color/agent.md): Turn one brand color into a ramp of 9 to 11 shades of the same hue, numbered 50 to 950, and take backgrounds, borders, buttons and text from its steps instead of picking each color by eye.
- [Use opacity to blend borders](skills/designspo/lessons/use-opacity-to-blend-borders/agent.md): Use black at 10 to 15% opacity for borders instead of a solid light gray, so one border color blends in on any background.

### Components

- [Build a pricing card](skills/designspo/lessons/build-a-pricing-card/agent.md): Order pricing cards as plan name, price, features and button, make the price the largest text with the billing period small beside it, and keep feature lists short and in the same order on every plan.
- [Write specific testimonials](skills/designspo/lessons/build-a-testimonial-card/agent.md): Give each testimonial a short, specific quote, the person's name, their role or company, and a real photo, so it doesn't look invented.

### Conversion

- [A/B test one change at a time](skills/designspo/lessons/a-b-test-one-change-at-a-time/agent.md): Change one meaningful thing per A/B test, like the headline or the button, so the result tells you which change made the difference.
- [Anchor your price with a higher plan](skills/designspo/lessons/anchor-your-price-with-a-higher-plan/agent.md): Show a genuinely bigger, higher-priced plan beside your main plan, so the main plan reads as the sensible choice instead of the most expensive thing on the page.
- [Avoid dark patterns](skills/designspo/lessons/avoid-dark-patterns/agent.md): Replace design tricks that push people into choices, like pre-checked add-ons at checkout, cancel links that are hard to find and decline links that shame people, with honest options that are as easy to decline as to accept.
- [Choose testimonials with specific results](skills/designspo/lessons/choose-testimonials-with-specific-results/agent.md): Feature testimonials that name a specific result, ideally a number or a clear before and after, instead of vague praise that could describe any company.
- [Collect objections from sales and support](skills/designspo/lessons/collect-objections-from-sales-and-support/agent.md): Ask sales and support for the top five questions and objections they hear, then answer each one on the page where it comes up, like security near the signup form and setup time on the pricing page.
- [Find where visitors drop off](skills/designspo/lessons/find-where-visitors-drop-off/agent.md): Build a funnel report for the path to a conversion, compare the drop-off between steps, and work first on the step with the biggest drop.
- [Give your tests enough time to run](skills/designspo/lessons/give-your-tests-enough-time-to-run/agent.md): Decide how many visitors each version of an A/B test needs before it starts, and don't stop the test or pick a winner until they've all had that many.
- [Offer a smaller first step](skills/designspo/lessons/offer-a-smaller-first-step/agent.md): Add a smaller first step, like a free guide, a product tour or a free trial, beside a call to action that asks for a big commitment, styled as a secondary button or text link.
- [Place trust signals near the next step](skills/designspo/lessons/place-trust-signals-near-the-ask/agent.md): Put trust signals, like a privacy note, a review rating or a guarantee, right beside the form's submit button or the checkout button, where people hesitate, instead of leaving them in the footer.
- [Remove friction before adding persuasion](skills/designspo/lessons/remove-friction-before-adding-persuasion/agent.md): Before adding testimonials, bolder headlines or countdown timers to a page that isn't converting, find and remove the friction that makes the next step harder, like slow pages, long or confusing forms and surprise costs at checkout.
- [Reverse the risk with a guarantee](skills/designspo/lessons/reverse-the-risk-with-a-guarantee/agent.md): State a guarantee, like a 30-day money-back guarantee or a free trial, plainly next to the price and the buy button, and only offer terms the business will honor without a fight.
- [Run a five-second test on your hero](skills/designspo/lessons/run-a-five-second-test-on-your-hero/agent.md): Show the hero section to someone for five seconds, hide it and ask what the company does, and rewrite the headline if they can't say or describe something different.
- [Showing who uses your product already](skills/designspo/lessons/show-how-many-people-already-use-it/agent.md): Add one short line of social proof, like "Used by 3,000 dental clinics", right under a headline or call-to-action button, with a number that's large for the market and specific to the audience.
- [Test your website with people in person](skills/designspo/lessons/test-your-website-with-people-in-person/agent.md): Find a site's biggest usability problems by watching about five people try a simple task, like finding out what it costs, instead of waiting for lots of analytics data.
- [Track one conversion goal per page](skills/designspo/lessons/track-one-conversion-goal-per-page/agent.md): Decide the single action that counts as success for each key page, like a demo request on the homepage or a signup on a landing page, and track it as one conversion event or goal in analytics.
- [Track the in-between steps](skills/designspo/lessons/track-the-small-steps-too/agent.md): Track micro-conversions, small actions that show interest like watching a demo video, visiting the pricing page or starting a form, alongside the final sale or signup, so you can see which pages move people closer to deciding.
- [Use the thank-you page for the next step](skills/designspo/lessons/use-the-thank-you-page-for-the-next-step/agent.md): Turn the page people see after submitting a form into a next step, by confirming what happens next and offering one related action, like booking a call or reading a short case study.
- [Use urgency only when it’s real](skills/designspo/lessons/use-urgency-only-when-its-real/agent.md): Use countdowns, deadlines and scarcity labels only for real limits, like an event date, a price increase or a program that's actually filling up, and state each one as a specific, true claim.
- [Watch session recordings to find confusion](skills/designspo/lessons/watch-session-recordings-to-find-confusion/agent.md): Watch 10 to 20 session recordings of a key page, note where visitors hesitate, scroll back up or click things that aren't links, and fix the spots that keep coming up.

### Copy

- [Add reassurance to your CTA](skills/designspo/lessons/add-reassurance-next-to-the-button/agent.md): Replace a vague call-to-action label like "Sign up" with one that says what happens, and add one short, true line of small, muted text under the button, such as "No credit card required" under "Start your free trial", to answer the worry that makes people hesitate before they click.

### Design Systems

- [Build dark mode by swapping token values](skills/designspo/lessons/build-dark-mode-by-swapping-token-values/agent.md): Style components with semantic tokens like bg-surface and text-primary, then build dark mode by changing what those tokens point to instead of restyling each component.
- [Change component colors easily](skills/designspo/lessons/change-component-colors-easily/agent.md): Add component color tokens like button-color, card-border and badge-color on top of primitive and semantic tokens, so one component's color changes by re-pointing one token instead of using a raw color.
- [Clean out unused classes](skills/designspo/lessons/clean-out-unused-classes/agent.md): Every few months, find the CSS classes that nothing on the site uses any more and delete them, after checking popups and conditional elements.
- [Combining component classes with utilities](skills/designspo/lessons/combining-component-classes-with-utilities/agent.md): Put a component's core styles in one component class and use small, token-based utility classes only for occasional adjustments, like extra space above one card.
- [Decide when a value deserves a token](skills/designspo/lessons/decide-when-a-value-deserves-a-token/agent.md): Make a value a design token only if it appears in three or more places or you'd want to change it everywhere at once, and keep one-off values in the component's own styles.
- [Define breakpoints once](skills/designspo/lessons/define-breakpoints-once/agent.md): Pick three or four site-wide breakpoints, like 480px, 768px and 1024px, and use only those in every media query, so every part of the page changes layout at the same widths.
- [Document your design system](skills/designspo/lessons/document-your-design-system/agent.md): Put every token, class and component on a few plain reference pages, each with its name and a short note on when to use it, so nobody has to guess.
- [Give states their own tokens](skills/designspo/lessons/give-states-their-own-tokens/agent.md): Define tokens for interaction states, like bg-brand_hover and bg-brand_disabled, so every component uses the same hover, active, disabled and error colors instead of shades picked by eye.
- [Keep design file and code tokens in sync](skills/designspo/lessons/keep-design-file-and-code-tokens-in-sync/agent.md): Use the same token names in the design tool (like Figma variables) and in the CSS, change both in the same sitting, and compare the two lists before each new project.
- [Keep your scales short](skills/designspo/lessons/keep-your-scales-short/agent.md): Give each component a short list of three or four spacing options that point to your primitives, instead of letting it use every value on the full scale.
- [Pick a small set of corner radii](skills/designspo/lessons/pick-a-small-set-of-corner-radii/agent.md): Limit corner radii to three or four values stored as tokens, so components don't each get their own slightly different rounding.
- [Pick one class naming convention](skills/designspo/lessons/pick-one-class-naming-convention/agent.md): Name every CSS class with one convention, such as BEM, and write the rules down, so people can find existing classes instead of creating near-duplicates.
- [Semantic Scaling](skills/designspo/lessons/semantic-scaling/agent.md): Define a scale's raw values as primitive tokens and map semantic names like small, medium and large onto them, so sizes are easy to remember and a name can move to another value without changing the scale.
- [Set type sizes as tokens](skills/designspo/lessons/set-type-sizes-as-tokens/agent.md): Define font sizes as a small set of type tokens, like text-sm, text-md and text-xl, give each kind of text a semantic token built from them, like body-md, and pick from those everywhere, so the same kind of text has the same size on every page.
- [Start your system from a real page](skills/designspo/lessons/start-your-system-from-a-real-page/agent.md): Build one real page first, then turn the colors, sizes and spacing it actually uses into tokens, and grow the system from each new page instead of deciding every value up front.
- [Stop hardcoding values](skills/designspo/lessons/stop-hardcoding-values/agent.md): Use the design system's token, like var(--brand-500), instead of typing a raw value like #0C41DF into an element, even when only one element needs it.
- [Style the default elements first](skills/designspo/lessons/style-the-defaults-first/agent.md): Set global styles for body text, headings, links and lists before writing classes, so plain elements look right without one and classes only handle what's different.
- [Two-Dimensional Scales](skills/designspo/lessons/two-dimensional-scales/agent.md): Give each semantic size token a value per breakpoint, so one name like heading-lg maps to a smaller primitive on phones and a larger one on desktop.
- [Use component variants](skills/designspo/lessons/give-components-variants/agent.md): Build the forms of a component, like large, outlined or icon buttons, as variants of one base class plus small modifier classes, instead of separate copies.
- [Use three shadow levels](skills/designspo/lessons/use-three-shadow-levels/agent.md): Define three shadow tokens, subtle for cards, medium for dropdowns and menus and strong for modals, so elements at the same height always get the same shadow.
- [When to use design tokens](skills/designspo/lessons/when-to-use-design-tokens/agent.md): Use design tokens for the colors, spacing and sizes that repeat across a design, and give uses like button backgrounds and highlights their own tokens that point at the shared ones.
- [Working with numbered and t-shirt size names](skills/designspo/lessons/choose-numbered-or-t-shirt-size-names/agent.md): Choose between t-shirt size names (sm, md, lg) and numbered names (space-4, space-8) for size tokens on purpose, knowing that t-shirt names read more easily but numbered names are easier to extend.

### Hierarchy

- [Asymmetric grid layouts](skills/designspo/lessons/asymmetric-grid-layouts/agent.md): Split two-column sections unevenly on a 12-column grid, like 7 and 5 or 8 and 4, and give the wider side to the more important content.
- [Balancing images and text](skills/designspo/lessons/balance-big-images-against-text/agent.md): Decide whether the image or the headline leads, and if it's the headline, make the image smaller and lighter and the headline bigger and bolder.
- [Creating hierarchy with a single typeface](skills/designspo/lessons/build-hierarchy-with-a-single-font/agent.md): Create typographic contrast with size, weight, letter case and shade within one font family, instead of adding a second typeface for it.
- [Visual hierarchy is like a pyramid](skills/designspo/lessons/visual-hierarchy-is-like-a-pyramid/agent.md): Give each section one element that stands out, a few that get noticed and a consistent, quiet style for everything else, like the tiers of a pyramid.

### Interaction

- [Add hover states only to things you can click](skills/designspo/lessons/add-hover-states-only-to-things-you-can-click/agent.md): Give hover effects only to links, buttons and other elements that do something, so a hover never promises a click that goes nowhere.
- [Animate elements using short distances](skills/designspo/lessons/animate-short-distances/agent.md): Keep entrance animations to a small move of about 8 to 24px paired with a fade, so people don't wait for elements to travel across the screen.
- [Animate transform and opacity](skills/designspo/lessons/animate-transform-and-opacity/agent.md): Animate transform and opacity instead of width, height, top or left, so the browser skips layout on every frame and animations stay smooth on slower devices.

### Layout

- [Align elements to edges](skills/designspo/lessons/align-elements-to-the-same-edges/agent.md): Line up the elements in a section on two or three shared edges, and remove stray margin, padding or centered text that gives an element an edge of its own, so the section doesn't look busy.
- [Balancing imagery in two-column layouts](skills/designspo/lessons/balance-image-and-text-in-split-sections/agent.md): Center both columns of a split section vertically and size the image to about the height of the text beside it, so the section doesn't feel lopsided.
- [Consistent Spacing Rules](skills/designspo/lessons/consistent-spacing-rules/agent.md): Take every size and space from one scale, built with a ratio or a fixed step, and give every component of a kind the same spacing rules, instead of eyeballing each one.
- [Relational Spacing](skills/designspo/lessons/relational-spacing/agent.md): Name spacing values after relationships like sibling, neighbor and parent, and give every pair of elements that relate the same way the same spacing.
- [Reorganize lonely cards](skills/designspo/lessons/avoid-a-lonely-card-in-the-last-row/agent.md): Plan the number of items in a card grid around its column count, so every row is full instead of one card sitting alone on the last row.
- [The 4px Rule](skills/designspo/lessons/the-4px-rule/agent.md): Make every size, padding, margin and gap divisible by 4px (0.25rem), so values are quick to choose and remember and everything fits on a grid of 4×4 squares.
- [Thinking in grids](skills/designspo/lessons/thinking-in-grids/agent.md): Pick a base grid unit that divides easily (4, 8, 16 or 32px), place and size every element on it, and break the grid only on purpose.

### Navigation

- [Add a skip to content link for articles](skills/designspo/lessons/add-a-skip-link-for-keyboard-users/agent.md): Add a "Skip to content" link as the first focusable element on every page, hidden until someone presses Tab, so keyboard users can jump past the header straight to the main content.
- [Add a table of contents to long pages](skills/designspo/lessons/add-a-table-of-contents-to-long-pages/agent.md): Add a table of contents that links to each main section of long guides, documentation and policies, so readers can jump straight to the part they need instead of scrolling to find it.

### Typography

- [Balance headlines with text-wrap](skills/designspo/lessons/balance-headlines-with-text-wrap/agent.md): Add text-wrap: balance to headings so a headline that wraps splits into even lines instead of leaving one word alone.
- [Build a fluid type scale with clamp()](skills/designspo/lessons/build-a-fluid-type-scale-with-clamp/agent.md): Size each step of the type scale with clamp(min, preferred, max) stored as a variable, so text grows smoothly with the screen width instead of jumping at media query breakpoints.

<!-- lessons:end -->

## License

The lessons are licensed under [CC BY 4.0](LICENSE). You can use, share and adapt them, including commercially, as long as you credit DesignSpo with a link to [designspo.co](https://designspo.co).
