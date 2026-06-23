# Component Contracts

This file documents non-article components in `src/components/`.

## ui-topbar

Purpose: primary top navigation for the main page.

When to use: use at the top of `ui-page`.

HTML minimum:

```html
<header class="ui-topbar">
  <div class="ui-topbar__inner"></div>
</header>
```

Required classes:

- `ui-topbar`
- `ui-topbar__inner`

Optional classes:

- `ui-topbar__left`
- `ui-topbar__brand`
- `ui-topbar__logo`
- `ui-topbar__nav`
- `ui-topbar__link`
- `ui-topbar__actions`
- `ui-topbar__search-button`
- `ui-topbar__search-icon`
- `ui-topbar__subscribe-button`
- `ui-topbar__menu-button`
- `ui-topbar__menu-icon`
- `ui-topbar__mobile-nav`

Dependencies:

- Material Symbols for icons when used.
- `src/components/ui-topbar/ui-topbar.scss`

Responsive:

- Desktop nav is hidden at smaller sizes.
- Mobile nav is shown through the CSS focus pattern on the menu button.

Accessibility:

- Icon-only buttons need `aria-label`.
- Brand links should include an `href` in production markup.
- Menu behavior is CSS-only; consumer projects can enhance it with their own JavaScript if needed.

Example:

```html
<header class="ui-topbar">
  <div class="ui-topbar__inner">
    <a class="ui-topbar__brand" href="#">Brand</a>
  </div>
</header>
```

## ui-editorial-topbar

Purpose: compact editorial navigation for article pages.

When to use: use above `ui-editorial-page`.

HTML minimum:

```html
<header class="ui-editorial-topbar">
  <div class="ui-editorial-topbar__inner"></div>
</header>
```

Required classes:

- `ui-editorial-topbar`
- `ui-editorial-topbar__inner`

Optional classes:

- `ui-editorial-topbar__left`
- `ui-editorial-topbar__brand`
- `ui-editorial-topbar__nav`
- `ui-editorial-topbar__link`
- `ui-editorial-topbar__actions`
- `ui-editorial-topbar__search-button`
- `ui-editorial-topbar__subscribe-button`

Dependencies:

- Material Symbols for search icon.
- `src/components/editorial-topbar/ui-editorial-topbar.scss`

Responsive:

- Nav is hidden by default and shown from 768px.

Accessibility:

- Search button needs `aria-label`.
- Links need meaningful destinations.

Example:

```html
<header class="ui-editorial-topbar">
  <div class="ui-editorial-topbar__inner">
    <a class="ui-editorial-topbar__brand" href="#">Crimson Courier</a>
  </div>
</header>
```

## ui-banner

Purpose: featured story or hero block for the main page.

When to use: use near the top of `ui-layout`.

HTML minimum:

```html
<section class="ui-banner">
  <div class="ui-banner__wrapper"></div>
</section>
```

Required classes:

- `ui-banner`
- `ui-banner__wrapper`

Optional classes:

- `ui-banner__media`
- `ui-banner__image`
- `ui-banner__content`
- `ui-banner__eyebrow`
- `ui-banner__title`
- `ui-banner__description`
- `ui-banner__author`
- `ui-banner__author-image`
- `ui-banner__author-info`
- `ui-banner__author-name`
- `ui-banner__meta`
- `ui-banner__link`

Dependencies:

- An image if using media.
- Material Symbols if using the arrow icon.

Responsive:

- Stacked by default.
- Media and content sit side by side from 1024px.

Accessibility:

- Use descriptive `alt` text when the image is meaningful.
- If the image is decorative, use empty `alt`.
- `ui-banner__link` needs a real destination in consumer projects.

Example:

```html
<section class="ui-banner">
  <div class="ui-banner__wrapper">
    <div class="ui-banner__content">
      <span class="ui-banner__eyebrow">Featured</span>
      <h2 class="ui-banner__title">Featured title</h2>
    </div>
  </div>
</section>
```

