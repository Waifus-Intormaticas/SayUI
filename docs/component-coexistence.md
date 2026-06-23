# Component Coexistence Matrix

This document defines the official coexistence policy between SayUI's original public components and newer reusable primitives.

Modern primitives do not make original components legacy. Original components remain public compositions unless a future migration is designed, documented, tested in demos, and explicitly approved.

## Official Status Criteria

| Status | Meaning |
| --- | --- |
| Implementado | The public component exists with HTML, SCSS, documentation, bundle import, and demo coverage. This does not approve migration of an original pattern. |
| Conviven | The primitive and original pattern can exist side by side. No migration is expected. |
| Experimental en demo | The primitive is close enough to an original pattern to test visually in demos before any real migration. |
| Migracion futura posible | The primitive could replace or standardize part of an original component later, after contract approval. |
| No migrar | The overlap is superficial or semantically incorrect. The primitive should not replace the original pattern. |
| Requiere contrato futuro | Another component or integration contract is needed before deciding whether migration makes sense. |

## Official Matrix

| Modern primitive | Related original patterns | Official status | Justification | Adoption risk | Potential benefit | Future dependencies | Before real migration |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `ui-section-header` | `ui-main__heading`, `ui-sidebar__section-title`, `ui-article-sidebar__section-title`, `ui-article-related__header`, `ui-article-main__section-title` | Experimental en demo | It matches section heading semantics, but original contexts have different scale, rhythm, and composition needs. | Medium | A shared section-heading contract could reduce repeated title patterns. | Stable editorial/related variants. | Validate side-by-side in demos and document which original heading patterns can adopt it. |
| `ui-eyebrow` | `ui-banner__eyebrow`, `ui-post-card__eyebrow`, `ui-article-hero__eyebrow`, `ui-article-related__category`, `ui-article-sidebar__category` | Migracion futura posible | These are mostly single editorial labels or category links with similar semantics. | Low/medium | Strong reuse for labels and category markers. | Clear rules for `span` vs `a`. | Confirm visual parity for base, editorial, muted, accent, and underline treatments. |
| `ui-meta-list` | `ui-post-card__meta`, `ui-banner__meta`, `ui-sidebar__item-meta`, `ui-article-hero__meta-group`, `ui-article-main__meta` | Migracion futura posible | Compact metadata overlaps strongly, while hero/article metadata can be more structured. | Medium | Standard metadata semantics, separators, and `time datetime` usage. | Distinction between compact metadata and structured metadata. | Migrate only simple metadata first; postpone complex hero/article metadata. |
| `ui-tag-list` | `ui-article-main__tags`, `ui-article-sidebar__tags`, `ui-sidebar__categories` | Migracion futura posible | Article tags map well. Vertical categories with counts are covered in v1 by the official stacked `ui-tag-list` composition. | Medium | Shared tag/category contract and accessible interactive states. | No `ui-category-list` contract is required in v1. | Test article tags and the documented vertical category composition in comparative demos before considering adoption. |
| `ui-pullquote` | `ui-article-main__quote` | Experimental en demo | It directly matches editorial quote semantics but should preserve the original visual rhythm before migration. | Medium | A reusable quote component for articles and editorial pages. | Stable `--editorial` behavior. | Validate `blockquote`, cite, and decorative mark handling against the original article quote. |
| `ui-newsletter` | `ui-sidebar__newsletter` | Experimental en demo | It represents the same signup block, but the sidebar version is integrated into a larger composition. | Medium | Reusable newsletter block outside sidebars. | Form/accessibility contract stays stable. | Validate `--strong` against the dark sidebar pattern and decide whether sidebar keeps its internal markup. |
| `ui-author-card` | `ui-article-sidebar__author` | Experimental en demo | The article-sidebar author block maps well. Banner bylines and comment authors now have separate `ui-byline` and `ui-comment` contracts. | Medium/high | Reusable author presentation for sidebars and editorial contexts. | Comparative demo against the article-sidebar author block. | Do not use it to migrate banner bylines or comment authors. |
| `ui-byline` | `ui-banner__author`, partial author/metadata patterns in `ui-article-hero` | Implementado / Experimental en demo | The public component now covers compact authorship, optional avatar, and short publication metadata without becoming an author card. | Medium | Standard compact authorship across banners, previews, and simple hero contexts. | Comparative demo and explicit adoption contract. | Validate visual parity and metadata boundaries before changing banner or hero markup. |
| `ui-comment` | Comment blocks inside `ui-article-main` | Implementado / Conviven | The public component now represents an individual comment, including simple reply presentation, while the original article composition remains valid. | Medium | Reusable, accessible comment markup outside article-main. | Comparative demo and article-main adoption contract. | Do not migrate `ui-article-main` until its complete comments composition is visually approved. |
| `ui-comment-form` | `ui-article-main__comment-form`, `ui-article-main__textarea`, `ui-article-main__submit` | Implementado / Conviven | The public component provides a specific semantic comment form with visible labels and accessible help text. It is not a general form system. | Medium/high | Reusable and accessible comment-entry form independent from article-main. | Comparative demo and article-main adoption contract. | Keep the existing article form unchanged until visual and semantic equivalence is approved. |
| `ui-related-list` | `ui-article-sidebar__list`, `ui-article-related` | Experimental en demo | Compact related links map well; related-card grids remain a separate pattern. | Medium/high | Reusable compact related-content lists. | Comparative demo against `ui-article-sidebar__list`. | Do not replace card grids or media-heavy lists. |
| `ui-trending-list` | `ui-sidebar__trending-list` | Implementado / Experimental en demo | The public component now covers compact linked content with optional thumbnail and metadata. It remains distinct from `ui-related-list` and `ui-post-card`. | Medium | Reusable trending/editorial recommendation lists outside the composed sidebar. | Comparative demo and explicit sidebar adoption contract. | Validate image sizing, density, and metadata rhythm before changing `ui-sidebar`. |
| `ui-social-links` | `ui-article-sidebar__social`, `ui-footer__socials`, `ui-footer-editorial__social`, `ui-author-card__links` | Implementado / Experimental en demo | The public component now provides semantic `ul > li > a` markup, accessible icon-only links, and compact/boxed treatments without an icon dependency. | Medium | Shared accessible social/contact link groups across new compositions. | Comparative demos on light, dark, narrow, and footer contexts. | Do not migrate original social zones until contextual color and spacing are visually approved. |
| `ui-callout` | `ui-article-main__principle`, `ui-sidebar__newsletter`, `ui-article-main__quote` | Conviven / No migrar | It is semantically for notes/context, not quotes, newsletters, or numbered principles. | High if forced | Useful for technical/editorial notes as a separate pattern. | None for current coexistence. | Do not migrate these originals to `ui-callout`; keep it independent. |
| `ui-table` | Future article/docs tabular content | Conviven | It adds semantic table styling where no original equivalent exists. | Low | Better technical/documentation content support. | None. | Use inside content areas when needed; no original migration required. |
| `ui-code-block` | Future article/docs code content | Conviven | It adds code/command display where no original equivalent exists. | Low | Better technical content support without JavaScript. | None. | Use inside content areas when needed; no original migration required. |
| `ui-toc` | `ui-article-sidebar`, docs sidebar navigation | Conviven / Requiere contrato futuro | It can live near sidebar compositions, but should not replace full sidebars or implement scrollspy. | Medium | Reusable table of contents for long content. | Sidebar integration guidance if adopted. | Define how it sits inside or beside editorial sidebars before using it as an official sidebar pattern. |

