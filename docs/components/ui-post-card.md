# ui-post-card

Purpose: reusable preview card for an article, post, resource, or editorial entry.

When to use: use in post grids, related-content areas, landing sections, archive listings, or any context where one content item needs image, category, title, description, and metadata.

When not to use: do not use for full articles, feature banners, navigation links, simple metadata rows, or purely tabular content.

HTML minimum:

```html
<article class="ui-post-card">
  <div class="ui-post-card__content">
    <h4 class="ui-post-card__title">Post title</h4>
  </div>
</article>
```

Recommended complete structure:

```html
<article class="ui-post-card">
  <div class="ui-post-card__image-wrapper">
    <img class="ui-post-card__image" src="thumbnail.jpg" alt="Article thumbnail">
  </div>

  <div class="ui-post-card__content">
    <span class="ui-post-card__eyebrow">Color Theory</span>
    <h4 class="ui-post-card__title">Mastering Red in Editorial Interfaces</h4>
    <p class="ui-post-card__description">
      Exploring why a focused color system can hold a full editorial identity.
    </p>
    <div class="ui-post-card__meta">Mar 24, 2024 - 5 min read</div>
  </div>
</article>
```

Required classes:

- `ui-post-card`
- `ui-post-card__content`
- `ui-post-card__title`

Optional classes:

- `ui-post-card__image-wrapper`
- `ui-post-card__image`
- `ui-post-card__eyebrow`
- `ui-post-card__title`
- `ui-post-card__description`
- `ui-post-card__meta`

Internal or composition-dependent classes:

- `ui-post-card__image` should live inside `ui-post-card__image-wrapper`.
- `ui-post-card__eyebrow` and `ui-post-card__meta` are card-specific text treatments, not standalone primitives yet.
- The card width and column behavior are usually controlled by the parent grid.

Dependencies:

- Image only if media is used.
- Parent layout such as `ui-main__grid` or another consumer-defined grid.
- `src/components/ui-post-card/ui-post-card.scss`

Responsive:

- Card sizing depends on its parent grid.
- Internal spacing and media treatment are component-owned.
- In `ui-main__grid`, cards follow the grid breakpoint behavior rather than defining their own columns.

Accessibility:

- If the card is clickable, document whether the title link or full card link is used.
- Images need useful `alt` text when meaningful.
- Avoid nesting a full-card link around other interactive controls.
- Use semantic heading levels that fit the surrounding page, even if the class remains `ui-post-card__title`.

Relationship with newer primitives:

- `ui-meta-list` may be a future replacement for `ui-post-card__meta`, but the current card contract keeps `ui-post-card__meta`.
- `ui-tag-list` should not replace `ui-post-card__eyebrow`; category chips can be placed outside the card if needed.
- `ui-callout`, `ui-code-block`, `ui-table`, and `ui-toc` are not card internals.

Future extraction candidates:

- `ui-eyebrow` for category/label text.
- `ui-meta-list` migration for metadata after card visual review.
- A future generic `ui-card` should not be introduced until several card families are compared.

Isolated example:

```html
<article class="ui-post-card">
  <div class="ui-post-card__content">
    <span class="ui-post-card__eyebrow">Tech</span>
    <h4 class="ui-post-card__title">Post title</h4>
  </div>
</article>
```

Composition example:

```html
<div class="ui-main__grid">
  <article class="ui-post-card">
    <div class="ui-post-card__content">
      <span class="ui-post-card__eyebrow">Design</span>
      <h4 class="ui-post-card__title">Post title</h4>
    </div>
  </article>
</div>
```

