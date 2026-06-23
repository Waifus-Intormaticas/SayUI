# ui-eyebrow

Purpose: small editorial label for a single contextual category, short non-critical status, or decorative/contextual label near a title, card, preview, or content block.

When to use: use for one editorial label, category, or short contextual marker.

When not to use: do not use for multiple tags, filters, badges with counts, secondary metadata, section headers, titles, nav links, author badges, or complete category lists.

HTML minimum:

```html
<span class="ui-eyebrow">Design</span>
```

As a link:

```html
<a class="ui-eyebrow" href="/categories/design">
  Design
</a>
```

Compact:

```html
<span class="ui-eyebrow ui-eyebrow--compact">
  Tech
</span>
```

Muted:

```html
<span class="ui-eyebrow ui-eyebrow--muted">
  Sponsored
</span>
```

Accent:

```html
<span class="ui-eyebrow ui-eyebrow--accent">
  Featured Story
</span>
```

Editorial:

```html
<span class="ui-eyebrow ui-eyebrow--editorial">
  Color Theory
</span>
```

Underline:

```html
<a class="ui-eyebrow ui-eyebrow--underline" href="/categories/development">
  Development
</a>
```

Required classes:

- `ui-eyebrow`

Optional classes:

- `ui-eyebrow--compact`
- `ui-eyebrow--muted`
- `ui-eyebrow--accent`
- `ui-eyebrow--editorial`
- `ui-eyebrow--underline`

Rules:

- Base `ui-eyebrow` uses the primary/accent color by default.
- `ui-eyebrow--accent` adds an extra visual signal with a border/underline treatment, not color alone.
- `ui-eyebrow--editorial` preserves the wider tracking used by original banner and post-card labels.
- `ui-eyebrow--underline` preserves the underlined editorial category treatment used by article hero and related content.
- Use `a.ui-eyebrow` for category links.
- There is no `ui-eyebrow--link` modifier.
- Do not use `button` for this component.
- Do not use `ui-eyebrow` as a replacement for tags, metadata, or section headers.

Dependencies:

- No JavaScript required.
- No external icon dependency.
- `src/components/ui-eyebrow/ui-eyebrow.scss`

Responsive:

- Inline by default.
- Does not impose width.
- Allows natural wrapping for long labels.
- `ui-eyebrow--compact` is intended for dense cards and sidebars.

Accessibility:

- Use `span` for informational labels.
- Use `a href` when the label navigates.
- Do not use `button`.
- Do not use as a heading.
- Do not rely on `ui-eyebrow` for critical state communication.

Relationship with existing components:

- Inspired by `ui-banner__eyebrow`, `ui-post-card__eyebrow`, `ui-article-hero__eyebrow`, `ui-article-related__category`, and `ui-article-sidebar__category`.
- Does not replace existing component internals automatically.
- Do not migrate existing components without a future approved contract.

Relationship with primitives:

- Use `ui-tag-list` for multiple tags, filters, and tag collections.
- Use `ui-meta-list` for date, author, reading time, views, and other metadata.
- Use `ui-section-header` for section headings.

Example:

```html
<article>
  <a class="ui-eyebrow ui-eyebrow--accent" href="/categories/design">Design</a>
  <h2>Editorial systems for quiet interfaces</h2>
</article>
```
