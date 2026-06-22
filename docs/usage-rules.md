# Usage Rules

These rules protect SayUI's framework-agnostic architecture.

## Do

* Import the compiled CSS bundle in consumer projects.
* Use `ui-*` classes as the public HTML contract.
* Keep SayUI as HTML + SCSS + compiled CSS.
* Use `src/demo/` as visual testing and living documentation.
* Keep `src/styles/main.scss` as the complete bundle entry.
* Verify components, layouts, and demos before changing imports.
* Add documentation before broad API changes.
* Improve accessibility in component contracts.

## Do Not

* Do not convert SayUI to Astro, React, Next.js, Vue, Angular, or another framework.
* Do not add Vite, Webpack, Rollup, Parcel, Tailwind, or equivalent tools unless explicitly requested.
* Do not treat demo files as production pages.
* Do not remove layouts or demos just because they look similar.
* Do not remove `main.scss` imports only because they appear duplicated.
* Do not assume every component is fully independent.

## Main SCSS Rule

`src/styles/main.scss` generates the full library CSS bundle.

Before touching imports:

1. Check `src/styles/foundations/`.
2. Check `src/layouts/`.
3. Check `src/components/`.
4. Check `src/components/article/`.
5. Check the demos in `src/demo/`.
6. Confirm which selectors are expected in `dist/css/sayui.css`.

## Bundle Completeness Rule

`src/styles/main.scss` is allowed to include styles that are only visible in specific demos or page compositions.

Do not remove an import unless:

1. The SCSS file no longer exists.
2. No documented component depends on it.
3. No documented layout depends on it.
4. No demo depends on it.
5. The selector is not part of the public contract.
6. The change has been explicitly approved.

The goal of `main.scss` is to generate the complete SayUI bundle, not the smallest possible CSS file.

## Layout Rule

Layouts can be structural wrappers, not only full pages.

Some layout files exist only to preserve component composition, spacing, alignment, or responsive behavior.

Do not remove, merge, rename, or simplify layouts only because:

* They do not expose a standalone block class.
* They appear small.
* They wrap other components.
* They seem redundant at first glance.

Structural layouts are considered part of the architecture.

## Component Contract Rule

Each component should document:

* Purpose
* When to use it
* HTML minimum
* Required classes
* Optional classes
* Dependencies
* Responsive behavior
* Accessibility notes
* Minimal example

## Public API Rule

The public API of SayUI is:

* Compiled CSS
* Documented HTML structure
* Documented `ui-*` classes

Internal implementation details may evolve, but documented contracts should remain stable whenever possible.

Before changing a documented contract:

1. Verify existing demos.
2. Verify existing layouts.
3. Verify related components.
4. Update documentation.

## Demos Rule

The demos are intentionally broader than isolated components.

### `index.html`

General component demo.

Used to preview individual components and smaller compositions.

### `ui-page.html`

Complete main page demo.

Used to preview the full primary page composition.

### `ui-editorial.html`

Complete secondary/editorial page demo.

Used to preview the full editorial/article composition.

The demos are allowed to contain repeated markup because they are visual references and living documentation.

They are not production pages.

## Accessibility Rule

When documenting or updating components:

* Icon-only buttons need accessible names.
* Images need correct `alt` treatment.
* Forms need labels or accessible names.
* Interactive icons should be links or buttons.
* Placeholder links in demos should become real links in consumer projects.
* Focus-visible states should remain accessible.
* Decorative content should be hidden from assistive technologies when appropriate.

## Framework-Agnostic Rule

SayUI must remain framework agnostic.

Consumer projects may use:

* Astro
* React
* Next.js
* Vue
* Eleventy
* Jekyll
* HTML-only environments

However, SayUI itself should not depend on those technologies.

Framework-specific examples belong in consumer projects or documentation examples, not in the core library.

## Documentation First Rule

Before introducing:

* New tokens
* New components
* New layouts
* New variants
* Breaking changes

Documentation should be updated first or alongside the implementation.

Documentation is considered part of the public contract.
