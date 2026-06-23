# Demos

The `src/demo/` directory is living documentation and a visual testing area. It is not an application, router, or production layer.

## Demo Index

File: `src/demo/index.html`

Purpose: general component demo. It can be used to test individual components or small combinations without searching through every component folder.

When to use:

- Previewing a component quickly.
- Copying markup while building a consumer project.
- Testing small visual changes.

Dependencies:

- `../../dist/css/sayui.css`
- `demo.css`
- Manrope font
- Material Symbols

Accessibility notes:

- Placeholder links may need real `href` values in consumer projects.
- Icon-only controls should keep accessible labels.

## Main Page Demo

File: `src/demo/ui-page.html`

Purpose: complete visual demo of the main page layout.

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

Purpose: complete visual demo of the secondary/editorial article layout.

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

## P1 Components Demo

File: `src/demo/ui-components.html`

Purpose: visual gallery for reusable technical/content components and primitives.

Includes:

- `ui-tag-list`
- `ui-callout`
- `ui-table`
- `ui-code-block`
- `ui-toc`
- `ui-meta-list`

When to use:

- Checking reusable technical/editorial components in isolation.
- Reviewing accessibility-oriented markup examples.
- Copying small component snippets without opening full page demos.

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
