# ui-trending-list

Purpose: compact list of highlighted or trending content with optional thumbnail/media, required title, and optional short metadata.

When to use: use in sidebars, editorial modules, footers, or static recommendation areas where items need a small visual preview and a link to content.

When not to use: do not use for full cards, card grids, purely textual related lists, TOCs, tags, breadcrumbs, primary navigation, long feeds, algorithmic ranking, JavaScript recommendations, or complex badges.

## HTML Minimum

```html
<ul class="ui-trending-list" aria-label="Trending articles">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/grid-systems">
      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          10 Grid Systems Every Designer Should Master
        </span>
      </span>
    </a>
  </li>
</ul>
```

## With Thumbnail

```html
<ul class="ui-trending-list" aria-label="Trending articles">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/grid-systems">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          10 Grid Systems Every Designer Should Master
        </span>
      </span>
    </a>
  </li>
</ul>
```

Use `alt=""` when the thumbnail is decorative and the visible title describes the destination.

## With Metadata

```html
<ul class="ui-trending-list" aria-label="Most viewed articles">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/grid-systems">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          10 Grid Systems Every Designer Should Master
        </span>
        <span class="ui-trending-list__meta">48k views</span>
      </span>
    </a>
  </li>
</ul>
```

## With Date

```html
<ul class="ui-trending-list" aria-label="Recent recommendations">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/designing-with-time">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="Abstract editorial interface preview">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          Designing with Time as a Constraint
        </span>
        <span class="ui-trending-list__meta">
          <time datetime="2026-06-23">Jun 23, 2026</time>
        </span>
      </span>
    </a>
  </li>
</ul>
```

## Compact

```html
<ul class="ui-trending-list ui-trending-list--compact" aria-label="Trending resources">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/motion-context">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          Motion as spatial context
        </span>
        <span class="ui-trending-list__meta">8 min read</span>
      </span>
    </a>
  </li>
</ul>
```

## Divided

```html
<ul class="ui-trending-list ui-trending-list--divided" aria-label="Popular articles">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/grid-systems">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          10 Grid Systems Every Designer Should Master
        </span>
        <span class="ui-trending-list__meta">48k views</span>
      </span>
    </a>
  </li>
</ul>
```

## Manual Ranking With ol

Use `ol` only when the order represents manual editorial ranking.

```html
<ol class="ui-trending-list" aria-label="Manual editorial ranking">
  <li class="ui-trending-list__item">
    <a class="ui-trending-list__link" href="/articles/start-with-semantics">
      <span class="ui-trending-list__media">
        <img class="ui-trending-list__image" src="thumb.jpg" alt="">
      </span>

      <span class="ui-trending-list__body">
        <span class="ui-trending-list__title">
          Start with semantic HTML
        </span>
        <span class="ui-trending-list__meta">Editor's pick</span>
      </span>
    </a>
  </li>
</ol>
```

## Public Classes

- `ui-trending-list`
- `ui-trending-list__item`
- `ui-trending-list__link`
- `ui-trending-list__media`
- `ui-trending-list__image`
- `ui-trending-list__body`
- `ui-trending-list__title`
- `ui-trending-list__meta`
- `ui-trending-list--compact`
- `ui-trending-list--divided`

## Not Included

- `ui-trending-list--without-media`
- `ui-trending-list--ranked`
- `ui-trending-list--grid`
- `ui-trending-list--featured`
- `ui-trending-list__description`
- `ui-trending-list__badge`
- `ui-trending-list__eyebrow`

## Accessibility

- Use `ul` by default.
- Use `ol` only for manual editorial ranking.
- Each item must use `li`.
- Each navigable item should use `a.ui-trending-list__link` with a real `href`.
- `ui-trending-list__title` is required.
- Use `alt=""` for decorative thumbnails when the title describes the destination.
- Use meaningful `alt` text when the image adds information not present in the title.
- Use `<time datetime="">` for real dates.
- Do not use buttons for navigation.
- Do not add unnecessary roles.

## Responsive

The base layout is vertical. Each item is horizontal with optional media and wrapping text. `ui-trending-list--compact` reduces spacing and thumbnail size. `ui-trending-list--divided` adds item borders without creating cards or grids.

## Relationship To Existing Components

- `ui-related-list`: use for textual related links without media.
- `ui-post-card`: use for complete cards with larger images, descriptions, and card surfaces.
- `ui-sidebar`: `ui-sidebar__trending-list` inspired this component, but should not be migrated automatically.
- `ui-meta-list`: `ui-trending-list__meta` is local in v1.
- `ui-eyebrow`: not used internally in v1.
