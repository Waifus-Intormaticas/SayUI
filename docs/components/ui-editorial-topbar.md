# ui-editorial-topbar

Purpose: compact editorial navigation for article pages.

When to use: use above `ui-editorial-page`.

HTML minimum:

```html
<header class="ui-editorial-topbar">
  <div class="ui-editorial-topbar__inner"></div>
</header>
```

Required classes:

- `ui-editorial-topbar`
- `ui-editorial-topbar__inner`

Optional classes:

- `ui-editorial-topbar__left`
- `ui-editorial-topbar__brand`
- `ui-editorial-topbar__nav`
- `ui-editorial-topbar__link`
- `ui-editorial-topbar__actions`
- `ui-editorial-topbar__search-button`
- `ui-editorial-topbar__subscribe-button`

Dependencies:

- Material Symbols for search icon.
- `src/components/editorial-topbar/ui-editorial-topbar.scss`

Responsive:

- Nav is hidden by default and shown from 768px.

Accessibility:

- Search button needs `aria-label`.
- Links need meaningful destinations.

Example:

```html
<header class="ui-editorial-topbar">
  <div class="ui-editorial-topbar__inner">
    <a class="ui-editorial-topbar__brand" href="#">Crimson Courier</a>
  </div>
</header>
```

