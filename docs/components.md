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

