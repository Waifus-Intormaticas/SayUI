# ui-callout

Purpose: reusable highlighted block for editorial and technical notes.

When to use: use for notes, tips, warnings, documentation guidance, contextual messages, and optional actions inside articles, docs, sidebars, or grids.

When not to use: do not use for quotes, newsletters, toast messages, modals, dismissible alerts, post cards, or numbered principle lists.

HTML minimum:

```html
<aside class="ui-callout">
  <p class="ui-callout__content">
    This is an important note.
  </p>
</aside>
```

Recommended structures:

```html
<aside class="ui-callout" aria-labelledby="callout-title">
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-title">Before you continue</h3>
    <p class="ui-callout__content">
      Make sure your compiled CSS is imported before using SayUI classes.
    </p>
  </div>
</aside>
```

```html
<aside class="ui-callout ui-callout--tip" aria-labelledby="callout-tip-title">
  <span class="ui-callout__icon" aria-hidden="true">i</span>
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-tip-title">Tip</h3>
    <p class="ui-callout__content">
      Use semantic HTML first, then apply SayUI classes.
    </p>
  </div>
</aside>
```

```html
<aside class="ui-callout ui-callout--info" aria-labelledby="callout-docs-title">
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-docs-title">Documentation note</h3>
    <p class="ui-callout__content">
      This component works without JavaScript.
    </p>
    <div class="ui-callout__actions">
      <a class="ui-callout__link" href="/guidelines">Read the guidelines</a>
    </div>
  </div>
</aside>
```

Required classes:

- `ui-callout`
- `ui-callout__content`

Optional classes:

- `ui-callout__icon`
- `ui-callout__body`
- `ui-callout__title`
- `ui-callout__link`
- `ui-callout__actions`
- `ui-callout__action`
- `ui-callout--info`
- `ui-callout--tip`
- `ui-callout--warning`
- `ui-callout--danger`
- `ui-callout--success`
- `ui-callout--compact`
- `ui-callout--strong`
- `ui-callout--inline`

Dependencies:

- No JavaScript required.
- No external icon dependency.
- `src/components/ui-callout/ui-callout.scss`

Responsive:

- Fluid by default.
- Works inside articles, documentation pages, sidebars, and grids.
- Stacks icon and body on very narrow screens.
- `ui-callout--compact` is better for dense sidebars.
- `ui-callout--inline` is intended for short inline notes.

Accessibility:

- Use `aside` for complementary content.
- Use `div` if the message is part of the direct reading flow.
- Do not use `role="alert"` unless the message is dynamic or genuinely critical.
- Decorative icons need `aria-hidden="true"`.
- Use links for navigation.
- Use buttons only for actions in the current page.
- Links and actions keep visible focus.

Example:

```html
<aside class="ui-callout ui-callout--warning" aria-labelledby="callout-warning-title">
  <span class="ui-callout__icon" aria-hidden="true">!</span>
  <div class="ui-callout__body">
    <h3 class="ui-callout__title" id="callout-warning-title">Check first</h3>
    <p class="ui-callout__content">
      Confirm the expected markup before copying this pattern.
    </p>
  </div>
</aside>
```

