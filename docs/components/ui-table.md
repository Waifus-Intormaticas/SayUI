# ui-table

Purpose: reusable table component for real tabular data.

When to use: use for feature comparisons, support matrices, versions, compatibility data, package totals, and other row/column data.

When not to use: do not use for page layout, card grids, navigation, simple lists, or interactive data grids with sorting/filtering unless a consumer project adds that behavior separately.

HTML minimum:

```html
<table class="ui-table">
  <thead>
    <tr>
      <th scope="col">Feature</th>
      <th scope="col">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Compiled CSS</td>
      <td>Supported</td>
    </tr>
  </tbody>
</table>
```

Recommended structure:

```html
<div class="ui-table__wrapper">
  <table class="ui-table ui-table--responsive">
    <caption class="ui-table__caption">
      Browser support matrix
    </caption>
    <thead>
      <tr>
        <th scope="col">Browser</th>
        <th scope="col">Version</th>
        <th scope="col">Support</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Chrome</th>
        <td>120+</td>
        <td>Full</td>
      </tr>
    </tbody>
  </table>
</div>
```

Required classes:

- `ui-table`

Optional classes:

- `ui-table__wrapper`
- `ui-table__caption`
- `ui-table--compact`
- `ui-table--striped`
- `ui-table--bordered`
- `ui-table--responsive`

Dependencies:

- No JavaScript required.
- No framework dependency.
- `src/components/ui-table/ui-table.scss`

Responsive:

- `ui-table__wrapper` handles horizontal overflow.
- `ui-table--responsive` gives the table a minimum width so columns do not collapse too aggressively.
- Tables are not converted into cards.
- `tabindex="0"` is optional on the wrapper when a consumer needs keyboard-focusable horizontal scrolling.

Accessibility:

- Use native `table`, `thead`, `tbody`, `tfoot`, `tr`, `th`, `td`, and `caption`.
- Use `th scope="col"` for column headers.
- Use `th scope="row"` when the first cell labels a row.
- Keep `caption` as a real `<caption>` element.
- Do not use tables for layout.
- Add an accessible label to a focusable wrapper when using `tabindex="0"`.

Example:

```html
<div class="ui-table__wrapper" tabindex="0" aria-label="Scrollable browser support table">
  <table class="ui-table ui-table--responsive ui-table--striped">
    <caption class="ui-table__caption">Browser support matrix</caption>
    <thead>
      <tr>
        <th scope="col">Browser</th>
        <th scope="col">Support</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">Chrome</th>
        <td>Full</td>
      </tr>
    </tbody>
  </table>
</div>
```

