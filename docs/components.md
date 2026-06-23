# Component Contracts

This file is the index for SayUI component contracts. Detailed contracts live in `docs/components/`.

SayUI components have different roles. Some are primitives, some are composed editorial components, and some are content components. Original components are not obsolete: they are first-class public parts of the library. Newer primitives do not automatically replace older composed components.

Do not migrate, rename, split, or remove a component without an approved contract.

## Taxonomy

- Foundations: tokens, mixins, typography, and global design inputs.
- Layouts: structural page and content containers.
- Primitives: small reusable UI contracts such as tags, metadata, tables, code blocks, and TOCs.
- Composed components: larger public components made from several internal zones.
- Editorial components: article and publishing-oriented components.
- Technical/content components: reusable content blocks for documentation and technical writing.
- Demos: living documentation and visual verification, not production routes.

## Component Index

| Component | Category | Public/internal | Role | Recommendation |
| --- | --- | --- | --- | --- |
| [`ui-tag-list`](components/ui-tag-list.md) | Primitive | Public | Tags, topics, categories, and simple filters. | Use for new generic tag lists; do not auto-migrate older tags. |
| [`ui-meta-list`](components/ui-meta-list.md) | Primitive | Public | Compact metadata and label/value metadata. | Use for new generic metadata; do not auto-migrate older metadata. |
| [`ui-table`](components/ui-table.md) | Primitive | Public | Semantic tabular data. | Use for real tables only. |
| [`ui-code-block`](components/ui-code-block.md) | Primitive | Public | Code, commands, and configuration snippets. | Use for code blocks, not inline code. |
| [`ui-toc`](components/ui-toc.md) | Primitive | Public | Static in-page navigation. | Keep independent from sidebars. |
| [`ui-section-header`](components/ui-section-header.md) | Primitive | Public | Reusable section headings for content groups and editorial blocks. | Keep independent; do not auto-migrate older headings. |
| [`ui-eyebrow`](components/ui-eyebrow.md) | Primitive | Public | Single editorial label or category marker. | Keep independent; do not replace tags, metadata, or headings. |
| [`ui-callout`](components/ui-callout.md) | Technical/content component | Public | Notes, tips, warnings, and contextual messages. | Do not use as quote, newsletter, or card replacement. |
| [`ui-topbar`](components/ui-topbar.md) | Composed component | Public | Main navigation. | Keep as a composed public component. |
| [`ui-editorial-topbar`](components/ui-editorial-topbar.md) | Composed component | Public | Editorial navigation. | Keep as a composed public component. |
| [`ui-banner`](components/ui-banner.md) | Composed component | Public | Featured story block. | Keep public; can adopt primitives later by contract. |
| [`ui-main-header`](components/ui-main-header.md) | Subcomponent / composed-area part | Public within `ui-main` | Header row and filters. | Document as part of the `ui-main` ecosystem. |
| [`ui-post-grid`](components/ui-post-grid.md) | Subcomponent / layout helper | Public within `ui-main` | Post grid and load-more area. | Keep. |
| [`ui-post-card`](components/ui-post-card.md) | Composed component | Public | Article/post preview card. | Keep public. |
| [`ui-sidebar`](components/ui-sidebar.md) | Composed component | Public | Trending links, categories, and newsletter. | Do not split without approved contracts. |
| [`ui-footer`](components/ui-footer.md) | Composed component | Public | Main footer. | Keep. |
| [`ui-footer-editorial`](components/ui-footer-editorial.md) | Composed component | Public | Editorial footer. | Keep. |
| [`ui-article-main`](components/ui-article-main.md) | Editorial component | Public | Long-form article body with prose, quote, figure, tags, and comments. | Keep public; extract smaller patterns only with approved contracts. |
| [`ui-article-sidebar`](components/ui-article-sidebar.md) | Editorial composed component | Public | Article sidebar with author block, social links, related stories, and tag cloud. | Keep public; do not split without approved contracts. |

## Notes

- Original components remain core SayUI components.
- Primitives and composed components can coexist.
- Component-specific contracts are documented in separate files to keep this index readable.
- `src/styles/main.scss` remains the complete SayUI bundle and is not affected by documentation structure.