## ui-main-header

Purpose: header row and filters for the `ui-main` ecosystem.

When to use: use inside `ui-main` above `ui-main__grid`.

HTML minimum:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>
</div>
```

Required classes:

- `ui-main__header-row`
- `ui-main__heading`

Optional classes:

- `ui-main__filters`
- `ui-main__filter-button`

Dependencies:

- `ui-main`

Responsive:

- No dedicated breakpoint.

Accessibility:

- If filter buttons change content, consumer projects should expose selected state with `aria-pressed` or another appropriate pattern.

Example:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>
  <div class="ui-main__filters">
    <button class="ui-main__filter-button">All</button>
  </div>
</div>
```

## ui-post-card

Purpose: article or post preview card.

When to use: use inside `ui-main__grid`, `ui-article-related__grid`, or another listing context.

HTML minimum:

```html
<article class="ui-post-card">
  <div class="ui-post-card__content"></div>
</article>
```

Required classes:

- `ui-post-card`
- `ui-post-card__content`

Optional classes:

- `ui-post-card__image-wrapper`
- `ui-post-card__image`
- `ui-post-card__eyebrow`
- `ui-post-card__title`
- `ui-post-card__description`
- `ui-post-card__meta`

Dependencies:

- Image only if media is used.

Responsive:

- Card sizing depends on its parent grid.

Accessibility:

- If the card is clickable, document whether the title link or full card link is used.
- Images need useful `alt` text when meaningful.

Example:

```html
<article class="ui-post-card">
  <div class="ui-post-card__content">
    <span class="ui-post-card__eyebrow">Tech</span>
    <h4 class="ui-post-card__title">Post title</h4>
  </div>
</article>
```

## ui-post-grid

Purpose: post grid and load-more area for the `ui-main` ecosystem.

When to use: use inside `ui-main`.

HTML minimum:

```html
<div class="ui-main__grid"></div>
```

Required classes:

- `ui-main__grid`

Optional classes:

- `ui-main__more`
- `ui-main__more-button`

Dependencies:

- `ui-post-card`
- `ui-main`

Responsive:

- One column by default.
- Two columns from 768px.

Accessibility:

- Load-more buttons need a real action in consumer projects.

Example:

```html
<div class="ui-main__grid">
  <article class="ui-post-card"></article>
</div>
```

## ui-tag-list

Purpose: reusable list of tags, categories, topics, or simple filters.

When to use: use for article tags, category clouds, compact topic lists, and category lists with optional counts.

When not to use: do not use for primary navigation, breadcrumbs, related-story lists, tabs with panels, or complex removable chips.

HTML minimum:

```html
<ul class="ui-tag-list" aria-label="Tags">
  <li class="ui-tag-list__item">
    <span class="ui-tag-list__tag">JavaScript</span>
  </li>
</ul>
```

Recommended structures:

```html
<ul class="ui-tag-list" aria-label="Categories">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="#">CSS</a>
  </li>
</ul>
```

```html
<ul class="ui-tag-list ui-tag-list--interactive" aria-label="Filter by topic">
  <li class="ui-tag-list__item">
    <button class="ui-tag-list__tag ui-tag-list__tag--active" type="button" aria-pressed="true">
      Design
    </button>
  </li>
</ul>
```

```html
<ul class="ui-tag-list ui-tag-list--with-count" aria-label="Categories">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="#">
      <span class="ui-tag-list__label">Design</span>
      <span class="ui-tag-list__count" aria-label="12 articles">12</span>
    </a>
  </li>
</ul>
```

Required classes:

- `ui-tag-list`
- `ui-tag-list__item`
- `ui-tag-list__tag`

Optional classes:

