# Architecture

SayUI is a visual UI library. Consumer projects import the compiled CSS bundle and use the `ui-*` classes in their HTML.

```html
<link rel="stylesheet" href="dist/css/sayui.css">
```

SayUI is not Astro, React, Next.js, Vue, Angular, Tailwind UI, or a routing system. A future blog or documentation site can consume SayUI from another project, but SayUI itself remains HTML + SCSS + compiled CSS.

## Source Areas

### Foundations

Path: `src/styles/foundations/`

Purpose: shared design primitives.

Current files:

- `_variables.scss`: CSS custom properties and color tokens.
- `_typography.scss`: Sass font size, line height, and weight variables.
- `_mixins.scss`: shared Sass mixins.

### Layouts

Path: `src/layouts/`

Purpose: page roots and structural containers. Not every layout is a complete page. Some layouts exist to keep component composition stable.

Current layouts:

- `ui-page`: root for the main page demo.
- `ui-editorial-page`: root for the secondary/editorial page demo.
- `ui-layout`: structural content wrapper.
- `ui-main`: main content column.
- `ui-editorial-grid`: internal article + sidebar composition. It can define selectors such as `.ui-editorial-page__layout`; this is intentional.

### Components

Path: `src/components/`

Purpose: reusable visual blocks and component partials. Some components are standalone, while others are part of a larger ecosystem.

Examples:

- `ui-topbar`
- `ui-banner`
- `ui-post-card`
- `ui-sidebar`
- `ui-footer`
- `ui-footer-editorial`

### Article Components

Path: `src/components/article/`

Purpose: article-specific blocks used by editorial pages.

Current article components:

- `ui-article-hero`
- `ui-article-main`
- `ui-article-sidebar`
- `ui-article-related`

### Demos

Path: `src/demo/`

Purpose: visual testing and living documentation. Demos are not production pages and do not represent a routing system.

### Distribution

Path: `dist/css/`

Purpose: compiled CSS for consumers.

Current bundle files:

- `sayui.css`
- `sayui.min.css`

## Bundle Rule

`src/styles/main.scss` is the complete SayUI bundle entry. Imports must not be removed only because they appear redundant. Each import should be checked against components, layouts, and demos before changes are made.

