# SayUI

> A minimal, modular, framework-agnostic UI component library built with HTML, SCSS, and compiled CSS.

![Version](https://img.shields.io/badge/version-1.0.0-red)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-blue)

## Overview

SayUI is a lightweight visual component library for editorial pages, blogs, and content-driven interfaces.

It is intentionally simple:

- HTML snippets for component structure.
- SCSS source files for development.
- A single compiled CSS file for consumers.
- No framework runtime.
- No routing or content system.

SayUI can be consumed by any project that can load CSS and write HTML.

## Installation

Use the compiled CSS file in your HTML:

```html
<link rel="stylesheet" href="dist/css/sayui.css">
```

For minified production CSS:

```html
<link rel="stylesheet" href="dist/css/sayui.min.css">
```

Consumer projects should import the compiled CSS and use the documented `ui-*` classes in their markup.

## Development

SayUI uses Sass as its official compiler.

Build the standard CSS file:

```bash
npm run build
```

Watch SCSS changes:

```bash
npm run watch
```

Build the minified CSS file:

```bash
npm run build:min
```

Equivalent Sass commands:

```bash
sass src/styles/main.scss dist/css/sayui.css
sass src/styles/main.scss dist/css/sayui.css --watch
sass src/styles/main.scss dist/css/sayui.min.css --style=compressed
```

## Project Structure

```txt
src/
  components/
    banner/
    editorial-topbar/
    ui-footer/
    ui-footer-editorial/
    ui-main-header/
    ui-post-card/
    ui-post-grid/
    ui-sidebar/
    ui-topbar/
    article/
      ui-article-hero/
      ui-article-main/
      ui-article-related/
      ui-article-sidebar/

  layouts/
    ui-page/
    ui-layout/
    ui-main/
    ui-editorial-page/
    ui-editorial-grid/

  styles/
    foundations/
      _variables.scss
      _typography.scss
      _mixins.scss
    main.scss

  demo/
    index.html
    ui-page.html
    ui-editorial.html
    demo.css
    img/

dist/
  css/
    sayui.css
    sayui.min.css
```

## Architecture

SayUI follows a small separation of concerns:

- **Foundations**: design tokens, typography scales, and mixins.
- **Layouts**: structural composition patterns.
- **Components**: reusable visual blocks.
- **Demos**: examples used to preview and test compositions.
- **Dist**: compiled CSS for consumers.

## Components

Current component groups include:

- Topbars: `ui-topbar`, `ui-editorial-topbar`
- Editorial hero: `ui-banner`, `ui-article-hero`
- Post listing: `ui-post-card`, `ui-post-grid`
- Sidebars: `ui-sidebar`, `ui-article-sidebar`
- Article body: `ui-article-main`
- Related content: `ui-article-related`
- Footers: `ui-footer`, `ui-footer-editorial`

## Layouts

SayUI includes two intentional demo/layout families:

- `ui-page`: general editorial listing page.
- `ui-editorial-page`: article-focused editorial page.

These layouts are examples and composition templates. Consumer projects may use one layout, combine components, or adapt the markup while keeping the `ui-*` class contracts.

## Demo

Open the demo file directly in a browser:

```txt
src/demo/index.html
```

The demo imports:

```html
<link rel="stylesheet" href="../../dist/css/sayui.css">
```

## Usage Guidelines

- Keep SayUI framework-agnostic.
- Use the compiled CSS in consumer projects.
- Keep component class names under the `ui-*` namespace.
- Extend with custom classes in consumer projects instead of editing compiled CSS.
- Keep Sass changes organized under foundations, layouts, or components.

## License

MIT

## Author

Jonathan Ventura

GitHub: [JVenturaDev](https://github.com/JVenturaDev)