- `ui-tag-list__label`
- `ui-tag-list__count`
- `ui-tag-list--compact`
- `ui-tag-list--inline`
- `ui-tag-list--stacked`
- `ui-tag-list--with-count`
- `ui-tag-list--interactive`
- `ui-tag-list__tag--active`
- `ui-tag-list__tag--disabled`

Dependencies:

- No JavaScript required.
- No icon dependency.
- `src/components/ui-tag-list/ui-tag-list.scss`

Responsive:

- Wraps by default.
- `ui-tag-list--stacked` creates a full-width vertical list suitable for sidebars.
- `ui-tag-list--compact` reduces spacing for dense areas.

Accessibility:

- Use `ul > li > span` for informational tags.
- Use `ul > li > a` when each tag navigates.
- Use `ul > li > button type="button"` when tags filter content in place.
- Use `aria-current="page"` for active links.
- Use `aria-pressed="true"` for active filter buttons.
- Add `aria-label` to the list when context is not obvious.
- For disabled tags, prefer `span`.
- If using `a`, remove `href` while disabled.
- Do not use active links with `aria-disabled="true"`.

Example:

```html
<ul class="ui-tag-list ui-tag-list--interactive" aria-label="Topics">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="#">Design</a>
  </li>
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="#">Accessibility</a>
  </li>
</ul>
```

## ui-callout

Purpose: reusable highlighted block for editorial and technical notes.

When to use: use for notes, tips, warnings, documentation guidance, contextual messages, and optional actions inside articles, docs, sidebars, or grids.

When not to use: do not use for quotes, newsletters, toast messages, modals, dismissible alerts, post cards, or numbered principle lists.

HTML minimum:

```html
<aside class="ui-callout">
  <p class="ui-callout__content">
    This is an important note.
  </p>
</aside>
```

Recommended structures:

```html
<aside class="ui-callout" aria-labelledby="callout-title">
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-title">Before you continue</h3>
    <p class="ui-callout__content">
      Make sure your compiled CSS is imported before using SayUI classes.
    </p>
  </div>
</aside>
```

```html
<aside class="ui-callout ui-callout--tip" aria-labelledby="callout-tip-title">
  <span class="ui-callout__icon" aria-hidden="true">i</span>
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-tip-title">Tip</h3>
    <p class="ui-callout__content">
      Use semantic HTML first, then apply SayUI classes.
    </p>
  </div>
</aside>
```

```html
<aside class="ui-callout ui-callout--info" aria-labelledby="callout-docs-title">
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-docs-title">Documentation note</h3>
    <p class="ui-callout__content">
      This component works without JavaScript.
    </p>
    <div class="ui-callout__actions">
      <a class="ui-callout__link" href="#">Read the guidelines</a>
    </div>
  </div>
</aside>
```

Required classes:

- `ui-callout`
- `ui-callout__content`

Optional classes:

- `ui-callout__icon`
- `ui-callout__body`
- `ui-callout__title`
- `ui-callout__link`
- `ui-callout__actions`
- `ui-callout__action`
- `ui-callout--info`
- `ui-callout--tip`
- `ui-callout--warning`
- `ui-callout--danger`
- `ui-callout--success`
- `ui-callout--compact`
- `ui-callout--strong`
- `ui-callout--inline`

Dependencies:

- No JavaScript required.
- No external icon dependency.
- `src/components/ui-callout/ui-callout.scss`

Responsive:

- Fluid by default.
- Works inside articles, documentation pages, sidebars, and grids.
- Stacks icon and body on very narrow screens.
- `ui-callout--compact` is better for dense sidebars.
- `ui-callout--inline` is intended for short inline notes.

Accessibility:

- Use `aside` for complementary content.
- Use `div` if the message is part of the direct reading flow.
- Do not use `role="alert"` unless the message is dynamic or genuinely critical.
- Decorative icons need `aria-hidden="true"`.
- Use links for navigation.
- Use buttons only for actions in the current page.
- Links and actions keep visible focus.

Example:

