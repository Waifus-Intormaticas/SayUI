# ui-section-header

Purpose: reusable header for content sections, listings, editorial blocks, and grouped content areas.

When to use: use for section headings that introduce a reusable block of content.

When not to use: do not use for filters, eyebrows, bylines, hero titles, card titles, technical component titles, TOC navigation, tabs, breadcrumbs, or toolbars.

HTML minimum:

```html
<header class="ui-section-header">
  <h2 class="ui-section-header__title">Latest Stories</h2>
</header>
```

Recommended structure:

```html
<header class="ui-section-header" aria-labelledby="section-title">
  <h2 class="ui-section-header__title" id="section-title">
    Latest Stories
  </h2>

  <p class="ui-section-header__description">
    Recent articles from the editorial desk.
  </p>
</header>
```

With divider:

```html
<header class="ui-section-header ui-section-header--inline ui-section-header--with-divider">
  <h2 class="ui-section-header__title">Read Next</h2>
  <span class="ui-section-header__divider" aria-hidden="true"></span>
</header>
```

Compact:

```html
<header class="ui-section-header ui-section-header--compact">
  <h3 class="ui-section-header__title">Categories</h3>
</header>
```

Required classes:

- `ui-section-header`
- `ui-section-header__title`

Optional classes:

- `ui-section-header__description`
- `ui-section-header__divider`
- `ui-section-header--compact`
- `ui-section-header--inline`
- `ui-section-header--with-divider`
- `ui-section-header--accent`

Rules:

- `ui-section-header--with-divider` requires an explicit `ui-section-header__divider` element.
- `ui-section-header--inline` can be used independently.
- `ui-section-header--accent` uses a left border, not color alone.
- Description is supported in v1.
- Actions, centered layout, color variants, hero variants, and card variants are not part of v1.

Dependencies:

- No JavaScript required.
- No external icon dependency.
- `src/components/ui-section-header/ui-section-header.scss`

Responsive:

- Base layout is vertical.
- `ui-section-header--inline` can wrap.
- The divider should not force horizontal overflow.
- `ui-section-header--compact` reduces scale and spacing for dense contexts.

Accessibility:

- Use a native heading element with the correct document level.
- Use `aria-labelledby` when the header container needs an explicit accessible name.
- `ui-section-header__divider` is decorative and should use `aria-hidden="true"`.
- Do not use `role="heading"` when a native heading is available.

Relationship with existing components:

- Can coexist with `ui-main-header`, `ui-sidebar`, `ui-article-sidebar`, `ui-article-related`, and `ui-article-main`.
- Does not replace existing component internals automatically.
- Do not migrate existing components without a future approved contract.

Example:

```html
<header class="ui-section-header ui-section-header--accent ui-section-header--compact">
  <h3 class="ui-section-header__title">Related topics</h3>
</header>
```
