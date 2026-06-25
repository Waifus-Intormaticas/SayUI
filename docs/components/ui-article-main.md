# ui-article-main

Purpose: public editorial component for the main body of a long-form article, including prose, pull quote, principle list, figure, tags, and comments.

When to use: use for article pages, long-form essays, editorial features, or documentation-like narratives that need SayUI's article rhythm.

When not to use: do not use for a generic Markdown prose wrapper, compact cards, standalone comments, standalone quote blocks, or technical reference pages that only need tables/code/callouts.

HTML minimum:

```html
<article class="ui-article-main">
  <div class="ui-article-main__prose">
    <p class="ui-article-main__lead">
      Introductory article text.
    </p>
  </div>
</article>
```

Recommended complete structure:

```html
<article class="ui-article-main">
  <div class="ui-article-main__prose">
    <p class="ui-article-main__lead">
      Opening paragraph for the article.
    </p>
    <p class="ui-article-main__paragraph">
      Supporting article paragraph.
    </p>

    <h2 class="ui-article-main__title">The Functional Role of Motion</h2>

    <blockquote class="ui-article-main__quote">
      <span class="material-symbols-outlined ui-article-main__quote-icon" aria-hidden="true">format_quote</span>
      <p class="ui-article-main__quote-content">
        Minimalism is not absence. It is the right amount of signal.
      </p>
      <cite class="ui-article-main__quote-cite">Editorial Design Principles</cite>
    </blockquote>

    <h3 class="ui-article-main__section-title">Core Principles</h3>
    <ul class="ui-article-main__principles">
      <li class="ui-article-main__principle">
        <span class="ui-article-main__item-number">1</span>
        <div class="ui-article-main__item-content">
          <strong class="ui-article-main__item-title">Intentionality</strong>
          <span class="ui-article-main__item-text">Every decision should carry meaning.</span>
        </div>
      </li>
      <li class="ui-article-main__principle ui-article-main__principle--margin">
        <span class="ui-article-main__item-number">2</span>
        <div class="ui-article-main__item-content">
          <strong class="ui-article-main__item-title">Rhythm</strong>
          <span class="ui-article-main__item-text">Spacing should support comfortable reading.</span>
        </div>
      </li>
    </ul>

    <figure class="ui-article-main__figure">
      <img class="ui-article-main__figure-image" src="figure.jpg" alt="Article figure">
      <figcaption class="ui-article-main__figure-caption">
        Fig 1.1: Supporting visual context.
      </figcaption>
    </figure>

    <p class="ui-article-main__caption-text">
      Closing or explanatory paragraph after the figure.
    </p>
  </div>

  <div class="ui-article-main__tags">
    <span class="ui-article-main__tag">User Experience</span>
    <span class="ui-article-main__tag">Minimalism</span>
  </div>

  <section class="ui-article-main__comments-section">
    <h3 class="ui-article-main__discourse">The Discourse (3)</h3>
  </section>
</article>
```

Required classes:

- `ui-article-main`
- `ui-article-main__prose`

Optional classes:

- `ui-article-main__lead`
- `ui-article-main__paragraph`
- `ui-article-main__title`
- `ui-article-main__section-title`
- `ui-article-main__quote`
- `ui-article-main__quote-icon`
- `ui-article-main__quote-content`
- `ui-article-main__quote-cite`
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

Internal or composition-dependent classes:

- Quote classes depend on `ui-article-main__quote` and should not be documented as a standalone callout.
- Principle item classes depend on `ui-article-main__principles`.
- Comment classes form an internal comments pattern and should not become standalone public comments without a separate contract.
- `ui-article-main__tag` is article-specific today, even though `ui-tag-list` exists.
- `ui-article-main__meta` is comment metadata today, not the same contract as `ui-meta-list`.

Dependencies:

- Material Symbols if using `ui-article-main__quote-icon`.
- Images for figures and avatars when those zones are used.
- `src/components/article/ui-article-main/ui-article-main.scss`
- Usually composed with `ui-article-hero`, `ui-article-sidebar`, and `ui-article-related`, but it can be displayed alone.

Responsive:

- The component is fluid and should receive its reading width from the parent layout.
- Figures and comments stack naturally within the article flow.
- Reply comments and dense metadata should be checked on narrow viewports.

Accessibility:

- Use semantic `article`.
- Preserve heading order according to the surrounding page.
- Use `blockquote` and `cite` for quoted material.
- Use real `figure` and `figcaption` for figures.
- Figure and avatar images need appropriate `alt` text.
- Comment reply controls should be real buttons with `type="button"` when they act in-page.
- Textarea controls need a visible label or accessible name.

Relationship with newer primitives:

- `ui-tag-list` could eventually replace `ui-article-main__tags`, but only after a visual and contract migration.
- `ui-meta-list` should not replace `ui-article-main__meta` yet because that class currently belongs to comments.
- `ui-callout` can be used inside article prose for notes, but it does not replace `ui-article-main__quote` or principles.
- `ui-code-block` and `ui-table` can be placed inside article content when the article includes technical material.
- `ui-toc` can live beside `ui-article-main`, commonly inside a sidebar column, but should not be nested into the article body by default.

Future extraction candidates:

- `ui-prose` for generic article text rhythm.
- `ui-quote` for reusable pull quotes.
- `ui-principle-list` or a more generic feature-list pattern.
- `ui-figure` for images and captions.
- `ui-comment` or `ui-comment-list` for the comments area.
- `ui-tag-list` adoption for article tags.

Isolated example:

```html
<article class="ui-article-main">
  <div class="ui-article-main__prose">
    <p class="ui-article-main__lead">
      A long-form article can use the SayUI prose rhythm without the full editorial page.
    </p>
    <h2 class="ui-article-main__title">Section title</h2>
    <p class="ui-article-main__paragraph">
      Supporting text.
    </p>
  </div>
</article>
```

Composition example:

```html
<main class="ui-editorial-page">
  <section class="ui-article-hero"></section>

  <div class="ui-editorial-page__layout">
    <article class="ui-article-main">
      <div class="ui-article-main__prose">
        <p class="ui-article-main__lead">Article introduction.</p>
      </div>
    </article>

    <aside class="ui-article-sidebar"></aside>
  </div>
</main>
```