```html
<aside class="ui-callout ui-callout--warning" aria-labelledby="callout-warning-title">
  <span class="ui-callout__icon" aria-hidden="true">!</span>
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-warning-title">Check first</h3>
    <p class="ui-callout__content">
      Confirm the expected markup before copying this pattern.
    </p>
  </div>
</aside>
```

## ui-table

Purpose: reusable table component for real tabular data.

When to use: use for feature comparisons, support matrices, versions, compatibility data, package totals, and other row/column data.

When not to use: do not use for page layout, card grids, navigation, simple lists, or interactive data grids with sorting/filtering unless a consumer project adds that behavior separately.

HTML minimum:

```html
<table class="ui-table">
  <thead>
    <tr>
      <th scope="col">Feature</th>
      <th scope="col">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Compiled CSS</td>
      <td>Supported</td>
    </tr>
  </tbody>
</table>
```

Recommended structure:

```html
<div class="ui-table__wrapper">
  <table class="ui-table ui-table--responsive">
    <caption class="ui-table__caption">
      Browser support matrix
    </caption>
    <thead>
      <tr>
        <th scope="col">Browser</th>
        <th scope="col">Version</th>
        <th scope="col">Support</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Chrome</th>
        <td>120+</td>
        <td>Full</td>
      </tr>
    </tbody>
  </table>
</div>
```

Required classes:

- `ui-table`

Optional classes:

- `ui-table__wrapper`
- `ui-table__caption`
- `ui-table--compact`
- `ui-table--striped`
- `ui-table--bordered`
- `ui-table--responsive`

Dependencies:

- No JavaScript required.
- No framework dependency.
- `src/components/ui-table/ui-table.scss`

Responsive:

- `ui-table__wrapper` handles horizontal overflow.
- `ui-table--responsive` gives the table a minimum width so columns do not collapse too aggressively.
- Tables are not converted into cards.
- `tabindex="0"` is optional on the wrapper when a consumer needs keyboard-focusable horizontal scrolling.

Accessibility:

- Use native `table`, `thead`, `tbody`, `tfoot`, `tr`, `th`, `td`, and `caption`.
- Use `th scope="col"` for column headers.
- Use `th scope="row"` when the first cell labels a row.
- Keep `caption` as a real `<caption>` element.
- Do not use tables for layout.
- Add an accessible label to a focusable wrapper when using `tabindex="0"`.

Example:

```html
<div class="ui-table__wrapper" tabindex="0" aria-label="Scrollable browser support table">
  <table class="ui-table ui-table--responsive ui-table--striped">
    <caption class="ui-table__caption">Browser support matrix</caption>
    <thead>
      <tr>
        <th scope="col">Browser</th>
        <th scope="col">Support</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Chrome</th>
        <td>Full</td>
      </tr>
    </tbody>
  </table>
</div>
```

## ui-code-block

Purpose: reusable block for code snippets, commands, configuration, or short console output.

When to use: use for HTML, CSS, SCSS, JavaScript, JSON, shell commands, configuration snippets, and technical examples.

When not to use: do not use for inline code, interactive editors, sandboxes, large logs, syntax highlighting, diffs, or executable terminals.

HTML minimum:

```html
<pre class="ui-code-block"><code>npm run build</code></pre>
```

Recommended structure:

```html
<figure class="ui-code-block">
  <figcaption class="ui-code-block__caption">
    Build command
  </figcaption>

  <div class="ui-code-block__header">
    <span class="ui-code-block__filename">package.json</span>
    <span class="ui-code-block__language">json</span>
  </div>

  <pre class="ui-code-block__pre"><code class="ui-code-block__code">{
  "scripts": {
    "build": "sass src/styles/main.scss dist/css/sayui.css"
  }
}</code></pre>
</figure>
```

Copy hook:

