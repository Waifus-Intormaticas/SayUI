# ui-footer

Purpose: general footer for the main page.

When to use: use at the bottom of `ui-page`.

HTML minimum:

```html
<footer class="ui-footer">
  <div class="ui-footer__inner"></div>
</footer>
```

Required classes:

- `ui-footer`
- `ui-footer__inner`

Optional classes:

- `ui-footer__header`
- `ui-footer__brand`
- `ui-footer__icon-box`
- `ui-footer__brand-icon`
- `ui-footer__title`
- `ui-footer__socials`
- `ui-footer__social-link`
- `ui-footer__social-icon`
- `ui-footer__grid`
- `ui-footer__column`
- `ui-footer__column-title`
- `ui-footer__link`
- `ui-footer__legend`

Dependencies:

- Material Symbols if using footer icons.

Responsive:

- Footer columns use 2 columns by default and 4 columns from 768px.

Accessibility:

- Social links should have accessible labels.
- Footer navigation should use real links.

Example:

```html
<footer class="ui-footer">
  <div class="ui-footer__inner">
    <div class="ui-footer__legend">Copyright</div>
  </div>
</footer>
```

