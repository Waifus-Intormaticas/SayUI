# ui-post-grid

Purpose: post grid and load-more area for the `ui-main` ecosystem.

When to use: use inside `ui-main`.

HTML minimum:

```html
<div class="ui-main__grid"></div>
```

Required classes:

- `ui-main__grid`

Optional classes:

- `ui-main__more`
- `ui-main__more-button`

Dependencies:

- `ui-post-card`
- `ui-main`

Responsive:

- One column by default.
- Two columns from 768px.

Accessibility:

- Load-more buttons need a real action in consumer projects.

Example:

```html
<div class="ui-main__grid">
  <article class="ui-post-card"></article>
</div>
```

