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
