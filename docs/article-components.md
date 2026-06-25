# Article Component Contracts

Article components live in `src/components/article/` and support the editorial page composition.

## ui-article-hero

Purpose: article heading and hero media block.

When to use: use near the top of `ui-editorial-page`.

HTML minimum:

```html
<section class="ui-article-hero">
  <div class="ui-article-hero__body"></div>
</section>
```

Required classes:

- `ui-article-hero`
- `ui-article-hero__body`

Optional classes:

- `ui-article-hero__intro`
- `ui-article-hero__header`
- `ui-article-hero__eyebrow`
- `ui-article-hero__title`
- `ui-article-hero__subtitle`
- `ui-article-hero__meta-group`
- `ui-article-hero__author-label`
- `ui-article-hero__author-name`
- `ui-article-hero__published-label`
- `ui-article-hero__date`
- `ui-article-hero__image-wrapper`
- `ui-article-hero__image`
- `ui-article-hero__overlay`

Dependencies:

- Hero image if image wrapper is used.

Responsive:

- Body stacks by default.
- Intro and meta become a row from 768px.

Accessibility:

- Use one `h1` for the article title.
- Hero image needs useful `alt` text if meaningful.

Example:

```html
<section class="ui-article-hero">
  <div class="ui-article-hero__body">
    <div class="ui-article-hero__intro">
      <h1 class="ui-article-hero__title">Article title</h1>
    </div>
  </div>
</section>
```

## ui-article-main

Purpose: main article prose and related in-article patterns.

When to use: use inside `ui-editorial-page__layout`.

HTML minimum:

```html
<article class="ui-article-main">
  <div class="ui-article-main__prose"></div>
</article>
```

Required classes:

- `ui-article-main`
- `ui-article-main__prose`

Optional classes:

- `ui-article-main__lead`
- `ui-article-main__paragraph`
- `ui-article-main__title`
- `ui-article-main__quote`
- `ui-article-main__quote-icon`
- `ui-article-main__quote-content`
- `ui-article-main__quote-cite`
- `ui-article-main__section-title`
- `ui-article-main__principles`
- `ui-article-main__principle`
- `ui-article-main__principle--margin`
- `ui-article-main__item-number`
- `ui-article-main__item-content`
- `ui-article-main__item-title`
- `ui-article-main__item-text`
- `ui-article-main__figure`
- `ui-article-main__figure-image`
- `ui-article-main__figure-caption`
- `ui-article-main__caption-text`
- `ui-article-main__tags`
- `ui-article-main__tag`
- `ui-article-main__comments-section`
- `ui-article-main__discourse`
- `ui-article-main__comments-content`
- `ui-article-main__comment`
- `ui-article-main__comment--reply`
- `ui-article-main__avatar-container`
- `ui-article-main__avatar-container--reply`
- `ui-article-main__avatar`
- `ui-article-main__meta`
- `ui-article-main__author`
- `ui-article-main__badge`
- `ui-article-main__time`
- `ui-article-main__text`
- `ui-article-main__reply-button`
- `ui-article-main__comment-form`
- `ui-article-main__form-title`
- `ui-article-main__textarea`
- `ui-article-main__submit`

Dependencies:

- Material Symbols if using quote icon.
- Article layout grid if paired with sidebar.

Responsive:

- Spans 8 columns from 1024px when inside `ui-editorial-page__layout`.

Accessibility:

- Preserve heading order.
- Comment form is visual by default; consumer projects must connect behavior.
- Textarea should have a label or accessible name in production.

Example:

```html
<article class="ui-article-main">
  <div class="ui-article-main__prose">
    <p class="ui-article-main__lead">Lead paragraph.</p>
    <p class="ui-article-main__paragraph">Body paragraph.</p>
  </div>
</article>
```

## ui-article-sidebar

Purpose: article-side supporting content such as author info, related stories, and tag cloud.

When to use: use beside `ui-article-main` inside `ui-editorial-page__layout`.

HTML minimum:

```html
<aside class="ui-article-sidebar">
  <div class="ui-article-sidebar__card"></div>
</aside>
```

Required classes:

- `ui-article-sidebar`
- `ui-article-sidebar__card`

Optional classes:

- `ui-article-sidebar__author`
- `ui-article-sidebar__avatar-container`
- `ui-article-sidebar__avatar`
- `ui-article-sidebar__author-info`
- `ui-article-sidebar__author-name`
- `ui-article-sidebar__author-role`
- `ui-article-sidebar__description`
- `ui-article-sidebar__social`
- `ui-article-sidebar__social-link`
- `ui-article-sidebar__section`
- `ui-article-sidebar__section-teme`
- `ui-article-sidebar__section-title`
- `ui-article-sidebar__list`
- `ui-article-sidebar__item`
- `ui-article-sidebar__item-space`
- `ui-article-sidebar__link`
- `ui-article-sidebar__category`
- `ui-article-sidebar__item-title`
- `ui-article-sidebar__tags`
- `ui-article-sidebar__tag`

Dependencies:

- Avatar image if author block is used.
- Material Symbols if social icons are used.

Responsive:

- Spans 4 columns from 1024px when inside `ui-editorial-page__layout`.
- Sidebar card is sticky on larger layouts.

Accessibility:

- Social links need accessible names.
- Related stories should remain a list when possible.

Example:

```html
<aside class="ui-article-sidebar">
  <div class="ui-article-sidebar__card">
    <h4 class="ui-article-sidebar__author-name">Author</h4>
  </div>
</aside>
```

## ui-article-related

Purpose: related article section, usually "Read Next".

When to use: use after the article layout inside `ui-editorial-page`.

HTML minimum:

```html
<section class="ui-article-related">
  <div class="ui-article-related__container"></div>
</section>
```

Required classes:

- `ui-article-related`
- `ui-article-related__container`

Optional classes:

- `ui-article-related__header`
- `ui-article-related__divider`
- `ui-article-related__grid`
- `ui-article-related__card`
- `ui-article-related__image-wrapper`
- `ui-article-related__image`
- `ui-article-related__content`
- `ui-article-related__category`
- `ui-article-related__title`
- `ui-article-related__description`

Dependencies:

- Related cards and images if used.

Responsive:

- One column by default.
- Three columns from 768px.

Accessibility:

- Cards should include links when they navigate.
- Divider is decorative and can be hidden from assistive tech in production markup if needed.

Example:

```html
<section class="ui-article-related">
  <div class="ui-article-related__container">
    <h3 class="ui-article-related__header">Read Next</h3>
  </div>
</section>
```