## Ready For Visual Experimentation

These primitives can be tested next to original components in demos without changing original component contracts:

- `ui-section-header`
- `ui-eyebrow`
- `ui-meta-list`
- `ui-tag-list`
- `ui-pullquote`
- `ui-newsletter`
- `ui-author-card`
- `ui-byline`
- `ui-comment`
- `ui-comment-form`
- `ui-related-list`
- `ui-trending-list`
- `ui-social-links`

Experiments should happen in demo markup first. A successful demo does not automatically approve migration.

## Must Remain Independent

These components should remain independent and should not be used as replacements for original editorial compositions:

- `ui-callout`
- `ui-table`
- `ui-code-block`
- `ui-toc`

`ui-callout` is especially important: it must not absorb quotes, newsletter blocks, or article principles just because they are visually emphasized blocks.

## Documented Compositions And Boundaries

P4 intentionally avoids creating components where a documented composition is sufficient:

- SayUI does not include `ui-category-list` in v1. Flat vertical categories with counts use `ui-tag-list`, `ui-tag-list--stacked`, and `ui-tag-list--with-count`.
- `ui-sidebar__categories` remains part of the current `ui-sidebar` contract and is not migrated automatically.
- SayUI does not include `ui-comment-list` in v1. Comment groups use a semantic `section`, an external heading or `ui-section-header`, and multiple `article.ui-comment` elements.
- A future `ui-comment-list` would require additional needs such as official list spacing, an empty state, a divided variant, or formal integration with a comment form.
- SayUI does not include a general form system. `ui-comment-form` is specific to writing comments, while `ui-newsletter` retains its own subscription contract.
- Sidebar table-of-contents integration still requires a future adoption contract before `ui-toc` becomes part of an original sidebar composition.

## Migration Rule

No primitive should replace an original component pattern directly.

The required order is:

1. Test the primitive visually in a demo.
2. Document the equivalence and limitations.
3. Approve the migration contract.
4. Update one low-risk pattern first.
5. Verify demos and compiled CSS.

Until those steps happen, original patterns and modern primitives coexist.

## P4 Closure Status

P4 is closed for implementation and public contracts.

The modern primitives completed through P4 are implemented, documented, included in the complete Sass bundle, and represented in the reusable-components demo. Their existence does not make original SayUI components legacy. Original components remain public compositions with valid current contracts.

Real migrations remain blocked until all of the following happen:

1. A comparative demo presents the primitive beside the original pattern.
2. Visual and responsive equivalence is reviewed and approved.
3. Semantic and accessibility differences are documented.
4. A specific adoption contract defines compatibility and migration scope.

The recommended next phase is P5: comparative demos, visual validation, and controlled adoption experiments. P5 should not continue automatic extraction or mass migration.

The official P5.1 comparison inventory, evaluation criteria, allowed results, exclusions, and execution order are documented in [P5 Comparative Evaluation Plan](p5-comparison-plan.md).
