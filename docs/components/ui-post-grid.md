# ui-post-grid

Purpose: public layout helper inside `ui-main` for grouping `ui-post-card` items and an optional load-more action.

When to use: use inside `ui-main` when rendering a collection of post or article cards.

When not to use: do not use as a generic grid primitive, product grid, dashboard grid, masonry layout, or arbitrary layout utility.

HTML minimum:

```html
<div class="ui-main__grid"></div>
```

Recommended structure:

```html
<div class="ui-main__grid">
  <article class="ui-post-card">
    <div class="ui-post-card__content">
      <h4 class="ui-post-card__title">Post title</h4>
    </div>
  </article>

  <article class="ui-post-card">
    <div class="ui-post-card__content">
      <h4 class="ui-post-card__title">Another post title</h4>
    </div>
  </article>
</div>

<div class="ui-main__more">
  <button class="ui-main__more-button" type="button">More</button>
</div>
```

Required classes:

- `ui-main__grid`

Optional classes:

- `ui-main__more`
- `ui-main__more-button`

Public/internal status:

- Public within the `ui-main` ecosystem.
- It is a helper/layout contract for post cards.
- It is not a generic `ui-grid` primitive yet.

Class responsibilities:

- `ui-main__grid`: creates the card listing area.
- `ui-main__more`: holds the optional follow-up action after the listing.
- `ui-main__more-button`: styles the load-more or more-content control.

Dependencies:

- `ui-main`
- `ui-post-card`
- `src/components/ui-post-grid/ui-post-grid.scss`

Responsive:

- One column by default.
- Two columns from the current medium breakpoint behavior.
- The parent `ui-main` controls the available width and composition context.

Accessibility:

- `ui-main__more-button` should be a real `button type="button"` when it loads or reveals content in place.
- Use a link instead if the action navigates to an archive page.
- Consumer projects are responsible for announcing dynamically loaded content if they add JavaScript.

Relationship with newer primitives:

- `ui-meta-list` can be used inside `ui-post-card`, but the grid should not manage metadata.
- `ui-tag-list` can live in cards or filter areas, but it does not replace the grid.
- `ui-callout` could be placed near a listing, but it is not a grid item by default.
- `ui-toc` is unrelated to this component.

Future extraction candidates:

- `ui-card-grid`
- `ui-load-more`
- a generic `ui-grid`

These candidates should be designed separately. Do not rename `ui-main__grid` to a generic grid until the contract exists.

Example:

```html
<div class="ui-main">
  <div class="ui-main__grid">
    <article class="ui-post-card">
      <div class="ui-post-card__content">
        <h4 class="ui-post-card__title">Post title</h4>
      </div>
    </article>
  </div>

  <div class="ui-main__more">
    <button class="ui-main__more-button" type="button">More</button>
  </div>
</div>
```
