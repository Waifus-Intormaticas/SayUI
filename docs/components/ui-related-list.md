# ui-related-list

Purpose: compact list of links to related articles, resources, guides, or recommended reading.

When to use: use in sidebars, articles, editorial footers, documentation pages, or compact secondary content areas.

When not to use: do not use for post cards, card grids, trending widgets with thumbnails, table of contents navigation, tags, breadcrumbs, primary navigation, full feeds, or JavaScript-powered recommendations.

HTML minimum:

```html
<ul class="ui-related-list" aria-label="Related articles">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__title">
        Digital Sovereignty in the Age of AI
      </span>
    </a>
  </li>
</ul>
```

Recommended structure:

```html
<section aria-labelledby="related-list-title">
  <h2 id="related-list-title">Related Stories</h2>

  <ul class="ui-related-list">
    <li class="ui-related-list__item">
      <a class="ui-related-list__link" href="#">
        <span class="ui-related-list__category">Politics</span>
        <span class="ui-related-list__title">
          Digital Sovereignty in the Age of AI
        </span>
      </a>
    </li>
  </ul>
</section>
```

With category:

```html
<ul class="ui-related-list" aria-label="Related stories">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__category">Tech</span>
      <span class="ui-related-list__title">
        Hardware for the Distracted: The Light Phone III
      </span>
    </a>
  </li>
</ul>
```

With metadata:

```html
<ul class="ui-related-list" aria-label="Trending stories">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__title">
        10 Grid Systems Every Designer Should Master
      </span>
      <span class="ui-related-list__meta">48k views</span>
    </a>
  </li>

  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__title">
        Designing with Time as a Constraint
      </span>
      <span class="ui-related-list__meta">
        <time datetime="2026-06-23">Jun 23, 2026</time>
      </span>
    </a>
  </li>
</ul>
```

Compact:

```html
<ul class="ui-related-list ui-related-list--compact" aria-label="Related resources">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__title">Motion as spatial context</span>
    </a>
  </li>
</ul>
```

Divided:

```html
<ul class="ui-related-list ui-related-list--divided" aria-label="Related stories">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__category">Politics</span>
      <span class="ui-related-list__title">
        Digital Sovereignty in the Age of AI
      </span>
    </a>
  </li>
</ul>
```

Ordered:

```html
<ol class="ui-related-list" aria-label="Recommended reading order">
  <li class="ui-related-list__item">
    <a class="ui-related-list__link" href="#">
      <span class="ui-related-list__title">Start with semantic HTML</span>
    </a>
  </li>
</ol>
```

Required classes:

- `ui-related-list`
- `ui-related-list__item`
- `ui-related-list__link`
- `ui-related-list__title`

Optional classes:

- `ui-related-list__category`
- `ui-related-list__meta`
- `ui-related-list--compact`
- `ui-related-list--divided`

Rules:

- Use `ul` by default.
- Use `ol` only when order matters.
- Each item must be an `li`.
- `ui-related-list__title` is required.
- Each navigable item should use a real `a href`.
- `ui-related-list__category` is part of this component and does not require `ui-eyebrow`.
- `ui-related-list__meta` is part of this component and does not require `ui-meta-list`.
- If metadata is a date, use `time datetime`.
- If there is no visible title, use `aria-label`.
- If there is a visible external title, wrap the list in `section aria-labelledby`.
- Do not use for internal page navigation; use `ui-toc` instead.

Not included in v1:

- `ui-related-list--with-media`
- `ui-related-list--grid`
- `ui-related-list--trending`
- `ui-related-list--numbered`
- `ui-related-list__media`
- `ui-related-list__image`
- `ui-related-list__description`
- `ui-related-list__badge`
- `ui-related-list__section-title`

Dependencies:

- No JavaScript required.
- No image or media dependency.
- No `ui-post-card`, `ui-trending-list`, `ui-card`, or `ui-toc` dependency.
- `src/components/ui-related-list/ui-related-list.scss`

Responsive:

- Vertical by default.
- Works in narrow columns.
- Titles wrap naturally.
- Metadata stacks beneath titles.
- `ui-related-list--compact` reduces spacing.
- `ui-related-list--divided` adds item borders without requiring a fixed width.

Relationship with existing components:

- `ui-post-card` remains the component for complete post preview cards.
- `ui-article-related` remains the component for editorial card grids.
- `ui-sidebar` and `ui-article-sidebar` are not migrated automatically.
- `ui-section-header` can title a related-list composition, but `ui-related-list` does not depend on it.

Example:

```html
<section aria-labelledby="docs-related-title">
  <h2 id="docs-related-title">Related docs</h2>
  <ul class="ui-related-list ui-related-list--divided">
    <li class="ui-related-list__item">
      <a class="ui-related-list__link" href="#">
        <span class="ui-related-list__category">Guide</span>
        <span class="ui-related-list__title">Component contract basics</span>
        <span class="ui-related-list__meta">
          <time datetime="2026-06-23">Jun 23, 2026</time>
        </span>
      </a>
    </li>
  </ul>
</section>
```
