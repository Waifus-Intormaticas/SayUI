# P5 Comparative Evaluation Plan

This document is the official inventory and execution policy for P5.1 comparative evaluation.

P5.1 compares modern SayUI primitives with related original public patterns. It does not migrate, replace, rename, or remove original components. Comparative demos are evidence for future decisions, not migration approval by themselves.

## Official P5.1 Comparisons

| ID | Modern component | Original pattern | Evaluation focus |
| --- | --- | --- | --- |
| P5.1-01 | `ui-section-header` | `ui-main__heading` | Main-content section heading |
| P5.1-02 | `ui-section-header` | `ui-sidebar__section-title` | Sidebar section heading |
| P5.1-03 | `ui-section-header` | `ui-article-sidebar__section-title` | Editorial sidebar heading |
| P5.1-04 | `ui-section-header--related` | `ui-article-related__header` | Related-content heading and divider |
| P5.1-05 | `ui-eyebrow` | `ui-banner__eyebrow` | Featured editorial label |
| P5.1-06 | `ui-eyebrow` | `ui-post-card__eyebrow` | Card-level editorial label |
| P5.1-07 | `ui-eyebrow` | `ui-article-related__category` | Related-card category label |
| P5.1-08 | `ui-meta-list` | `ui-post-card__meta` | Compact card metadata |
| P5.1-09 | `ui-meta-list` | `ui-banner__meta` | Featured-content metadata |
| P5.1-10 | `ui-tag-list` | `ui-article-main__tags` | Article tag group |
| P5.1-11 | `ui-tag-list` | `ui-article-sidebar__tags` | Editorial sidebar tag cloud |
| P5.1-12 | `ui-pullquote` | `ui-article-main__quote` | Editorial quotation |
| P5.1-13 | `ui-newsletter` | `ui-sidebar__newsletter` | Sidebar subscription block |
| P5.1-14 | `ui-author-card` | `ui-article-sidebar__author` | Full author presentation |
| P5.1-15 | `ui-related-list` | `ui-article-sidebar__list` | Compact related-content list |
| P5.1-16 | `ui-byline` | `ui-banner__author` | Compact authorship and metadata |
| P5.1-17 | `ui-comment` | `ui-article-main__comment` | Individual comment and simple reply |
| P5.1-18 | `ui-comment-form` | `ui-article-main__comment-form` | Comment-entry form |
| P5.1-19 | `ui-trending-list` | `ui-sidebar__trending-list` | Compact content list with media |
| P5.1-20 | `ui-social-links` | `ui-article-sidebar__social` | Author/sidebar social links |
| P5.1-21 | `ui-social-links` | `ui-footer__socials` | Main-footer social links |
| P5.1-22 | `ui-social-links` | `ui-footer-editorial__social` | Editorial-footer social links |

## Official Evaluation Criteria

Every comparison must evaluate the following dimensions:

### Visual fidelity

- Overall visual intent.
- Shape, borders, backgrounds, and emphasis.
- Whether the primitive preserves the recognizable role of the original pattern.
- Whether differences are intentional improvements or incompatible changes.

### Spacing

- Internal padding and gaps.
- External rhythm in the original context.
- Alignment with surrounding content.
- Behavior in narrow and wide containers.

### Typography

- Font size, weight, line height, case, and letter spacing.
- Heading or text hierarchy.
- Readability at equivalent content lengths.

### Responsive behavior

- Mobile and desktop presentation.
- Wrapping, stacking, overflow, and minimum sizes.
- Behavior inside the original layout context.
- Dependence on parent width or original component selectors.

### Accessibility

- Native semantic structure.
- Accessible names and relationships.
- Keyboard interaction and visible focus where applicable.
- Image alternatives, `time datetime`, labels, and decorative content.
- Any accessibility improvement that would change the original contract.

### Migration risk

