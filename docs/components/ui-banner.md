# ui-banner

Purpose: featured editorial block for highlighting one primary story, resource, or announcement with media, text, author context, and a call to action.

When to use: use when one item should receive more visual weight than a post card, usually near the top of a page, section, or editorial listing.

When not to use: do not use for generic page heroes, multi-card grids, compact post previews, alerts, or newsletter signups.

HTML minimum:

```html
<section class="ui-banner">
  <div class="ui-banner__wrapper">
    <div class="ui-banner__content">
      <h2 class="ui-banner__title">Featured title</h2>
    </div>
  </div>
</section>
```

Recommended complete structure:

```html
<section class="ui-banner" aria-labelledby="featured-story-title">
  <div class="ui-banner__wrapper">
    <div class="ui-banner__media">
      <img class="ui-banner__image" src="feature.jpg" alt="Featured story image">
    </div>

    <div class="ui-banner__content">
      <span class="ui-banner__eyebrow">Featured Story</span>
      <h2 class="ui-banner__title" id="featured-story-title">
        The Future of Minimalist Design
      </h2>
      <p class="ui-banner__description">
        A short description that explains why this story matters.
      </p>

      <div class="ui-banner__author">
        <img class="ui-banner__author-image" src="author.jpg" alt="Alex Debil">
        <div class="ui-banner__author-info">
          <p class="ui-banner__author-name">Alex Debil</p>
          <p class="ui-banner__meta">Editorial Design - 8 min read</p>
        </div>
      </div>

      <a class="ui-banner__link" href="/articles/design-systems">
        Read full article
        <span class="material-symbols-outlined" aria-hidden="true">arrow_forward</span>
      </a>
    </div>
  </div>
</section>
```

Required classes:

- `ui-banner`
- `ui-banner__wrapper`
- `ui-banner__content`
- `ui-banner__title`

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

Internal or composition-dependent classes:

- `ui-banner__author-info` depends on `ui-banner__author`.
- `ui-banner__author-image`, `ui-banner__author-name`, and `ui-banner__meta` are meaningful as part of the author/meta row.
- The icon inside `ui-banner__link` is not required and should remain decorative when used.

Dependencies:

- An image if using media.
- Material Symbols if using the arrow icon.
- `src/components/banner/banner.scss`

Responsive:

- Stacked by default.
- Media and content sit side by side from 1024px.
- Works as an isolated block or inside a larger layout container.

Accessibility:

- Use descriptive `alt` text when the image is meaningful.
- If the image is decorative, use empty `alt`.
- `ui-banner__link` needs a real destination in consumer projects.
- Prefer `aria-labelledby` when the banner has a visible title.
- If the arrow icon is decorative, use `aria-hidden="true"`.

Relationship with newer primitives:

- `ui-meta-list` could eventually replace `ui-banner__meta`, but do not migrate without a contract update.
- `ui-tag-list` can be used near a banner, but should not replace `ui-banner__eyebrow`.
- `ui-callout`, `ui-code-block`, `ui-table`, and `ui-toc` are separate content components and should not be nested into the banner by default.

Future extraction candidates:

- `ui-eyebrow` for repeated eyebrow labels.
- `ui-byline` or `ui-author-card` for author image/name/meta patterns.
- `ui-meta-list` adoption for simple metadata after visual review.

Isolated example:

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

Composition example:

```html
<main class="ui-layout">
  <section class="ui-banner">
    <div class="ui-banner__wrapper">
      <div class="ui-banner__content">
        <span class="ui-banner__eyebrow">Featured</span>
        <h2 class="ui-banner__title">Featured title</h2>
      </div>
    </div>
  </section>
</main>
```

