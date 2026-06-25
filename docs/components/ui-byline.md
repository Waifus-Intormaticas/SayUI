# ui-byline

Purpose: compact authorship and short publication metadata for editorial previews, banners, cards, and simple article hero contexts.

When to use: use for a compact author name, optional avatar, date, reading time, or simple editorial source attached to one piece of content.

When not to use: do not use for full author cards, long bios, roles, social links, comments, testimonials, team cards, tabular metadata, tags, badges, or complex profile blocks.

## HTML Minimum

```html
<p class="ui-byline">
  <span class="ui-byline__name">Elena Valery</span>
</p>
```

## With Avatar

```html
<div class="ui-byline">
  <img class="ui-byline__avatar" src="author.jpg" alt="Elena Valery">

  <div class="ui-byline__body">
    <span class="ui-byline__name">Elena Valery</span>
  </div>
</div>
```

## Linked Author

```html
<div class="ui-byline">
  <img class="ui-byline__avatar" src="author.jpg" alt="Elena Valery">

  <div class="ui-byline__body">
    <a class="ui-byline__name" href="/authors/elena-valery">Elena Valery</a>
  </div>
</div>
```

Use `a.ui-byline__name` only when it navigates to a real author or source page. Use `span.ui-byline__name` for plain text.

## With Metadata

```html
<div class="ui-byline">
  <img class="ui-byline__avatar" src="author.jpg" alt="Elena Valery">

  <div class="ui-byline__body">
    <a class="ui-byline__name" href="/authors/elena-valery">Elena Valery</a>

    <span class="ui-byline__meta">
      <span class="ui-byline__item">
        <time datetime="2024-03-24">Mar 24, 2024</time>
      </span>
      <span class="ui-byline__item">8 min read</span>
    </span>
  </div>
</div>
```

## Compact

```html
<p class="ui-byline ui-byline--compact">
  <span class="ui-byline__name">Elena Valery</span>
  <span class="ui-byline__meta">
    <span class="ui-byline__item">8 min read</span>
  </span>
</p>
```

## Stacked

```html
<div class="ui-byline ui-byline--stacked">
  <img class="ui-byline__avatar" src="author.jpg" alt="Elena Valery">

  <div class="ui-byline__body">
    <span class="ui-byline__name">Elena Valery</span>

    <span class="ui-byline__meta">
      <span class="ui-byline__item">
        <time datetime="2024-03-24">Mar 24, 2024</time>
      </span>
      <span class="ui-byline__item">8 min read</span>
    </span>
  </div>
</div>
```

## Address

`address` is allowed only when the byline represents real authorship or contact information for the content.

```html
<address class="ui-byline">
  <img class="ui-byline__avatar" src="author.jpg" alt="Elena Valery">

  <div class="ui-byline__body">
    <a class="ui-byline__name" href="/authors/elena-valery">Elena Valery</a>
    <span class="ui-byline__meta">
      <span class="ui-byline__item">Editorial desk</span>
    </span>
  </div>
</address>
```

## Public Classes

- `ui-byline`
- `ui-byline__avatar`
- `ui-byline__body`
- `ui-byline__name`
- `ui-byline__meta`
- `ui-byline__item`
- `ui-byline--compact`
- `ui-byline--stacked`

## Not Included

- `ui-byline--with-avatar`
- `ui-byline--hero`
- `ui-byline--comment`
- `ui-byline--card`
- `ui-byline__bio`
- `ui-byline__role`
- `ui-byline__links`
- `ui-byline__badge`
- `ui-byline__actions`

## Accessibility

- The name is required.
- `ui-byline__name` can be `span` or `a`.
- Use `a` only when it navigates.
- Avatar is optional.
- Use meaningful `alt` text when the avatar identifies the author.
- Use empty `alt=""` only when the avatar is decorative and the visible name already identifies the author.
- Use `<time datetime="">` for real dates.
- Do not use buttons, badges, or unnecessary roles.

## Responsive

The base layout is compact and horizontal. Metadata can wrap when space is narrow. `ui-byline--stacked` provides a more vertical rhythm for banners, previews, or simple hero contexts.

## Relationship To Existing Components

- `ui-author-card`: use when the author block needs bio, role, or links. `ui-byline` is only compact authorship.
- `ui-meta-list`: use for generic metadata without author identity. `ui-byline__meta` is local to the byline contract and does not require `ui-meta-list`.
- `ui-banner`: `ui-banner__author` is the main inspiration, but it should not be migrated automatically.
- `ui-article-hero`: may use a byline-like pattern in the future, but current hero metadata needs separate review before migration.