```html
<figure class="ui-code-block ui-code-block--terminal">
  <div class="ui-code-block__header">
    <span class="ui-code-block__filename">Terminal</span>
    <span class="ui-code-block__language">shell</span>
    <button class="ui-code-block__copy" type="button">Copy</button>
  </div>

  <pre class="ui-code-block__pre"><code class="ui-code-block__code">$ npm run build</code></pre>
</figure>
```

Required classes:

- `ui-code-block`

Optional classes:

- `ui-code-block__header`
- `ui-code-block__filename`
- `ui-code-block__language`
- `ui-code-block__pre`
- `ui-code-block__code`
- `ui-code-block__caption`
- `ui-code-block__copy`
- `ui-code-block--compact`
- `ui-code-block--terminal`
- `ui-code-block--wrap`

Dependencies:

- No JavaScript required.
- No syntax highlighting required.
- No external icon dependency.
- `src/components/ui-code-block/ui-code-block.scss`

Responsive:

- Code scrolls horizontally by default.
- `ui-code-block--wrap` allows long lines to wrap.
- Headers wrap on narrow screens.
- Consumers may add `tabindex="0"` to `ui-code-block__pre` if keyboard-accessible horizontal scrolling is needed.

Accessibility:

- Preserve semantic `pre > code`.
- Use `figure` and `figcaption` when the block needs a description.
- Keep `ui-code-block__caption` on a real `figcaption`.
- `ui-code-block__copy` must be a `button type="button"` when used.
- `ui-code-block__copy` is only a visual hook; SayUI does not implement copy behavior.
- Do not use `role="button"` on non-interactive elements.
- Do not require `tabindex` on code blocks by default.

Example:

```html
<figure class="ui-code-block ui-code-block--wrap">
  <figcaption class="ui-code-block__caption">Install command</figcaption>
  <pre class="ui-code-block__pre" tabindex="0"><code class="ui-code-block__code">npm install sayui --save-dev --ignore-scripts</code></pre>
</figure>
```

## ui-toc

Purpose: reusable table of contents for long articles, documentation, guides, and pages with internal sections.

When to use: use for in-page navigation that links to real headings.

When not to use: do not use for primary navigation, breadcrumbs, tabs, filters, pagination, related posts, or automated scrollspy.

HTML minimum:

```html
<nav class="ui-toc" aria-label="Table of contents">
  <ol class="ui-toc__list">
    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#introduction">Introduction</a>
    </li>
  </ol>
</nav>
```

Recommended structure:

```html
<nav class="ui-toc" aria-labelledby="toc-title">
  <h2 class="ui-toc__title" id="toc-title">On this page</h2>

  <ol class="ui-toc__list">
    <li class="ui-toc__item">
      <a class="ui-toc__link ui-toc__link--active" href="#overview" aria-current="location">
        Overview
      </a>
    </li>

    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#installation">Installation</a>

      <ol class="ui-toc__list ui-toc__list--nested">
        <li class="ui-toc__item">
          <a class="ui-toc__link" href="#requirements">Requirements</a>
        </li>
      </ol>
    </li>
  </ol>
</nav>
```

Required classes:

- `ui-toc`
- `ui-toc__list`
- `ui-toc__item`
- `ui-toc__link`

Optional classes:

- `ui-toc__title`
- `ui-toc__list--nested`
- `ui-toc__item--active`
- `ui-toc__link--active`
- `ui-toc--compact`
- `ui-toc--boxed`
- `ui-toc--sticky`

Dependencies:

- No JavaScript required.
- No scrollspy included.
- No external icon dependency.
- `src/components/ui-toc/ui-toc.scss`

Responsive:

- Base component is fluid and can live inside sidebars or content columns.
- `ui-toc__list--nested` indents nested sections without requiring extra depth classes.
- `ui-toc--boxed` adds its own visual container.
- `ui-toc--sticky` only becomes sticky from the medium breakpoint; on mobile it remains a normal block.

Accessibility:

