# ui-footer-editorial

Purpose: editorial footer for secondary/article pages.

When to use: use after `ui-editorial-page`.

HTML minimum:

```html
<footer class="ui-footer-editorial">
  <div class="ui-footer-editorial__container"></div>
</footer>
```

Required classes:

- `ui-footer-editorial`
- `ui-footer-editorial__container`

Optional classes:

- `ui-footer-editorial__top`
- `ui-footer-editorial__brand`
- `ui-footer-editorial__logo`
- `ui-footer-editorial__tagline`
- `ui-footer-editorial__nav`
- `ui-footer-editorial__link`
- `ui-footer-editorial__bottom`
- `ui-footer-editorial__copyright`
- `ui-footer-editorial__social`
- `ui-footer-editorial__social-item`
- `ui-footer-editorial__icon`

Dependencies:

- Material Symbols if using social icons.

Responsive:

- Stacked by default.
- Top and bottom groups become rows from 768px.

Accessibility:

- If social icons are interactive, prefer links or buttons with accessible labels.

Example:

```html
<footer class="ui-footer-editorial">
  <div class="ui-footer-editorial__container">
    <div class="ui-footer-editorial__brand">
      <span class="ui-footer-editorial__logo">Brand</span>
    </div>
  </div>
</footer>
```