- Markup incompatibility.
- Selector or cascade conflicts.
- Visual regressions.
- Responsive regressions.
- Accessibility regressions.
- Effects on demos, documentation, and consumer-facing contracts.

Each comparison should record concise evidence for all six criteria. Similar appearance alone is not enough to approve migration.

## Allowed Results

Every comparison must end with exactly one of these results:

| Result | Meaning |
| --- | --- |
| `Convive` | Both patterns remain valid for different contexts. No replacement is proposed. |
| `Experimental` | The relationship is promising but needs more visual, responsive, or contract validation. |
| `Migrable` | A future controlled adoption is reasonable after a specific migration contract is approved. |
| `No migrar` | Semantics, visual role, composition, or risk make replacement inappropriate. |

`Migrable` does not authorize a code change. It only permits a later migration proposal.

## Excluded From P5.1

The following implemented components are intentionally excluded because they do not need comparison with an original pattern during P5.1:

- `ui-callout`
- `ui-table`
- `ui-code-block`
- `ui-toc`

The following proposed components are also excluded because they do not exist in SayUI v1:

- `ui-category-list`: flat vertical categories with counts use the documented `ui-tag-list` composition.
- `ui-comment-list`: comment groups use the documented semantic composition with multiple `ui-comment` components.

P5.1 must not create these excluded components as a side effect of comparison work.

## Recommended Execution Order

The five official lots prioritize comparisons with clear boundaries and manageable review scope.

### Lot 1

- `ui-byline` compared with `ui-banner__author`
- `ui-related-list` compared with `ui-article-sidebar__list`

Purpose: begin with compact display-only patterns whose semantic boundaries are already documented.

### Lot 2

- `ui-trending-list` compared with `ui-sidebar__trending-list`
- `ui-social-links` compared with `ui-article-sidebar__social`

Purpose: evaluate media sizing and navigational link groups without changing the composed sidebar.

### Lot 3

- `ui-author-card` compared with `ui-article-sidebar__author`
- `ui-newsletter` compared with `ui-sidebar__newsletter`

Purpose: evaluate larger composed blocks. Newsletter remains an individual review because it contains a form.

### Lot 4

- `ui-pullquote` compared with `ui-article-main__quote`
- `ui-comment` compared with `ui-article-main__comment`

Purpose: compare editorial content patterns while keeping `ui-article-main` unchanged.

### Lot 5

- `ui-comment-form` compared with `ui-article-main__comment-form`
- `ui-section-header` compared with its official editorial heading patterns

The section-header review covers:

- `ui-main__heading`
- `ui-sidebar__section-title`
- `ui-article-sidebar__section-title`
- `ui-article-related__header` using `ui-section-header--related`

Purpose: finish with form behavior and the broader heading family, both of which need careful contextual review.

## Complementary Comparison Queue

The following official comparisons remain required after the five priority lots:

- `ui-eyebrow` compared with `ui-banner__eyebrow`
- `ui-eyebrow` compared with `ui-post-card__eyebrow`
- `ui-eyebrow` compared with `ui-article-related__category`
- `ui-meta-list` compared with `ui-post-card__meta`
- `ui-meta-list` compared with `ui-banner__meta`
- `ui-tag-list` compared with `ui-article-main__tags`
- `ui-tag-list` compared with `ui-article-sidebar__tags`
- `ui-social-links` compared with `ui-footer__socials`
- `ui-social-links` compared with `ui-footer-editorial__social`

These comparisons are part of P5.1 even though they are not assigned a numbered priority lot. They should be scheduled after Lot 5 or pulled into a related lot only when that does not expand the lot beyond a reviewable scope.

## P5.1 Operating Rules

- Original components remain unchanged during comparative evaluation.
- Comparative demos must isolate the primitive and original pattern without altering either internal contract.
- Demo-only layout must use `demo-*` classes and must not enter the public bundle.
- A result must be documented before any adoption proposal.
- No migration may be implemented without separate explicit approval.
- P5.1 favors controlled validation over additional component extraction.
