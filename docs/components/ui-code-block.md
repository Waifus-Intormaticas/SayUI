# ui-code-block

Purpose: reusable block for code snippets, commands, configuration, or short console output.

When to use: use for HTML, CSS, SCSS, JavaScript, JSON, shell commands, configuration snippets, and technical examples.

When not to use: do not use for inline code, interactive editors, sandboxes, large logs, syntax highlighting, diffs, or executable terminals.

HTML minimum:

```html
<pre class="ui-code-block"><code>npm run build</code></pre>
```

Recommended structure:

```html
<figure class="ui-code-block">
  <figcaption class="ui-code-block__caption">
    Build command
  </figcaption>

  <div class="ui-code-block__header">
    <span class="ui-code-block__filename">package.json</span>
    <span class="ui-code-block__language">json</span>
  </div>

  <pre class="ui-code-block__pre"><code class="ui-code-block__code">{
  "scripts": {
    "build": "sass src/styles/main.scss dist/css/sayui.css"
  }
}</code></pre>
</figure>
```

Copy hook:

```html
<figure class="ui-code-block ui-code-block--terminal">
  <div class="ui-code-block__header">
    <span class="ui-code-block__filename">Terminal</span>
    <span class="ui-code-block__language">shell</span>
    <button class="ui-code-block__copy" type="button">Copy</button>
  </div>

  <pre class="ui-code-block__pre"><code class="ui-code-block__code">$ npm run build</code></pre>
</figure>
```

Required classes:

- `ui-code-block`

Optional classes:

- `ui-code-block__header`
- `ui-code-block__filename`
- `ui-code-block__language`
- `ui-code-block__pre`
- `ui-code-block__code`
- `ui-code-block__caption`
- `ui-code-block__copy`
- `ui-code-block--compact`
- `ui-code-block--terminal`
- `ui-code-block--wrap`

Dependencies:

- No JavaScript required.
- No syntax highlighting required.
- No external icon dependency.
- `src/components/ui-code-block/ui-code-block.scss`

Responsive:

- Code scrolls horizontally by default.
- `ui-code-block--wrap` allows long lines to wrap.
- Headers wrap on narrow screens.
- Consumers may add `tabindex="0"` to `ui-code-block__pre` if keyboard-accessible horizontal scrolling is needed.

Accessibility:

- Preserve semantic `pre > code`.
- Use `figure` and `figcaption` when the block needs a description.
- Keep `ui-code-block__caption` on a real `figcaption`.
- `ui-code-block__copy` must be a `button type="button"` when used.
- `ui-code-block__copy` is only a visual hook; SayUI does not implement copy behavior.
- Do not use `role="button"` on non-interactive elements.
- Do not require `tabindex` on code blocks by default.

Example:

```html
<figure class="ui-code-block ui-code-block--wrap">
  <figcaption class="ui-code-block__caption">Install command</figcaption>
  <pre class="ui-code-block__pre" tabindex="0"><code class="ui-code-block__code">npm install sayu-ui --save-dev --ignore-scripts</code></pre>
</figure>
```

