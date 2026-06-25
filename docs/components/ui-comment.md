# ui-comment

Purpose: individual comment component for simple editorial or community conversations.

When to use: use for a single comment with required author and text, optional avatar, optional time, optional badge, optional reply action, and simple reply/nested presentation.

When not to use: do not use for comment forms, full comment systems, moderation, likes, votes, authentication, complex threading, author cards, editorial bylines, or testimonials.

## HTML Minimum

```html
<article class="ui-comment">
  <div class="ui-comment__body">
    <header class="ui-comment__header">
      <span class="ui-comment__author">Julian Moss</span>
    </header>

    <p class="ui-comment__text">
      This is a thoughtful comment.
    </p>
  </div>
</article>
```

## With Avatar And Time

```html
<article class="ui-comment">
  <div class="ui-comment__avatar-wrapper">
    <img class="ui-comment__avatar" src="avatar.jpg" alt="Julian Moss">
  </div>

  <div class="ui-comment__body">
    <header class="ui-comment__header">
      <span class="ui-comment__author">Julian Moss</span>
      <time class="ui-comment__time" datetime="2026-06-23T14:00:00">2h ago</time>
    </header>

    <p class="ui-comment__text">
      The point about motion as spatial awareness is critical.
    </p>
  </div>
</article>
```

## With Badge

```html
<article class="ui-comment">
  <div class="ui-comment__avatar-wrapper">
    <img class="ui-comment__avatar" src="author.jpg" alt="Elena Valery">
  </div>

  <div class="ui-comment__body">
    <header class="ui-comment__header">
      <span class="ui-comment__author">Elena Valery</span>
      <span class="ui-comment__badge">Author</span>
      <time class="ui-comment__time" datetime="2026-06-23T15:00:00">1h ago</time>
    </header>

    <p class="ui-comment__text">
      Motion is the why and where of the interface.
    </p>
  </div>
</article>
```

## With Reply Action

```html
<article class="ui-comment">
  <div class="ui-comment__body">
    <header class="ui-comment__header">
      <span class="ui-comment__author">Julian Moss</span>
      <time class="ui-comment__time" datetime="2026-06-23T14:00:00">2h ago</time>
    </header>

    <p class="ui-comment__text">
      This is exactly the kind of detail that makes motion feel useful.
    </p>

    <button class="ui-comment__reply" type="button">Reply</button>
  </div>
</article>
```

## Reply / Nested

```html
<article class="ui-comment ui-comment--reply">
  <div class="ui-comment__avatar-wrapper">
    <img class="ui-comment__avatar" src="author.jpg" alt="Elena Valery">
  </div>

  <div class="ui-comment__body">
    <header class="ui-comment__header">
      <span class="ui-comment__author">Elena Valery</span>
      <span class="ui-comment__badge">Author</span>
      <time class="ui-comment__time" datetime="2026-06-23T15:00:00">1h ago</time>
    </header>

    <p class="ui-comment__text">
      Exactly. Motion should explain where the interface is going.
    </p>

    <button class="ui-comment__reply" type="button">Reply</button>
  </div>
</article>
```

## Official Comment Composition

SayUI does not include `ui-comment-list` in v1.

For now, comment groups should be composed with a semantic `section`, an external heading, and multiple `article.ui-comment` elements.

Basic composition:

```html
<section aria-labelledby="comments-title">
  <h2 id="comments-title">The Discourse (3)</h2>

  <article class="ui-comment">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Julian Moss</span>
        <time class="ui-comment__time" datetime="2026-06-23T14:00:00">2h ago</time>
      </header>

      <p class="ui-comment__text">
        Motion as spatial awareness is critical.
      </p>
    </div>
  </article>

  <article class="ui-comment">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Nora Vale</span>
        <time class="ui-comment__time" datetime="2026-06-23T14:30:00">90m ago</time>
      </header>

      <p class="ui-comment__text">
        The strongest systems make orientation feel effortless.
      </p>
    </div>
  </article>
</section>
```

Composition with `ui-section-header`:

```html
<section aria-labelledby="comments-heading">
  <header class="ui-section-header ui-section-header--compact">
    <h2 class="ui-section-header__title" id="comments-heading">
      The Discourse (3)
    </h2>
  </header>

  <article class="ui-comment">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Julian Moss</span>
        <time class="ui-comment__time" datetime="2026-06-23T14:00:00">2h ago</time>
      </header>

      <p class="ui-comment__text">
        Motion as spatial awareness is critical.
      </p>
    </div>
  </article>
</section>
```

Composition with a simple reply:

```html
<section aria-labelledby="comments-thread-title">
  <h2 id="comments-thread-title">Comments</h2>

  <article class="ui-comment">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Julian Moss</span>
        <time class="ui-comment__time" datetime="2026-06-23T14:00:00">2h ago</time>
      </header>

      <p class="ui-comment__text">
        Motion as spatial awareness is critical.
      </p>

      <button class="ui-comment__reply" type="button">Reply</button>
    </div>
  </article>

  <article class="ui-comment ui-comment--reply">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Elena Valery</span>
        <span class="ui-comment__badge">Author</span>
        <time class="ui-comment__time" datetime="2026-06-23T15:00:00">1h ago</time>
      </header>

      <p class="ui-comment__text">
        Exactly. Motion should explain where the interface is going.
      </p>

      <button class="ui-comment__reply" type="button">Reply</button>
    </div>
  </article>
</section>
```

A future `ui-comment-list` would only make sense if SayUI needs an official contract for list spacing, empty states, a divided variant, or formal integration with a future `ui-comment-form`.

The current composition does not include forms, pagination, sorting, realtime behavior, moderation, likes, votes, authentication, or login flows.

## Public Classes

- `ui-comment`
- `ui-comment__avatar-wrapper`
- `ui-comment__avatar`
- `ui-comment__body`
- `ui-comment__header`
- `ui-comment__author`
- `ui-comment__badge`
- `ui-comment__time`
- `ui-comment__text`
- `ui-comment__reply`
- `ui-comment--reply`

## Not Included

- `ui-comment--compact`
- `ui-comment--highlighted`
- `ui-comment__actions`
- `ui-comment__form`
- `ui-comment__textarea`
- `ui-comment__submit`

## Accessibility

- Use `article` as the root for each comment.
- Author is required.
- Text is required.
- Avatar is optional.
- Use meaningful `alt` text when the avatar identifies the author.
- Use empty `alt=""` only when the avatar is decorative and the visible author already identifies the comment.
- Use `<time datetime="">` for real dates or timestamps.
- Use `button type="button"` for `ui-comment__reply` when it triggers an in-page action.
- Use `a.ui-comment__reply` only if the reply action navigates; examples in v1 use buttons.
- Do not add unnecessary roles.
- Badge must be visible text when it communicates a state such as `Author`.

## Responsive

The base layout is horizontal with avatar and content. The header can wrap author, badge, and time on narrow viewports. `ui-comment--reply` provides simple nesting with a left border and indentation; it is not a complex threading system.

## Relationship To Existing Components

- `ui-author-card`: do not use internally. Author cards are for profile/bio blocks.
- `ui-byline`: do not use internally. Bylines are compact editorial authorship, not comments.
- `ui-meta-list`: do not use internally in v1. Comment metadata belongs to the comment header.
- `ui-article-main`: the current article comment pattern inspired this component, but `ui-article-main` should not be migrated automatically.
- Future `ui-comment-form`: should be a separate contract for textarea, submit, validation, and form behavior.
