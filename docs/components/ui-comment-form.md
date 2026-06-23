# ui-comment-form

Purpose: public form component for writing a comment. SayUI provides its semantic HTML contract and visual presentation, but does not process, validate, or submit comments.

When to use: use beside `ui-comment` instances or within an editorial discussion area when a consumer needs a textarea, visible label, optional help text, and submit action.

When not to use: do not use for individual comments, comment lists, general contact forms, backend behavior, JavaScript validation, authentication, captcha, Markdown or rich-text editing, previews, uploads, moderation, or submission states.

## HTML Minimum

```html
<form class="ui-comment-form" aria-label="Add a comment">
  <div class="ui-comment-form__field">
    <label class="ui-comment-form__label" for="comment-message">Comment</label>
    <textarea
      class="ui-comment-form__textarea"
      id="comment-message"
      name="comment"
    ></textarea>
  </div>

  <div class="ui-comment-form__actions">
    <button class="ui-comment-form__submit" type="submit">Post Comment</button>
  </div>
</form>
```

## Recommended HTML

```html
<form
  class="ui-comment-form"
  action="/comments"
  method="post"
  aria-labelledby="comment-form-title"
>
  <h3 class="ui-comment-form__title" id="comment-form-title">
    Add to the Conversation
  </h3>

  <div class="ui-comment-form__field">
    <label class="ui-comment-form__label" for="article-comment">Comment</label>
    <textarea
      class="ui-comment-form__textarea"
      id="article-comment"
      name="comment"
      rows="6"
    ></textarea>
  </div>

  <div class="ui-comment-form__actions">
    <button class="ui-comment-form__submit" type="submit">Post Comment</button>
  </div>
</form>
```

The consuming project owns the real `action`, `method`, endpoint, and submission behavior.

## With Help Text

```html
<form
  class="ui-comment-form"
  action="/comments"
  method="post"
  aria-labelledby="comment-help-title"
>
  <h3 class="ui-comment-form__title" id="comment-help-title">Leave a Comment</h3>

  <div class="ui-comment-form__field">
    <label class="ui-comment-form__label" for="comment-with-note">Comment</label>
    <textarea
      class="ui-comment-form__textarea"
      id="comment-with-note"
      name="comment"
      rows="6"
      aria-describedby="comment-note"
    ></textarea>
    <p class="ui-comment-form__note" id="comment-note">
      Keep your response relevant and respectful.
    </p>
  </div>

  <div class="ui-comment-form__actions">
    <button class="ui-comment-form__submit" type="submit">Post Comment</button>
  </div>
</form>
```

## Without A Visible Title

The form needs an accessible name even when it does not have a visible title. The textarea still keeps its visible label.

```html
<form
  class="ui-comment-form"
  action="/comments"
  method="post"
  aria-label="Write a comment"
>
  <div class="ui-comment-form__field">
    <label class="ui-comment-form__label" for="standalone-comment">Comment</label>
    <textarea
      class="ui-comment-form__textarea"
      id="standalone-comment"
      name="comment"
      rows="6"
    ></textarea>
  </div>

  <div class="ui-comment-form__actions">
    <button class="ui-comment-form__submit" type="submit">Post Comment</button>
  </div>
</form>
```

## Composition With ui-comment

```html
<section aria-labelledby="discussion-title">
  <header class="ui-section-header ui-section-header--compact">
    <h2 class="ui-section-header__title" id="discussion-title">Discussion</h2>
  </header>

  <article class="ui-comment">
    <div class="ui-comment__body">
      <header class="ui-comment__header">
        <span class="ui-comment__author">Julian Moss</span>
      </header>
      <p class="ui-comment__text">Semantic forms make the discussion easier to use.</p>
    </div>
  </article>

  <form
    class="ui-comment-form"
    action="/comments"
    method="post"
    aria-labelledby="discussion-form-title"
  >
    <h3 class="ui-comment-form__title" id="discussion-form-title">Add a Comment</h3>
    <div class="ui-comment-form__field">
      <label class="ui-comment-form__label" for="discussion-comment">Comment</label>
      <textarea
        class="ui-comment-form__textarea"
        id="discussion-comment"
        name="comment"
        rows="6"
      ></textarea>
    </div>
    <div class="ui-comment-form__actions">
      <button class="ui-comment-form__submit" type="submit">Post Comment</button>
    </div>
  </form>
</section>
```

This is a documented composition, not a `ui-comment-list` component.

## Public Classes

- `ui-comment-form`
- `ui-comment-form__title`
- `ui-comment-form__field`
- `ui-comment-form__label`
- `ui-comment-form__textarea`
- `ui-comment-form__note`
- `ui-comment-form__actions`
- `ui-comment-form__submit`

`ui-comment-form__title` and `ui-comment-form__note` are optional. The field, visible label, textarea, actions region, and submit button are required by the v1 contract.

## Variants

There are no modifiers in v1. The component does not define compact, reply, or inline variants, and it does not include success, error, or loading states.

## Accessibility

- Always use `form` as the root; do not add `role="form"`.
- Give every textarea a unique `id` and a meaningful `name`.
- Keep `ui-comment-form__label` visible and connect it with `for`.
- A placeholder never replaces the visible label.
- Do not use only `aria-label` to name the textarea.
- Use `aria-labelledby` on the form when a visible title is present.
- Use `aria-label` on the form when no visible title exists.
- Connect help text with `aria-describedby`.
- Use `button type="submit"` for submission.
- The textarea and submit button have visible focus styles.
- `required`, `maxlength`, validation rules, and error messaging belong to the consumer.

## Responsive

The component occupies the available width and uses a vertical flow. The textarea can resize vertically, and the actions region can wrap on narrow viewports. It does not depend on article or sidebar layout classes.

## Relationships

- `ui-comment`: represents a published comment; it is not contained or recreated by this component.
- `ui-newsletter`: shares native form and focus principles, but keeps a separate public API and purpose.
- `ui-article-main`: contains the original comment-form pattern, but is not migrated or modified by this component.
- Future form foundations: may eventually share lower-level patterns after a separate contract is approved. `ui-comment-form` does not create a general form system.
