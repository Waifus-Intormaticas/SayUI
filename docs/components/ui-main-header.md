# ui-main-header

Purpose: header row and filters for the `ui-main` ecosystem.

When to use: use inside `ui-main` above `ui-main__grid`.

HTML minimum:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>
</div>
```

Required classes:

- `ui-main__header-row`
- `ui-main__heading`

Optional classes:

- `ui-main__filters`
- `ui-main__filter-button`

Dependencies:

- `ui-main`

Responsive:

- No dedicated breakpoint.

Accessibility:

- If filter buttons change content, consumer projects should expose selected state with `aria-pressed` or another appropriate pattern.

Example:

```html
<div class="ui-main__header-row">
  <h3 class="ui-main__heading">Latest Stories</h3>
  <div class="ui-main__filters">
    <button class="ui-main__filter-button">All</button>
  </div>
</div>
```

