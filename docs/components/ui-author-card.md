# ui-author-card

Purpose: public editorial card for presenting brief author information.

When to use: use for author blocks in sidebars, articles, simple author pages, or editorial footers.

When not to use: do not use for compact bylines, user comments, testimonials, team grids, full profile pages, author archives, or publication metadata.

HTML minimum:

```html
<article class="ui-author-card" aria-labelledby="author-card-name">
  <h3 class="ui-author-card__name" id="author-card-name">
    Elena Valery
  </h3>
</article>
```

Recommended structure:

```html
<article class="ui-author-card" aria-labelledby="author-card-name">
  <div class="ui-author-card__header">
    <div class="ui-author-card__avatar-wrapper">
      <img class="ui-author-card__avatar" src="author.jpg" alt="Elena Valery">
    </div>

    <div class="ui-author-card__identity">
      <h3 class="ui-author-card__name" id="author-card-name">
        Elena Valery
      </h3>
      <p class="ui-author-card__role">Senior Design Editor</p>
    </div>
  </div>

  <p class="ui-author-card__bio">
    Elena explores the intersection of cognitive psychology and digital craftsmanship.
  </p>

  <div class="ui-author-card__links" aria-label="Author links">
    <a class="ui-author-card__link" href="#" aria-label="Email Elena Valery">
      <span aria-hidden="true">@</span>
    </a>
    <a class="ui-author-card__link" href="#" aria-label="Visit Elena Valery website">
      <span aria-hidden="true">www</span>
    </a>
  </div>
</article>
```

Without avatar:

```html
<article class="ui-author-card" aria-labelledby="author-card-no-avatar-name">
  <div class="ui-author-card__identity">
    <h3 class="ui-author-card__name" id="author-card-no-avatar-name">
      Elena Valery
    </h3>
    <p class="ui-author-card__role">Senior Design Editor</p>
  </div>

  <p class="ui-author-card__bio">
    Elena writes about interface craft and editorial systems.
  </p>
</article>
```

Compact:

```html
<article class="ui-author-card ui-author-card--compact" aria-labelledby="author-card-compact-name">
  <div class="ui-author-card__header">
    <div class="ui-author-card__avatar-wrapper">
      <img class="ui-author-card__avatar" src="author.jpg" alt="Elena Valery">
    </div>

    <div class="ui-author-card__identity">
      <h3 class="ui-author-card__name" id="author-card-compact-name">
        Elena Valery
      </h3>
      <p class="ui-author-card__role">Senior Editor</p>
    </div>
  </div>
</article>
```

Editorial:

```html
<aside class="ui-author-card ui-author-card--editorial" aria-labelledby="author-card-editorial-name">
  <div class="ui-author-card__header">
    <div class="ui-author-card__avatar-wrapper">
      <img class="ui-author-card__avatar" src="author.jpg" alt="Elena Valery">
    </div>

    <div class="ui-author-card__identity">
      <h3 class="ui-author-card__name" id="author-card-editorial-name">
        Elena Valery
      </h3>
      <p class="ui-author-card__role">Senior Design Editor</p>
    </div>
  </div>

  <p class="ui-author-card__bio">
    Elena explores the intersection of cognitive psychology and digital craftsmanship.
  </p>

  <div class="ui-author-card__links" aria-label="Author links">
    <a class="ui-author-card__link" href="#" aria-label="Email Elena Valery">
      <span aria-hidden="true">@</span>
    </a>
    <a class="ui-author-card__link" href="#" aria-label="Visit Elena Valery website">
      <span aria-hidden="true">www</span>
    </a>
  </div>
</aside>
```

Required classes:

- `ui-author-card`
- `ui-author-card__name`

Optional classes:

- `ui-author-card__header`
- `ui-author-card__avatar-wrapper`
- `ui-author-card__avatar`
- `ui-author-card__identity`
- `ui-author-card__role`
- `ui-author-card__bio`
- `ui-author-card__links`
- `ui-author-card__link`
- `ui-author-card--compact`
- `ui-author-card--editorial`

Rules:

- Use `article` as the recommended root.
- Use `aside` when the author card is complementary to an article.
- Use `div` only when a parent already provides the semantic container.
- Name is required.
- Avatar, role, bio, and links are optional.
- `ui-author-card--editorial` preserves the strong article-sidebar author-panel intent.
- `ui-author-card--compact` is part of v1.
- There is no `ui-author-card--horizontal`, `ui-author-card--centered`, `ui-author-card--team`, or `ui-author-card--profile`.
- There is no `ui-author-card__badge`, `ui-author-card__meta`, or `ui-author-card__actions`.

Dependencies:

- No JavaScript required.
- No Material Symbols or external icon dependency.
- No `ui-byline`, `ui-comment`, testimonial, team grid, or profile-page dependency.
- `src/components/ui-author-card/ui-author-card.scss`

Responsive:

- Flexible by default.
- Header uses avatar plus identity in a row.
- Bio and links stack below.
- Links wrap when there are multiple items.
- `ui-author-card--compact` reduces padding, gap, avatar size, and type scale.

Accessibility:

- `ui-author-card__name` should use a native heading element at the correct document level.
- Use `aria-labelledby` on the root when the card should have an accessible name.
- Avatar images need meaningful `alt` text when they identify the author.
- Social links need `aria-label` when their visible text is symbolic.
- Decorative text inside social links should use `aria-hidden="true"`.

Relationship with existing components:

- `ui-author-card` is independent from `ui-article-sidebar`.
- `ui-article-sidebar__author` remains part of the current `ui-article-sidebar` contract and is not migrated automatically.
- `ui-banner__author` is closer to a future `ui-byline`; do not migrate it to `ui-author-card`.
- `ui-meta-list` can handle publication metadata outside the author card.
- `ui-eyebrow` can accompany a composition but should not replace `ui-author-card__role`.
- `ui-section-header` can introduce an author section but is not part of this component.

Example:

```html
<article class="ui-author-card ui-author-card--compact" aria-labelledby="author-example-name">
  <div class="ui-author-card__header">
    <div class="ui-author-card__avatar-wrapper">
      <img class="ui-author-card__avatar" src="author.jpg" alt="Elena Valery">
    </div>
    <div class="ui-author-card__identity">
      <h3 class="ui-author-card__name" id="author-example-name">Elena Valery</h3>
      <p class="ui-author-card__role">Senior Editor</p>
    </div>
  </div>
</article>
```
