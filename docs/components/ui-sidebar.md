# ui-sidebar

Purpose: composed sidebar for secondary editorial content: trending links, category links with counts, and a newsletter signup block.

When to use: use beside `ui-main`, inside editorial layouts, or in any consumer page that needs a complete secondary column.

When not to use: do not use for primary navigation, table of contents, article author bio, related-card grids, or a single newsletter block unless the complete sidebar composition is wanted.

HTML minimum:

```html
<aside class="ui-sidebar">
  <section>
    <h4 class="ui-sidebar__section-title">Categories</h4>
  </section>
</aside>
```

Recommended complete structure:

```html
<aside class="ui-sidebar">
  <section>
    <h4 class="ui-sidebar__section-title">Trending Now</h4>
    <div class="ui-sidebar__trending-list">
      <a href="/articles/grid-systems" class="ui-sidebar__trending-item">
        <div class="ui-sidebar__thumb-wrapper">
          <img src="thumb.jpg" alt="Article thumbnail" class="ui-sidebar__thumb">
        </div>
        <div>
          <h5 class="ui-sidebar__item-title">10 Grid Systems Every Designer Should Master</h5>
          <span class="ui-sidebar__item-meta">48k Views</span>
        </div>
      </a>
    </div>
  </section>

  <section>
    <h4 class="ui-sidebar__section-title">Categories</h4>
    <div class="ui-sidebar__categories">
      <a href="/categories/architecture" class="ui-sidebar__category-link">
        <span class="ui-sidebar__category-title">Architecture</span>
        <span class="ui-sidebar__count-badge">
          <span class="ui-sidebar__count-text">12</span>
        </span>
      </a>
    </div>
  </section>

  <section class="ui-sidebar__newsletter" aria-labelledby="sidebar-newsletter-title">
    <span class="material-symbols-outlined ui-sidebar__newsletter-icon" aria-hidden="true">mail</span>
    <h4 class="ui-sidebar__newsletter-title" id="sidebar-newsletter-title">The Weekly Digest</h4>
    <p class="ui-sidebar__newsletter-text">
      Get selected stories delivered to your inbox.
    </p>
    <form class="ui-sidebar__form">
      <input class="ui-sidebar__input" type="email" aria-label="Email address" placeholder="Your email address">
      <button class="ui-sidebar__submit" type="submit">Subscribe Now</button>
      <p class="ui-sidebar__form-note">No spam, ever. Unsubscribe anytime.</p>
    </form>
  </section>
</aside>
```

Required classes:

- `ui-sidebar`

Optional classes:

- `ui-sidebar__section-title`
- `ui-sidebar__trending-list`
- `ui-sidebar__trending-item`
- `ui-sidebar__thumb-wrapper`
- `ui-sidebar__thumb`
- `ui-sidebar__item-title`
- `ui-sidebar__item-meta`
- `ui-sidebar__categories`
- `ui-sidebar__category-link`
- `ui-sidebar__category-title`
- `ui-sidebar__count-badge`
- `ui-sidebar__count-text`
- `ui-sidebar__newsletter`
- `ui-sidebar__newsletter-icon`
- `ui-sidebar__newsletter-title`
- `ui-sidebar__newsletter-text`
- `ui-sidebar__form`
- `ui-sidebar__input`
- `ui-sidebar__submit`
- `ui-sidebar__form-note`

Internal or composition-dependent classes:

- `ui-sidebar__trending-item`, `ui-sidebar__thumb-wrapper`, `ui-sidebar__thumb`, `ui-sidebar__item-title`, and `ui-sidebar__item-meta` belong to the trending-list pattern.
- `ui-sidebar__category-link`, `ui-sidebar__category-title`, `ui-sidebar__count-badge`, and `ui-sidebar__count-text` belong to the categories pattern.
- `ui-sidebar__newsletter-*` classes belong to the newsletter composition and should not be treated as a standalone public primitive yet.

Dependencies:

- Material Symbols if using the newsletter icon.
- `src/components/ui-sidebar/ui-sidebar.scss`
- Works best inside a layout that gives it an appropriate column width.

Responsive:

- Full width by default.
- 33.333333% width from 1024px.
- Can be shown in a narrow demo wrapper when presented as an isolated component.

Accessibility:

- Newsletter input should have a label or accessible name.
- Links need valid destinations.
- Use `aside` when the content is complementary to the main page.
- Use meaningful `alt` text for thumbnails when they add information, or empty `alt` if the linked text already describes the destination.
- Icon-only or icon-led elements need hidden decorative icons or accessible names, depending on whether they are interactive.
- Forms should use `type="email"` for email inputs and a real submit button.

Relationship with newer primitives:

- `ui-tag-list` could eventually replace the category cloud/count pattern, but the current sidebar contract keeps `ui-sidebar__categories`.
- `ui-meta-list` could eventually replace `ui-sidebar__item-meta`.
- `ui-callout` should not replace the newsletter block; newsletter has a distinct form contract.
- `ui-toc` may live near a sidebar or inside the same column in a consumer layout, but it should not depend on `ui-sidebar`.
- `ui-code-block` and `ui-table` are content components and should not be sidebar internals by default.

Future extraction candidates:

- `ui-newsletter` for the newsletter block.
- `ui-related-list` or `ui-trending-list` for compact linked stories.
- `ui-tag-list` adoption for categories with counts.
- `ui-meta-list` adoption for compact item metadata.

Isolated example:

```html
<aside class="ui-sidebar">
  <section>
    <h4 class="ui-sidebar__section-title">Categories</h4>
  </section>
</aside>
```

Composition example:

```html
<div class="ui-layout__content">
  <main class="ui-main"></main>

  <aside class="ui-sidebar">
    <section>
      <h4 class="ui-sidebar__section-title">Trending Now</h4>
    </section>
  </aside>
</div>
```

