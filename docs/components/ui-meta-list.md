# ui-meta-list

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

