# Component Coexistence Matrix

This document defines the official coexistence policy between SayUI's original public components and newer reusable primitives.

Modern primitives do not make original components legacy. Original components remain public compositions unless a future migration is designed, documented, tested in demos, and explicitly approved.

## Official Status Criteria

| Status | Meaning |
| --- | --- |
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
| `ui-tag-list` | `ui-article-main__tags`, `ui-article-sidebar__tags`, `ui-sidebar__categories` | Migracion futura posible | Article tags map well; sidebar categories with counts need more care. | Medium | Shared tag/category contract and accessible interactive states. | Decision for counted categories. | Test article tags first, then evaluate sidebar categories separately. |
| `ui-pullquote` | `ui-article-main__quote` | Experimental en demo | It directly matches editorial quote semantics but should preserve the original visual rhythm before migration. | Medium | A reusable quote component for articles and editorial pages. | Stable `--editorial` behavior. | Validate `blockquote`, cite, and decorative mark handling against the original article quote. |
| `ui-newsletter` | `ui-sidebar__newsletter` | Experimental en demo | It represents the same signup block, but the sidebar version is integrated into a larger composition. | Medium | Reusable newsletter block outside sidebars. | Form/accessibility contract stays stable. | Validate `--strong` against the dark sidebar pattern and decide whether sidebar keeps its internal markup. |
| `ui-author-card` | `ui-article-sidebar__author`, `ui-banner__author`, comment author blocks | Experimental en demo | The article-sidebar author block maps well; banner and comments are different patterns. | Medium/high | Reusable author presentation for sidebars and editorial contexts. | Future `ui-byline` and `ui-comment` contracts. | Only consider article-sidebar-style author cards; do not migrate banner bylines or comments yet. |
| `ui-related-list` | `ui-article-sidebar__list`, `ui-sidebar__trending-list`, `ui-article-related` | Experimental en demo | Compact related links map well; trending widgets and related-card grids are separate patterns. | Medium/high | Reusable compact related-content lists. | Future trending/media list contract if needed. | Test against `ui-article-sidebar__list`; do not replace card grids or media-heavy lists. |
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
- `ui-related-list`

Experiments should happen in demo markup first. A successful demo does not automatically approve migration.

## Must Remain Independent

These components should remain independent and should not be used as replacements for original editorial compositions:

- `ui-callout`
- `ui-table`
- `ui-code-block`
- `ui-toc`

`ui-callout` is especially important: it must not absorb quotes, newsletter blocks, or article principles just because they are visually emphasized blocks.

## Require Future Contracts

Some overlaps point to missing future contracts rather than direct migration targets:

- `ui-byline`: needed before touching `ui-banner__author`.
- `ui-comment`: needed before touching comment author blocks.
- `ui-trending-list`: needed before touching `ui-sidebar__trending-list`.
- Counted category pattern: needed before migrating `ui-sidebar__categories` fully to `ui-tag-list`.
- Sidebar table-of-contents integration: needed before making `ui-toc` an official part of `ui-article-sidebar`.

## Migration Rule

No primitive should replace an original component pattern directly.

The required order is:

1. Test the primitive visually in a demo.
2. Document the equivalence and limitations.
3. Approve the migration contract.
4. Update one low-risk pattern first.
5. Verify demos and compiled CSS.

Until those steps happen, originals and primitives coexist.
