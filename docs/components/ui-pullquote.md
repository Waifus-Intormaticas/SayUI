# ui-pullquote

Purpose: reusable editorial pullquote for highlighted phrases and quoted passages.

When to use: use for standout editorial quotes, memorable phrases inside articles, and quotes with an optional visible source.

When not to use: do not use for notes, warnings, tips, technical callouts, testimonials, user comments, author cards, numbered principles, or newsletters.

HTML minimum:

```html
<blockquote class="ui-pullquote">
  <p class="ui-pullquote__content">
    Minimalism is not absence. It is the right amount of signal.
  </p>
</blockquote>
```

With cite:

```html
<blockquote class="ui-pullquote">
  <p class="ui-pullquote__content">
    Minimalism is not the absence of something. It is the perfect amount of something.
  </p>

  <cite class="ui-pullquote__cite">
    Editorial Design Principles, 2024
  </cite>
</blockquote>
```

Decorated:

```html
<blockquote class="ui-pullquote ui-pullquote--decorated">
  <span class="ui-pullquote__mark" aria-hidden="true">&ldquo;</span>

  <p class="ui-pullquote__content">
    Motion is the why and where of the interface.
  </p>

  <cite class="ui-pullquote__cite">
    Elena Valery
  </cite>
</blockquote>
```

Compact:

```html
<blockquote class="ui-pullquote ui-pullquote--compact">
  <p class="ui-pullquote__content">
    Good editorial rhythm is quiet but deliberate.
  </p>
</blockquote>
```

Strong:

```html
<blockquote class="ui-pullquote ui-pullquote--strong">
  <p class="ui-pullquote__content">
    A strong pullquote should add emphasis without becoming a callout.
  </p>
</blockquote>
```

Editorial:

```html
<blockquote class="ui-pullquote ui-pullquote--decorated ui-pullquote--editorial">
  <span class="ui-pullquote__mark" aria-hidden="true">&ldquo;</span>

  <p class="ui-pullquote__content">
    Design systems become memorable when their rhythm feels intentional.
  </p>

  <cite class="ui-pullquote__cite">
    SayUI editorial notes
  </cite>
</blockquote>
```

Required classes:

- `ui-pullquote`
- `ui-pullquote__content`

Optional classes:

- `ui-pullquote__cite`
- `ui-pullquote__mark`
- `ui-pullquote--compact`
- `ui-pullquote--strong`
- `ui-pullquote--decorated`
- `ui-pullquote--editorial`

Public contract:

- The root element must be `blockquote`.
- `ui-pullquote__content` is required.
- `ui-pullquote__cite` is optional and should only be used when a visible source exists.
- `ui-pullquote__mark` is decorative text owned by the component, not an external icon.
- `ui-pullquote--decorated` requires `ui-pullquote__mark`.
- `ui-pullquote--editorial` preserves the larger article quote rhythm from the original article body pattern.

Dependencies:

- No JavaScript required.
- No icon set required.
- No syntax highlighter or framework dependency.
- `src/components/ui-pullquote/ui-pullquote.scss`

Responsive:

- Fluid by default.
- Works inside article bodies, editorial pages, documentation pages, and grid content.
- Mobile spacing and type scale are reduced to keep the quote readable.

Accessibility:

- Always use `blockquote`.
- Use `cite` only when there is a visible source.
- Decorative marks need `aria-hidden="true"`.
- Do not add roles unless a consuming project has a specific semantic need.
- Do not use this component for critical, dynamic, or instructional messages. Use `ui-callout` for that.

Relationship with other components:

- `ui-callout` is for contextual notes, warnings, tips, and technical messages.
- `ui-pullquote` is for editorial quotation and emphasis.
- `ui-article-main__quote` can coexist with `ui-pullquote`; do not migrate it without an approved adoption plan.

Example:

```html
<blockquote class="ui-pullquote ui-pullquote--decorated">
  <span class="ui-pullquote__mark" aria-hidden="true">&ldquo;</span>
  <p class="ui-pullquote__content">
    Editorial rhythm is strongest when emphasis is intentional.
  </p>
  <cite class="ui-pullquote__cite">SayUI editorial notes</cite>
</blockquote>
```
