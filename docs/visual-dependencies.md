# Visual Dependencies

SayUI is consumed through compiled CSS and HTML classes.

## Required CSS

Use one of the compiled CSS files:

```html
<link rel="stylesheet" href="dist/css/sayui.css">
```

or:

```html
<link rel="stylesheet" href="dist/css/sayui.min.css">
```

## Build Tool

SayUI uses Sass.

Official commands:

```bash
npm run build
npm run watch
npm run build:min
```

Do not add a framework or app bundler to SayUI unless explicitly requested.

## Fonts

The demos use Manrope from Google Fonts.

Consumer projects can either load Manrope or provide their own font stack. If Manrope is not loaded, typography will fall back to the browser/system font stack.

## Icons

The demos use Material Symbols for icon text such as:

- `search`
- `menu`
- `mail`
- `share`
- `rss_feed`
- `format_quote`

If a consumer project does not load Material Symbols, icon spans will render as text.

## Images

Image paths in snippets are demo paths. Consumer projects should replace them with their own assets.

Image rules:

- Use descriptive `alt` for meaningful content images.
- Use empty `alt=""` only for decorative images.
- Preserve `object-fit` friendly dimensions when replacing images.

## CSS Variables

Design values come mainly from `src/styles/foundations/_variables.scss`.

Consumers can override CSS custom properties if they need theme changes:

```css
:root {
  --primary: rgb(230 57 70 / 1);
}
```

## Breakpoints Used

Current component breakpoints include:

- `768px`: editorial topbar nav, article related grid, editorial footer rows.
- `1024px`: main layout columns, sidebar width, article grid columns, banner split layout.

