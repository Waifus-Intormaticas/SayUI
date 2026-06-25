# ui-tag-list

Purpose: reusable list of tags, categories, topics, or simple filters.

When to use: use for article tags, category clouds, compact topic lists, and category lists with optional counts.

When not to use: do not use for primary navigation, breadcrumbs, related-story lists, tabs with panels, or complex removable chips.

HTML minimum:

```html
<ul class="ui-tag-list" aria-label="Tags">
  <li class="ui-tag-list__item">
    <span class="ui-tag-list__tag">JavaScript</span>
  </li>
</ul>
```

Recommended structures:

```html
<ul class="ui-tag-list" aria-label="Categories">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/css">CSS</a>
  </li>
</ul>
```

```html
<ul class="ui-tag-list ui-tag-list--interactive" aria-label="Filter by topic">
  <li class="ui-tag-list__item">
    <button class="ui-tag-list__tag ui-tag-list__tag--active" type="button" aria-pressed="true">
      Design
    </button>
  </li>
</ul>
```

```html
<ul class="ui-tag-list ui-tag-list--with-count" aria-label="Categories">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/design">
      <span class="ui-tag-list__label">Design</span>
      <span class="ui-tag-list__count" aria-label="12 articles">12</span>
    </a>
  </li>
</ul>
```

Required classes:

- `ui-tag-list`
- `ui-tag-list__item`
- `ui-tag-list__tag`

Optional classes:

- `ui-tag-list__label`
- `ui-tag-list__count`
- `ui-tag-list--compact`
- `ui-tag-list--inline`
- `ui-tag-list--stacked`
- `ui-tag-list--with-count`
- `ui-tag-list--interactive`
- `ui-tag-list__tag--active`
- `ui-tag-list__tag--disabled`

Dependencies:

- No JavaScript required.
- No icon dependency.
- `src/components/ui-tag-list/ui-tag-list.scss`

Responsive:

- Wraps by default.
- `ui-tag-list--stacked` creates a full-width vertical list suitable for sidebars.
- `ui-tag-list--compact` reduces spacing for dense areas.

## Official Vertical Category Composition

SayUI does not include `ui-category-list` in v1. The current flat category-navigation case is covered by composing `ui-tag-list` with its stacked and counted options.

```html
<ul
  class="ui-tag-list ui-tag-list--stacked ui-tag-list--with-count"
  aria-label="Categories"
>
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/architecture">
      <span class="ui-tag-list__label">Architecture</span>
      <span class="ui-tag-list__count" aria-label="12 articles">12</span>
    </a>
  </li>

  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/editorial-design">
      <span class="ui-tag-list__label">Editorial Design</span>
      <span class="ui-tag-list__count" aria-label="45 articles">45</span>
    </a>
  </li>

  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/typography">
      <span class="ui-tag-list__label">Typography</span>
      <span class="ui-tag-list__count" aria-label="31 articles">31</span>
    </a>
  </li>
</ul>
```

Use this composition for:

- Simple navigation by category.
- Sidebar category groups.
- Flat taxonomies.
- Categories with article or resource counts.

Do not use this composition for:

- Hierarchical category trees.
- Complex active-filter systems.
- Primary navigation.
- Expandable or collapsible categories.
- Tags without counts when the base `ui-tag-list` already covers the requirement.

`ui-sidebar__categories` remains part of the current public `ui-sidebar` contract. This composition documents the recommended approach for new generic category lists; it does not migrate or replace the existing sidebar pattern.

Accessibility:

- Use `ul > li > span` for informational tags.
- Use `ul > li > a` when each tag navigates.
- Use `ul > li > button type="button"` when tags filter content in place.
- Use `aria-current="page"` for active links.
- Use `aria-pressed="true"` for active filter buttons.
- Add `aria-label` to the list when context is not obvious.
- For disabled tags, prefer `span`.
- If using `a`, remove `href` while disabled.
- Do not use active links with `aria-disabled="true"`.

Example:

```html
<ul class="ui-tag-list ui-tag-list--interactive" aria-label="Topics">
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/design">Design</a>
  </li>
  <li class="ui-tag-list__item">
    <a class="ui-tag-list__tag" href="/categories/accessibility">Accessibility</a>
  </li>
</ul>
```

