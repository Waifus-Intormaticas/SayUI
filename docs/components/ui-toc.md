# ui-toc

Purpose: reusable table of contents for long articles, documentation, guides, and pages with internal sections.

When to use: use for in-page navigation that links to real headings.

When not to use: do not use for primary navigation, breadcrumbs, tabs, filters, pagination, related posts, or automated scrollspy.

HTML minimum:

```html
<nav class="ui-toc" aria-label="Table of contents">
  <ol class="ui-toc__list">
    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#introduction">Introduction</a>
    </li>
  </ol>
</nav>
```

Recommended structure:

```html
<nav class="ui-toc" aria-labelledby="toc-title">
  <h2 class="ui-toc__title" id="toc-title">On this page</h2>

  <ol class="ui-toc__list">
    <li class="ui-toc__item">
      <a class="ui-toc__link ui-toc__link--active" href="#overview" aria-current="location">
        Overview
      </a>
    </li>

    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#installation">Installation</a>

      <ol class="ui-toc__list ui-toc__list--nested">
        <li class="ui-toc__item">
          <a class="ui-toc__link" href="#requirements">Requirements</a>
        </li>
      </ol>
    </li>
  </ol>
</nav>
```

Required classes:

- `ui-toc`
- `ui-toc__list`
- `ui-toc__item`
- `ui-toc__link`

Optional classes:

- `ui-toc__title`
- `ui-toc__list--nested`
- `ui-toc__item--active`
- `ui-toc__link--active`
- `ui-toc--compact`
- `ui-toc--boxed`
- `ui-toc--sticky`

Dependencies:

- No JavaScript required.
- No scrollspy included.
- No external icon dependency.
- `src/components/ui-toc/ui-toc.scss`

Responsive:

- Base component is fluid and can live inside sidebars or content columns.
- `ui-toc__list--nested` indents nested sections without requiring extra depth classes.
- `ui-toc--boxed` adds its own visual container.
- `ui-toc--sticky` only becomes sticky from the medium breakpoint; on mobile it remains a normal block.

Accessibility:

- Use `nav`.
- Use `aria-label` when there is no visible title.
- Use `aria-labelledby` when using `ui-toc__title`.
- Links must point to real heading IDs.
- Use `aria-current="location"` only on the active link.
- Active state is manual; SayUI does not implement scrollspy.
- Use links, not buttons, for section navigation.
- Links keep visible focus.

Example:

```html
<nav class="ui-toc ui-toc--boxed ui-toc--sticky" aria-labelledby="toc-example-title">
  <h2 class="ui-toc__title" id="toc-example-title">On this page</h2>
  <ol class="ui-toc__list">
    <li class="ui-toc__item ui-toc__item--active">
      <a class="ui-toc__link ui-toc__link--active" href="#overview" aria-current="location">Overview</a>
    </li>
    <li class="ui-toc__item">
      <a class="ui-toc__link" href="#usage">Usage</a>
    </li>
  </ol>
</nav>
```

