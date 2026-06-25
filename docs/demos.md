# Demos

The `src/demo/` directory is living documentation and a visual testing area. It is not an application, router, or production layer.

## Published Root Demo

File: `index.html`

Purpose: published GitHub Pages entry with the editorial demo and navigation to the blog and reusable-component demos.

When to use:

- Opening the published project.
- Reviewing the complete editorial composition.
- Navigating to `src/demo/blog-index.html` or `src/demo/ui-components.html`.

Dependencies:

- `dist/css/sayui.css`
- `src/demo/demo.css`
- `src/demo/styles/demo.css`
- Manrope font
- Material Symbols

Accessibility notes:

- Demo links use real relative destinations or representative external schemes such as `mailto:`.
- Icon-only controls should keep accessible labels.

## Blog Demo Index

File: `src/demo/blog-index.html`

Purpose: navigation hub for the six implemented consumer blog demos.

Includes links to:

- `blog-home.html`
- `blog-article.html`
- `blog-category.html`
- `blog-author.html`
- `blog-search.html`
- `blog-404.html`
- `ui-components.html`
- `ui-original-components.html`
- root `index.html`

## Main Page Demo

File: `src/demo/ui-page.html`

Purpose: historical markup demo of the complete main page composition.

Includes:

- `ui-page`
- `ui-topbar`
- `ui-layout`
- `ui-banner`
- `ui-main`
- `ui-main-header`
- `ui-post-grid`
- `ui-post-card`
- `ui-sidebar`
- `ui-footer`

When to use:

- Checking the full main page composition.
- Testing interactions between banner, main grid, sidebar, and footer.

## Editorial Page Demo

File: `src/demo/ui-editorial.html`

Purpose: historical markup demo of the secondary/editorial article composition.

Includes:

- `ui-editorial-topbar`
- `ui-editorial-page`
- `ui-article-hero`
- `ui-editorial-page__layout`
- `ui-article-main`
- `ui-article-sidebar`
- `ui-article-related`
- `ui-footer-editorial`

When to use:

- Checking the full article composition.
- Testing article + sidebar layout.
- Testing the editorial footer.

## Reusable Components Demo

File: `src/demo/ui-components.html`

Purpose: complete visual gallery for reusable primitives, editorial components, technical/content components, and P5 comparative examples.

Includes:

- `ui-tag-list`
- `ui-meta-list`
- `ui-section-header`
- `ui-eyebrow`
- `ui-callout`
- `ui-pullquote`
- `ui-newsletter`
- `ui-author-card`
- `ui-related-list`
- `ui-byline`
- `ui-comment`
- `ui-comment-form`
- `ui-trending-list`
- `ui-social-links`
- `ui-table`
- `ui-code-block`
- `ui-toc`

When to use:

- Checking reusable technical/editorial components in isolation.
- Reviewing accessibility-oriented markup examples.
- Copying small component snippets without opening full page demos.
- Reviewing approved original-versus-primitive comparisons.

## Blog Consumer Demos

The blog demos validate that existing SayUI primitives can compose complete consumer pages without introducing generic cards, grids, search systems, profile systems, error components, or empty-state components.

| File | Role |
| --- | --- |
| `src/demo/blog-home.html` | Editorial home with featured and recent content. |
| `src/demo/blog-article.html` | Long-form article with technical content, sidebar, comments, and comment form. |
| `src/demo/blog-category.html` | Static category/taxonomy page. |
| `src/demo/blog-author.html` | Author page using `ui-author-card` as an independent block. |
| `src/demo/blog-search.html` | Static search-results composition with a consumer-owned GET form. |
| `src/demo/blog-404.html` | Consumer-owned not-found composition. |

All six pages use local relative navigation suitable for GitHub Pages. They remain demos rather than production routes or application behavior.

## Original Components Demo

File: `src/demo/ui-original-components.html`

Purpose: visual gallery for SayUI's original components as reusable library pieces. These components are not legacy and should not only be understood through the complete page demos.

Includes:

- `ui-topbar`
- `ui-editorial-topbar`
- `ui-banner`
- `ui-main-header`
- `ui-post-grid`
- `ui-post-card`
- `ui-sidebar`
- `ui-footer`
- `ui-footer-editorial`
- `ui-article-hero`
- representative `ui-article-main` patterns
- `ui-article-sidebar`
- `ui-article-related`

When to use:

- Reviewing original components in isolation or minimal context.
- Confirming that original editorial components remain first-class public components.
- Copying focused examples without opening a complete page composition.

## Demo Rules

- Demos can contain complete compositions.
- Demos can duplicate component markup for easier preview.
- Demos are allowed to be broader than isolated component snippets.
- Do not treat demo files as production routes.
- Do not remove demos unless there is a proven technical issue.

## Form Integration Placeholders

Form `action` values such as `/comments`, `/subscribe`, and `/newsletter/subscribe` are integration placeholders. GitHub Pages does not provide the backend required to process them.

Consumers must replace these values with their own server, static-form provider, or external service endpoint. SayUI supplies visual and semantic form contracts only; it does not supply submission, validation, authentication, success/error state, or persistence behavior.