- Use `nav`.
- Use `aria-label` when there is no visible title.
- Use `aria-labelledby` when using `ui-toc__title`.
- Links must point to real heading IDs.
- Use `aria-current="location"` only on the active link.
- Active state is manual; SayUI does not implement scrollspy.
- Use links, not buttons, for section navigation.
- Links keep visible focus.

Example:

```html
<nav class="ui-toc ui-toc--boxed ui-toc--sticky" aria-labelledby="toc-example-title">
  <h2 class="ui-toc__title" id="toc-example-title">On this page</h2>
  <ol class="ui-toc__list">
    <li class="ui-toc__item ui-toc__item--active">
      <a class="ui-toc__link ui-toc__link--active" href="#overview" aria-current="location">Overview</a>
    </li>
    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#usage">Usage</a>
    </li>
  </ol>
</nav>
```

## ui-meta-list

Purpose: reusable metadata list for compact editorial or technical details.

When to use: use for publication dates, reading time, view counts, simple author text, simple categories, and other short secondary details near cards, banners, previews, sidebars, or documentation entries.

When not to use: do not use for tags or filters, author cards with avatars, complex bylines, comments, author badges, hero metadata layouts, breadcrumbs, navigation, or tabular data.

HTML minimum:

```html
<ul class="ui-meta-list" aria-label="Article metadata">
  <li class="ui-meta-list__item">5 min read</li>
</ul>
```

Recommended inline structure:

```html
<ul class="ui-meta-list ui-meta-list--inline ui-meta-list--with-separators" aria-label="Article metadata">
  <li class="ui-meta-list__item">
    <time datetime="2024-03-24">Mar 24, 2024</time>
  </li>
  <li class="ui-meta-list__item">5 min read</li>
  <li class="ui-meta-list__item">48k views</li>
</ul>
```

Recommended stacked structure:

```html
<dl class="ui-meta-list ui-meta-list--stacked" aria-label="Publication metadata">
  <div class="ui-meta-list__item">
    <dt class="ui-meta-list__label">Published</dt>
    <dd class="ui-meta-list__value">
      <time datetime="2024-10-15">October 15, 2024</time>
    </dd>
  </div>

  <div class="ui-meta-list__item">
    <dt class="ui-meta-list__label">Author</dt>
    <dd class="ui-meta-list__value">Elena Valery</dd>
  </div>
</dl>
```

Required classes:

- `ui-meta-list`
- `ui-meta-list__item`

Optional classes:

- `ui-meta-list__label`
- `ui-meta-list__value`
- `ui-meta-list--inline`
- `ui-meta-list--stacked`
- `ui-meta-list--compact`
- `ui-meta-list--with-separators`

Dependencies:

- No JavaScript required.
- No framework dependency.
- No external icon dependency.
- `src/components/ui-meta-list/ui-meta-list.scss`

Responsive:

- Wraps by default.
- `ui-meta-list--inline` keeps equivalent metadata in a row that can wrap.
- `ui-meta-list--stacked` presents label/value pairs in a vertical rhythm.
- `ui-meta-list--compact` reduces spacing and type size for dense areas.
- No breakpoint is required by default.

Accessibility:

- Use `ul` when the metadata items are equivalent.
- Use `dl` when metadata uses label/value pairs.
- Use real `<time datetime="">` elements for dates.
- Add `aria-label` when surrounding context does not clearly name the metadata group.
- `ui-meta-list--with-separators` uses decorative pseudo-elements; do not add separator characters as text.
- Use links only when the metadata item navigates.
- Do not use this component for interactive filters; use `ui-tag-list`.

Example:

```html
<ul class="ui-meta-list ui-meta-list--compact ui-meta-list--with-separators" aria-label="Post metadata">
  <li class="ui-meta-list__item">By Elena Valery</li>
  <li class="ui-meta-list__item">
    <time datetime="2026-06-22">Jun 22, 2026</time>
  </li>
  <li class="ui-meta-list__item">Design</li>
</ul>
```

