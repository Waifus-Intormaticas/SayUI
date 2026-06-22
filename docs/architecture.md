# Architecture

SayUI is a framework-agnostic UI library built with HTML, SCSS, and compiled CSS.

Consumer projects import the compiled CSS bundle and use documented `ui-*` classes in their own HTML:

```html
<link rel="stylesheet" href="dist/css/sayui.css">
```

SayUI is meant to provide visual components, layout primitives, editorial patterns, and reusable technical-content components without owning the consumer application's routing, rendering, data layer, or framework.

## What SayUI Is

- A small UI library.
- A set of documented HTML contracts.
- A Sass source library compiled into a CSS bundle.
- A framework-agnostic design layer for editorial and technical interfaces.
- A project that can be consumed by HTML-only sites, static-site generators, documentation projects, or application frameworks.

## What SayUI Is Not

SayUI is not:

- Astro
- React
- Next.js
- Vue
- Angular
- Tailwind UI
- A router
- A CMS
- A blog engine
- A documentation generator
- A JavaScript behavior layer

A future blog or documentation site can consume SayUI from another project, but SayUI itself remains HTML + SCSS + compiled CSS.

## Source Areas

### Foundations

Path: `src/styles/foundations/`

Purpose: shared design primitives used by components and layouts.

Current files:

- `_variables.scss`: CSS custom properties for colors, contextual surfaces, gradients, and visual effects.
- `_typography.scss`: Sass font size, line height, and font weight variables.
- `_mixins.scss`: shared Sass mixins, currently including the `text` mixin.
- `_spacing.scss`: Sass spacing scale for new and gradually migrated components.
- `_radius.scss`: Sass radius scale for corners and pill shapes.
- `_breakpoints.scss`: Sass breakpoint variables and responsive mixins.
- `_shadows.scss`: Sass shadow tokens for new and low-risk migrated components.

Foundations are not a separate build target. They are included through `src/styles/main.scss` and imported directly by component SCSS when needed.

### Layouts

Path: `src/layouts/`

Purpose: page roots and structural containers. Not every layout is a complete page. Some layouts exist to keep component composition, spacing, alignment, or responsive behavior stable.

Current layouts:

- `ui-page`: root for the main page demo.
- `ui-editorial-page`: root for the secondary/editorial page demo.
- `ui-layout`: structural content wrapper.
- `ui-main`: main content column.
- `ui-editorial-grid`: internal article + sidebar composition. It can define selectors such as `.ui-editorial-page__layout`; this is intentional.

Layouts are part of the public architecture and should not be removed or merged only because they appear small or similar.

### Components

Path: `src/components/`

Purpose: reusable visual blocks and component partials. Some components are standalone; others are part of a larger page ecosystem.

Original editorial components include:

- `ui-topbar`
- `ui-editorial-topbar`
- `ui-banner`
- `ui-main-header`
- `ui-post-grid`
- `ui-post-card`
- `ui-sidebar`
- `ui-footer`
- `ui-footer-editorial`

Article-specific components live in:

```text
src/components/article/
```

Current article components:

- `ui-article-hero`
- `ui-article-main`
- `ui-article-sidebar`
- `ui-article-related`

Article components are intentionally scoped to editorial article pages. They should not be treated as mistakes just because some patterns overlap with newer reusable components.

## P1 Reusable Components

After the P1 phase, SayUI also includes reusable technical/editorial components that are not article-specific:

- `ui-tag-list`: tags, categories, topic lists, and simple filters.
- `ui-callout`: editorial or technical notes, tips, warnings, and contextual messages.
- `ui-table`: semantic tabular data with responsive overflow support.
- `ui-code-block`: code, commands, configuration, and terminal-style snippets without JavaScript or syntax highlighting.
- `ui-toc`: static table of contents for internal page sections, without scrollspy.

These components are designed to work in articles, documentation, guides, demos, or consumer projects without depending on a framework or a specific page layout.

## Demos

Path: `src/demo/`

Purpose: visual testing and living documentation. Demos are not production pages and do not represent a routing system.

Current demo roles:

- `index.html`: general component demo.
- `ui-page.html`: complete main page composition.
- `ui-editorial.html`: complete editorial/article page composition.

The demos are allowed to contain repeated markup because they are visual references and a practical way to inspect component compositions.

## Distribution

Path: `dist/css/`

Purpose: compiled CSS for consumers.

Current bundle files:

- `sayui.css`
- `sayui.min.css`

The package metadata points consumers to:

```json
"style": "dist/css/sayui.css"
```

## Build

SayUI uses Sass as its build tool.

Current commands:

```bash
npm run build
npm run watch
npm run build:min
```

Do not add app bundlers or framework build systems to SayUI unless that change is explicitly approved.

## Main SCSS Bundle Rule

`src/styles/main.scss` is the complete SayUI bundle entry.

Its purpose is to generate a full CSS bundle for the library, not a minimal CSS file. Imports must not be removed only because they appear redundant.

Before changing imports, check:

- `src/styles/foundations/`
- `src/layouts/`
- `src/components/`
- `src/components/article/`
- `src/demo/`
- documented public classes
- expected selectors in `dist/css/sayui.css`

## Framework-Agnostic Philosophy

SayUI should remain independent from any consumer technology.

Consumer projects may use:

- HTML-only workflows
- static-site generators
- documentation generators
- Astro
- React
- Next.js
- Vue
- Eleventy
- Jekyll

Those technologies belong in consumer projects, not inside SayUI's core library.

SayUI's public API is:

- compiled CSS
- documented HTML structure
- documented `ui-*` classes

## Current Maturity

SayUI is currently best described as **advanced alpha / early internal beta**.

The project has:

- a clear framework-agnostic architecture
- a complete Sass/CSS bundle workflow
- foundational tokens
- original editorial components
- reusable P1 technical/editorial components
- documentation for component and layout contracts

Before treating SayUI as a public beta, the next consolidation work should focus on demos for the P1 components, documentation organization, and gradual token migration in older components.
