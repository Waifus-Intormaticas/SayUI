# Layout Contracts

Layouts define page roots and structural composition. They are not necessarily standalone pages.

## ui-page

Purpose: root wrapper for the main page composition.

When to use: use as the outer container for the primary editorial/listing page.

HTML minimum:

```html
<main class="ui-page"></main>
```

Required classes:

- `ui-page`

Optional classes:

- None directly. It usually contains `ui-topbar`, `ui-layout`, and `ui-footer`.

Dependencies:

- `src/layouts/ui-page/ui-page.scss`

Responsive:

- Provides min-height and horizontal overflow protection.

Accessibility:

- Prefer `<main class="ui-page">` when it is the main content region.

Example:

```html
<main class="ui-page">
  <header class="ui-topbar"></header>
  <div class="ui-layout"></div>
  <footer class="ui-footer"></footer>
</main>
```

## ui-editorial-page

Purpose: root wrapper for the secondary/editorial article page.

When to use: use as the main container for article pages.

HTML minimum:

```html
<main class="ui-editorial-page"></main>
```

Required classes:

- `ui-editorial-page`

Optional classes:

- `ui-editorial-page__layout`

Dependencies:

- `src/layouts/ui-editorial-page/ui-editorial-page.scss`
- `src/layouts/ui-editorial-grid/ui-editorial-grid.scss`

Responsive:

- Page root is simple; grid behavior is handled by `ui-editorial-page__layout`.

Accessibility:

- Prefer `<main class="ui-editorial-page">`.

Example:

```html
<main class="ui-editorial-page">
  <section class="ui-article-hero"></section>
  <div class="ui-editorial-page__layout"></div>
</main>
```

## ui-layout

Purpose: structural wrapper for the main page content.

When to use: use inside `ui-page` to constrain width and place main content beside the sidebar.

HTML minimum:

```html
<div class="ui-layout">
  <div class="ui-layout__content"></div>
</div>
```

Required classes:

- `ui-layout`
- `ui-layout__content`

Optional classes:

- None.

Dependencies:

- `src/layouts/ui-layout/ui-layout.scss`

Responsive:

- `ui-layout__content` stacks on small screens and becomes a row from 1024px.

Accessibility:

- This is structural. Use semantic children such as `<main>` and `<aside>`.

Example:

```html
<div class="ui-layout">
  <section class="ui-banner"></section>
  <div class="ui-layout__content">
    <main class="ui-main"></main>
    <aside class="ui-sidebar"></aside>
  </div>
</div>
```

## ui-main

Purpose: main content column for post listings.

When to use: use inside `ui-layout__content`.

HTML minimum:

```html
<main class="ui-main"></main>
```

Required classes:

- `ui-main`

Optional classes:

- `ui-main__header-row`
- `ui-main__heading`
- `ui-main__filters`
- `ui-main__filter-button`
- `ui-main__grid`
- `ui-main__more`
- `ui-main__more-button`

Dependencies:

- `src/layouts/ui-main/ui-main.scss`
- `src/components/ui-main-header/ui-main-header.scss`
- `src/components/ui-post-grid/ui-post-grid.scss`

Responsive:

- Width becomes 66.666667% from 1024px when paired with `ui-sidebar`.

Accessibility:

- Prefer `<main class="ui-main">`.
- Filter buttons need a clear behavior in consumer projects.

Example:

```html
<main class="ui-main">
  <div class="ui-main__header-row">
    <h3 class="ui-main__heading">Latest Stories</h3>
  </div>
  <div class="ui-main__grid"></div>
</main>
```

## ui-editorial-grid

Purpose: internal article + sidebar grid for editorial pages.

When to use: use inside `ui-editorial-page` when composing `ui-article-main` and `ui-article-sidebar`.

HTML minimum:

```html
<div class="ui-editorial-page__layout"></div>
```

Required classes:

- `ui-editorial-page__layout`

Optional classes:

- None directly.

Dependencies:

- `src/layouts/ui-editorial-grid/ui-editorial-grid.scss`
- `ui-article-main`
- `ui-article-sidebar`

Responsive:

- One column by default.
- Twelve-column grid from 1024px.

Accessibility:

- Use semantic children: `<article>` for the main article and `<aside>` for the sidebar.

Example:

```html
<div class="ui-editorial-page__layout">
  <article class="ui-article-main"></article>
  <aside class="ui-article-sidebar"></aside>
</div>
```

Note: The file is named `ui-editorial-grid`, but the public selector is `.ui-editorial-page__layout`. This is valid in SayUI.