## ui-sidebar

Purpose: sidebar for trending links, categories, and newsletter.

When to use: use beside `ui-main` in `ui-layout__content`.

HTML minimum:

```html
<aside class="ui-sidebar"></aside>
```

Required classes:

- `ui-sidebar`

Optional classes:

- `ui-sidebar__section-title`
- `ui-sidebar__trending-list`
- `ui-sidebar__trending-item`
- `ui-sidebar__thumb-wrapper`
- `ui-sidebar__thumb`
- `ui-sidebar__item-title`
- `ui-sidebar__item-meta`
- `ui-sidebar__categories`
- `ui-sidebar__category-link`
- `ui-sidebar__category-title`
- `ui-sidebar__count-badge`
- `ui-sidebar__count-text`
- `ui-sidebar__newsletter`
- `ui-sidebar__newsletter-icon`
- `ui-sidebar__newsletter-title`
- `ui-sidebar__newsletter-text`
- `ui-sidebar__form`
- `ui-sidebar__input`
- `ui-sidebar__submit`
- `ui-sidebar__form-note`

Dependencies:

- Material Symbols if using the newsletter icon.

Responsive:

- Full width by default.
- 33.333333% width from 1024px.

Accessibility:

- Newsletter input should have a label or accessible name.
- Links need valid destinations.

Example:

```html
<aside class="ui-sidebar">
  <section>
    <h4 class="ui-sidebar__section-title">Categories</h4>
  </section>
</aside>
```

## ui-footer

Purpose: general footer for the main page.

When to use: use at the bottom of `ui-page`.

HTML minimum:

```html
<footer class="ui-footer">
  <div class="ui-footer__inner"></div>
</footer>
```

Required classes:

- `ui-footer`
- `ui-footer__inner`

Optional classes:

- `ui-footer__header`
- `ui-footer__brand`
- `ui-footer__icon-box`
- `ui-footer__brand-icon`
- `ui-footer__title`
- `ui-footer__socials`
- `ui-footer__social-link`
- `ui-footer__social-icon`
- `ui-footer__grid`
- `ui-footer__column`
- `ui-footer__column-title`
- `ui-footer__link`
- `ui-footer__legend`

Dependencies:

- Material Symbols if using footer icons.

Responsive:

- Footer columns use 2 columns by default and 4 columns from 768px.

Accessibility:

- Social links should have accessible labels.
- Footer navigation should use real links.

Example:

```html
<footer class="ui-footer">
  <div class="ui-footer__inner">
    <div class="ui-footer__legend">Copyright</div>
  </div>
</footer>
```

## ui-footer-editorial

Purpose: editorial footer for secondary/article pages.

When to use: use after `ui-editorial-page`.

HTML minimum:

```html
<footer class="ui-footer-editorial">
  <div class="ui-footer-editorial__container"></div>
</footer>
```

Required classes:

- `ui-footer-editorial`
- `ui-footer-editorial__container`

Optional classes:

- `ui-footer-editorial__top`
- `ui-footer-editorial__brand`
- `ui-footer-editorial__logo`
- `ui-footer-editorial__tagline`
- `ui-footer-editorial__nav`
- `ui-footer-editorial__link`
- `ui-footer-editorial__bottom`
- `ui-footer-editorial__copyright`
- `ui-footer-editorial__social`
- `ui-footer-editorial__social-item`
- `ui-footer-editorial__icon`

Dependencies:

- Material Symbols if using social icons.

Responsive:

- Stacked by default.
- Top and bottom groups become rows from 768px.

Accessibility:

- If social icons are interactive, prefer links or buttons with accessible labels.

Example:

```html
<footer class="ui-footer-editorial">
  <div class="ui-footer-editorial__container">
    <div class="ui-footer-editorial__brand">
      <span class="ui-footer-editorial__logo">Brand</span>
    </div>
  </div>
</footer>
```
