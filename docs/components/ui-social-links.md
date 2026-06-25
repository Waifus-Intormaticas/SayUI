# ui-social-links

Purpose: public primitive for a small semantic list of social, contact, website, RSS, or editorial-channel links.

When to use: use for compact groups of navigable destinations in sidebars, footers, author areas, editorial modules, or standalone contact sections.

When not to use: do not use for share buttons, JavaScript actions, social login, follower counts, general navigation, complete author profiles, local actions, or toolbars.

## HTML Minimum

```html
<ul class="ui-social-links" aria-label="Social links">
  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="/contact">
      <span class="ui-social-links__label">Contact</span>
    </a>
  </li>
</ul>
```

## Icon-only Links

SayUI does not provide an icon pack. Consumers provide text, images, SVGs, or icons from their own system.

```html
<ul class="ui-social-links" aria-label="Follow us">
  <li class="ui-social-links__item">
    <a
      class="ui-social-links__link"
      href="https://social.example/sayui"
      aria-label="Follow SayUI on Example"
    >
      <span class="ui-social-links__icon" aria-hidden="true">EX</span>
    </a>
  </li>

  <li class="ui-social-links__item">
    <a
      class="ui-social-links__link"
      href="/feed.xml"
      aria-label="Subscribe to the RSS feed"
    >
      <span class="ui-social-links__icon" aria-hidden="true">RSS</span>
    </a>
  </li>
</ul>
```

## Email And Website

```html
<ul class="ui-social-links" aria-label="Contact and social links">
  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="mailto:hello@example.com">
      <span class="ui-social-links__label">Email</span>
    </a>
  </li>

  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="https://example.com">
      <span class="ui-social-links__label">Website</span>
    </a>
  </li>
</ul>
```

## Compact

```html
<ul class="ui-social-links ui-social-links--compact" aria-label="Editorial channels">
  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="/feed.xml">
      <span class="ui-social-links__label">RSS</span>
    </a>
  </li>

  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="/newsletter">
      <span class="ui-social-links__label">Newsletter</span>
    </a>
  </li>
</ul>
```

## Boxed

```html
<ul class="ui-social-links ui-social-links--boxed" aria-label="Author links">
  <li class="ui-social-links__item">
    <a
      class="ui-social-links__link"
      href="mailto:elena@example.com"
      aria-label="Email Elena Valery"
    >
      <span class="ui-social-links__icon" aria-hidden="true">@</span>
    </a>
  </li>

  <li class="ui-social-links__item">
    <a
      class="ui-social-links__link"
      href="https://example.com/elena"
      aria-label="Visit Elena Valery's website"
    >
      <span class="ui-social-links__icon" aria-hidden="true">www</span>
    </a>
  </li>
</ul>
```

## Icon And Visible Label

```html
<ul class="ui-social-links ui-social-links--boxed" aria-label="SayUI channels">
  <li class="ui-social-links__item">
    <a class="ui-social-links__link" href="/feed.xml">
      <span class="ui-social-links__icon" aria-hidden="true">RSS</span>
      <span class="ui-social-links__label">Subscribe</span>
    </a>
  </li>
</ul>
```

## Public Classes

- `ui-social-links`
- `ui-social-links__item`
- `ui-social-links__link`
- `ui-social-links__icon`
- `ui-social-links__label`
- `ui-social-links--compact`
- `ui-social-links--boxed`

The root, item, and link classes are required. `ui-social-links__icon` and `ui-social-links__label` are optional individually, but every link needs meaningful visible content or an accessible name.

## Variants

- `ui-social-links--compact` reduces gap, link height, and text scale.
- `ui-social-links--boxed` gives links a contained treatment with border, background, padding, and a consistent target size.

There are no inline, vertical, footer, sidebar, author, active, or disabled variants in v1.

## Accessibility

- Always use `ul > li > a`.
- Give the list an accessible name when the surrounding context does not already identify it.
- Use real internal, external, `mailto:`, or RSS destinations.
- Icon-only links require `aria-label`.
- Decorative icons or marks need `aria-hidden="true"`.
- Visible descriptive text normally removes the need for a redundant `aria-label`.
- Do not use empty links or `href="#"`.
- Do not use buttons or `role="button"`; this component represents navigation.
- `ui-social-links__link` has a visible focus style.

## Responsive

The base list is horizontal and wraps naturally. It has no breakpoint dependency and does not impose full width. Both variants work in narrow sidebars, footers, and content columns.

## Relationships

- `ui-author-card__links` remains part of the current `ui-author-card` contract.
- `ui-footer__socials` and `ui-footer-editorial__social` remain part of their current footer contracts.
- `ui-article-sidebar__social` remains part of the current article-sidebar contract.
- `ui-social-links` can be used in new compositions without depending on or replacing those original patterns.
- No original component should migrate without a separate approved migration contract.

## Dependencies

- No JavaScript.
- No Material Symbols requirement.
- No icon pack supplied by SayUI.
- No dependency on footer, sidebar, or author components.
