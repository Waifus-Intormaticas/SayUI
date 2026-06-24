# ui-article-sidebar

Purpose: public editorial sidebar for article pages. It combines author context, social links, related stories, and a tag cloud in one composed component.

When to use: use beside `ui-article-main` in an editorial/article layout, or as a standalone article support panel in a consumer project.

When not to use: do not use as a generic site sidebar, table of contents, primary navigation, newsletter block, or standalone author card unless the full composition is desired.

HTML minimum:

```html
<aside class="ui-article-sidebar">
  <div class="ui-article-sidebar__card"></div>
</aside>
```

Recommended structure:

```html
<aside class="ui-article-sidebar">
  <div class="ui-article-sidebar__card">
    <div class="ui-article-sidebar__author">
      <div class="ui-article-sidebar__avatar-container">
        <img class="ui-article-sidebar__avatar" src="author.jpg" alt="Elena Valery">
      </div>

      <div class="ui-article-sidebar__author-info">
        <h4 class="ui-article-sidebar__author-name">Elena Valery</h4>
        <p class="ui-article-sidebar__author-role">Senior Design Editor</p>
      </div>
    </div>

    <p class="ui-article-sidebar__description">
      Elena writes about cognitive psychology, typography, and interface craft.
    </p>

    <div class="ui-article-sidebar__social" aria-label="Author links">
      <a class="ui-article-sidebar__social-link" href="mailto:elena@example.com" aria-label="Email Elena Valery">
        <span class="material-symbols-outlined" aria-hidden="true">alternate_email</span>
      </a>
      <a class="ui-article-sidebar__social-link" href="https://example.com/elena" aria-label="Visit Elena Valery website">
        <span class="material-symbols-outlined" aria-hidden="true">public</span>
      </a>
    </div>

    <div class="ui-article-sidebar__section">
      <h5 class="ui-article-sidebar__section-title">Related Stories</h5>

      <ul class="ui-article-sidebar__list">
        <li class="ui-article-sidebar__item">
          <a class="ui-article-sidebar__link" href="/articles/light-phone">
            <span class="ui-article-sidebar__category">Tech</span>
            <p class="ui-article-sidebar__item-title">Hardware for the Distracted</p>
          </a>
        </li>

        <li class="ui-article-sidebar__item ui-article-sidebar__item-space">
          <a class="ui-article-sidebar__link" href="/articles/neumorphism">
            <span class="ui-article-sidebar__category">Culture</span>
            <p class="ui-article-sidebar__item-title">The Return of Neumorphism</p>
          </a>
        </li>
      </ul>
    </div>

    <div class="ui-article-sidebar__section-teme">
      <h5 class="ui-article-sidebar__section-title">Category Cloud</h5>

      <div class="ui-article-sidebar__tags">
        <a class="ui-article-sidebar__tag" href="/categories/architecture">Architecture</a>
        <a class="ui-article-sidebar__tag" href="/categories/sustainability">Sustainability</a>
      </div>
    </div>
  </div>
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
- `ui-article-sidebar__section-title`
- `ui-article-sidebar__list`
- `ui-article-sidebar__item`
- `ui-article-sidebar__item-space`
- `ui-article-sidebar__link`
- `ui-article-sidebar__category`
- `ui-article-sidebar__item-title`
- `ui-article-sidebar__section-teme`
- `ui-article-sidebar__tags`
- `ui-article-sidebar__tag`

Public/internal status:

- Public editorial composed component.
- The full component is public.
- Its internal zones are documented as part of the current contract, but they are not standalone components yet.

Internal zones:

- Author block: `ui-article-sidebar__author`, avatar, author info, name, role, and description.
- Social links: `ui-article-sidebar__social` and `ui-article-sidebar__social-link`.
- Related stories: `ui-article-sidebar__section`, list, item, link, category, and item title.
- Tag cloud: `ui-article-sidebar__section-teme`, `ui-article-sidebar__tags`, and `ui-article-sidebar__tag`.

Naming note:

- `ui-article-sidebar__section-teme` is a confusing name, but it is part of the current contract.
- Do not rename it without a future versioned decision and migration plan.

Dependencies:

- Material Symbols if social icons are used.
- Images if the author avatar is used.
- `src/components/article/ui-article-sidebar/ui-article-sidebar.scss`
- Usually composed with `ui-article-main` and `ui-article-hero`.

Responsive:

- Works best in an article sidebar column.
- Can be shown in a narrow demo wrapper when isolated.
- Related items and tag cloud should wrap naturally inside the card width.

Accessibility:

- Use `aside` when the sidebar is complementary to the article.
- Avatar images need meaningful `alt` text when they identify the author.
- Icon-only social links need accessible names.
- Related story links should have meaningful text.
- Tag links should use real `href` destinations.

Relationship with newer primitives:

- `ui-tag-list` could eventually replace the tag cloud, but it does not replace `ui-article-sidebar__tags` today.
- `ui-meta-list` could support future related-story metadata, but there is no current migration.
- `ui-callout` should not replace the author block or related stories.
- `ui-toc` can coexist in the same article sidebar column, but it should not depend on `ui-article-sidebar`.

Future extraction candidates:

- `ui-author-card`
- `ui-related-list`
- `ui-social-links`
- adoption of `ui-tag-list` for tag cloud markup

These are candidates only. Do not split or migrate the current component without an approved contract.

Example:

```html
<aside class="ui-article-sidebar">
  <div class="ui-article-sidebar__card">
    <div class="ui-article-sidebar__author">
      <div class="ui-article-sidebar__author-info">
        <h4 class="ui-article-sidebar__author-name">Elena Valery</h4>
        <p class="ui-article-sidebar__author-role">Senior Design Editor</p>
      </div>
    </div>
  </div>
</aside>
```
