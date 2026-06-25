# ui-main-header

Purpose: public header area for the `ui-main` ecosystem. It introduces a content listing with a heading and optional filter controls.

When to use: use inside `ui-main`, above `ui-main__grid`, when a listing needs a title and simple filter actions.

When not to use: do not use as a global page header, standalone toolbar, tabs system, or generic filter primitive outside the `ui-main` composition.

HTML minimum:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>
</div>
```

Recommended structure:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>

  <div class="ui-main__filters" aria-label="Filter stories">
    <button class="ui-main__filter-button" type="button">All</button>
    <button class="ui-main__filter-button" type="button">Design</button>
    <button class="ui-main__filter-button" type="button">Tech</button>
  </div>
</div>
```

Required classes:

- `ui-main__header-row`
- `ui-main__heading`

Optional classes:

- `ui-main__filters`
- `ui-main__filter-button`

Public/internal status:

- Public within the `ui-main` ecosystem.
- Not a global primitive yet.
- The classes intentionally use the `ui-main__*` namespace because this header belongs to the main listing composition.

Class responsibilities:

- `ui-main__header-row`: arranges the heading and filter area.
- `ui-main__heading`: styles the section title for the listing.
- `ui-main__filters`: groups the filter controls.
- `ui-main__filter-button`: styles each filter action.

Dependencies:

- `ui-main`
- `src/components/ui-main-header/ui-main-header.scss`
- Often composed with `ui-post-grid` and `ui-post-card`.

Responsive:

- Does not define a standalone responsive system.
- It inherits available width from `ui-main`.
- Filter controls should be allowed to wrap or be simplified by the consumer if many filters are added.

Accessibility:

- Use real `button type="button"` elements for in-page filtering.
- If a button represents the active filter, consumers should add an accessible state such as `aria-pressed="true"`.
- If the filter group needs extra context, add an accessible label to `ui-main__filters`.

Relationship with newer primitives:

- `ui-tag-list` could inspire a future filter primitive, but it does not replace `ui-main__filters` today.
- `ui-meta-list`, `ui-callout`, and `ui-toc` are not direct internals of this component.

Future extraction candidates:

- `ui-filter-bar`
- `ui-filter-button`
- `ui-section-header`

These candidates do not exist yet. Do not rename or migrate `ui-main__filters` without a future approved contract.

Example:

```html
<div class="ui-main">
  <div class="ui-main__header-row">
    <h3 class="ui-main__heading">Latest Stories</h3>
    <div class="ui-main__filters" aria-label="Filter stories">
      <button class="ui-main__filter-button" type="button" aria-pressed="true">All</button>
      <button class="ui-main__filter-button" type="button">Design</button>
    </div>
  </div>
</div>
```
