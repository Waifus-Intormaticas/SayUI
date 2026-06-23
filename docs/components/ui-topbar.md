# ui-topbar

Purpose: primary top navigation for the main page.

When to use: use at the top of `ui-page`.

HTML minimum:

```html
<header class="ui-topbar">
  <div class="ui-topbar__inner"></div>
</header>
```

Required classes:

- `ui-topbar`
- `ui-topbar__inner`

Optional classes:

- `ui-topbar__left`
- `ui-topbar__brand`
- `ui-topbar__logo`
- `ui-topbar__nav`
- `ui-topbar__link`
- `ui-topbar__actions`
- `ui-topbar__search-button`
- `ui-topbar__search-icon`
- `ui-topbar__subscribe-button`
- `ui-topbar__menu-button`
- `ui-topbar__menu-icon`
- `ui-topbar__mobile-nav`

Dependencies:

- Material Symbols for icons when used.
- `src/components/ui-topbar/ui-topbar.scss`

Responsive:

- Desktop nav is hidden at smaller sizes.
- Mobile nav is shown through the CSS focus pattern on the menu button.

Accessibility:

- Icon-only buttons need `aria-label`.
- Brand links should include an `href` in production markup.
- Menu behavior is CSS-only; consumer projects can enhance it with their own JavaScript if needed.

Example:

```html
<header class="ui-topbar">
  <div class="ui-topbar__inner">
    <a class="ui-topbar__brand" href="#">Brand</a>
  </div>
</header>
```

