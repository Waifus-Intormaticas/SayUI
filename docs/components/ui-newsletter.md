# ui-newsletter

Purpose: public signup block for email newsletter subscriptions.

When to use: use for newsletter signup blocks in sidebars, footers, articles, documentation pages, or editorial pages.

When not to use: do not use for backend subscription logic, JavaScript validation, modals, popups, toast messages, captcha flows, advanced preferences, search, login, or contact forms.

HTML minimum:

```html
<section class="ui-newsletter" aria-labelledby="newsletter-title">
  <h2 class="ui-newsletter__title" id="newsletter-title">The Weekly Digest</h2>

  <form class="ui-newsletter__form" action="/subscribe" method="post">
    <label class="ui-newsletter__label" for="newsletter-email">Email address</label>
    <input class="ui-newsletter__input" id="newsletter-email" name="email" type="email">
    <button class="ui-newsletter__submit" type="submit">Subscribe</button>
  </form>
</section>
```

Recommended structure:

```html
<section class="ui-newsletter" aria-labelledby="newsletter-title">
  <span class="ui-newsletter__icon" aria-hidden="true">@</span>

  <div class="ui-newsletter__body">
    <h2 class="ui-newsletter__title" id="newsletter-title">The Weekly Digest</h2>

    <p class="ui-newsletter__text">
      Get selected stories delivered to your inbox every Sunday.
    </p>

    <form class="ui-newsletter__form" action="/subscribe" method="post">
      <label class="ui-newsletter__label" for="newsletter-email">Email address</label>
      <input
        class="ui-newsletter__input"
        id="newsletter-email"
        name="email"
        type="email"
        autocomplete="email"
        placeholder="you@example.com"
      >
      <button class="ui-newsletter__submit" type="submit">Subscribe Now</button>
      <p class="ui-newsletter__note">No spam, ever. Unsubscribe anytime.</p>
    </form>
  </div>
</section>
```

Strong:

```html
<section class="ui-newsletter ui-newsletter--strong" aria-labelledby="newsletter-strong-title">
  <span class="ui-newsletter__icon" aria-hidden="true">@</span>

  <div class="ui-newsletter__body">
    <h2 class="ui-newsletter__title" id="newsletter-strong-title">The Weekly Digest</h2>

    <p class="ui-newsletter__text">
      Join 20,000+ designers and get our best stories delivered every Sunday.
    </p>

    <form class="ui-newsletter__form" action="/subscribe" method="post">
      <label class="ui-newsletter__label" for="newsletter-strong-email">Email address</label>
      <input
        class="ui-newsletter__input"
        id="newsletter-strong-email"
        name="email"
        type="email"
        autocomplete="email"
        placeholder="Your email address"
      >
      <button class="ui-newsletter__submit" type="submit">Subscribe Now</button>
      <p class="ui-newsletter__note">No spam, ever. Unsubscribe anytime.</p>
    </form>
  </div>
</section>
```

Compact:

```html
<aside class="ui-newsletter ui-newsletter--compact" aria-labelledby="newsletter-compact-title">
  <h3 class="ui-newsletter__title" id="newsletter-compact-title">Weekly updates</h3>

  <form class="ui-newsletter__form" action="/subscribe" method="post">
    <label class="ui-newsletter__label" for="newsletter-compact-email">Email address</label>
    <input
      class="ui-newsletter__input"
      id="newsletter-compact-email"
      name="email"
      type="email"
      autocomplete="email"
      placeholder="you@example.com"
    >
    <button class="ui-newsletter__submit" type="submit">Subscribe</button>
  </form>
</aside>
```

Required classes:

- `ui-newsletter`
- `ui-newsletter__title`
- `ui-newsletter__form`
- `ui-newsletter__label`
- `ui-newsletter__input`
- `ui-newsletter__submit`

Optional classes:

- `ui-newsletter__icon`
- `ui-newsletter__body`
- `ui-newsletter__text`
- `ui-newsletter__note`
- `ui-newsletter--strong`
- `ui-newsletter--compact`

Rules:

- Use `section` as the recommended root.
- Use `aside` when the signup is complementary content.
- Use `div` only when the consuming context already provides the section semantics.
- `ui-newsletter__label` should be visible by default.
- `aria-label` on the input is allowed only for compact edge cases, not as the default pattern.
- The icon is optional and must not require an external icon set.
- `ui-newsletter--strong` preserves the dark signup intent from the original sidebar newsletter block.
- `ui-newsletter--compact` is part of v1.
- There is no `ui-newsletter--inline` or `ui-newsletter--centered` in v1.

Dependencies:

- No JavaScript required.
- No Material Symbols or external icon dependency.
- No general form system dependency.
- `src/components/ui-newsletter/ui-newsletter.scss`

Responsive:

- Vertical by default.
- Full width by default.
- Form controls stack to work in sidebars and narrow columns.
- `ui-newsletter--compact` reduces padding, spacing, and type scale.

Accessibility:

- Use `aria-labelledby` when the component has a visible title.
- Use native heading elements for `ui-newsletter__title`.
- Use `label` with `for` connected to the email input.
- Use `type="email"` on the input.
- Use `autocomplete="email"` when appropriate.
- Use `type="submit"` on the submit button.
- Decorative icons need `aria-hidden="true"`.
- Do not use `role="alert"` for static signup blocks.

Relationship with existing components:

- `ui-newsletter` is independent from `ui-sidebar`.
- `ui-sidebar__newsletter` remains part of the current `ui-sidebar` contract and is not migrated automatically.
- `ui-callout` should not replace `ui-newsletter`; newsletter has a form and signup purpose.

Example:

```html
<section class="ui-newsletter ui-newsletter--strong" aria-labelledby="weekly-title">
  <span class="ui-newsletter__icon" aria-hidden="true">@</span>
  <div class="ui-newsletter__body">
    <h2 class="ui-newsletter__title" id="weekly-title">Weekly updates</h2>
    <p class="ui-newsletter__text">A short digest of new components and patterns.</p>
    <form class="ui-newsletter__form" action="/subscribe" method="post">
      <label class="ui-newsletter__label" for="weekly-email">Email address</label>
      <input class="ui-newsletter__input" id="weekly-email" name="email" type="email" autocomplete="email">
      <button class="ui-newsletter__submit" type="submit">Subscribe</button>
      <p class="ui-newsletter__note">No spam, ever.</p>
    </form>
  </div>
</section>
```
