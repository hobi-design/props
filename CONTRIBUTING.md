# Contributing to PROPS

PROPS sections are written and tested in a separate workspace, and this repository is published from it automatically. Files here are replaced on every sync, so a fix is applied at the source and reaches this repository from there.

## Report a theme

Theme reports are what we need most: sections are designed to work in any theme, but we test on Dawn and can't cover the rest ourselves.

[Open a theme report](https://github.com/hobi-design/props/issues/new?template=theme-report.yml) with the theme's name and version, the section you used, and what you saw. A screenshot or a link to the page helps more than a description. Reports that a section works are welcome too, because they tell the next person that the section works in their theme.

## Report a bug

If a section behaves wrongly in a way that has nothing to do with the theme, such as a setting that does nothing, a layout that breaks at a certain width or a control that can't be reached by keyboard, [open a bug report](https://github.com/hobi-design/props/issues/new?template=bug-report.yml).

## Request a section

[Tell us what you had to build yourself](https://github.com/hobi-design/props/issues/new?template=section-request.yml) or what your theme left out. A link to a store that already does it well is the most useful thing you can include.

## Pull requests

Fixes to a section are welcome as pull requests, although we close them unmerged: we apply an accepted change at the source and it arrives here with the next sync, credited to you in the commit.

For anything larger than a fix, open an issue first so we can agree on the approach before you spend time on it.

## What a section has to do

Sections are built to the standard below, and a contributed change has to keep to it. A few of the earliest sections predate parts of it, so a report of where one falls short is useful too.

- **One file.** Schema, styles, markup and script live in a single `.liquid` file, with no snippets, assets or build step.
- **No dependencies.** Plain JavaScript and DOM APIs only. The section can't assume the theme loads jQuery, Swiper or anything else.
- **Namespaced and scoped.** Every class starts with `props-` and the section's name, and per-instance styles are scoped to `section.id`, so two copies on one page don't interfere with each other or with the theme.
- **Settings a merchant can read.** Plain-language labels, grouped in the order someone thinks about a section: layout, content, typography, spacing, colors.
- **Accessible.** Keyboard operable, visible focus states, touch targets of at least 44px, and a pause control on anything that moves by itself.
- **Reduced motion respected.** With `prefers-reduced-motion` set, the content stays visible and usable and the automatic movement stops.
- **A clean empty state.** A section with no content renders nothing on the storefront and shows a short prompt in the theme editor.
