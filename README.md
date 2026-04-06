# SayUI

> A minimal, modular and elegant UI component library built with SCSS.

![Version](https://img.shields.io/badge/version-1.0.0-red)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-blue)

---

##  Overview

SayUI is a lightweight UI library designed with a **clean architecture** based on:

* Layouts (structure)
* Components (reusability)
* Foundations (design tokens)

Built for scalability, readability and modern frontend workflows.

---

##  Features

* SCSS modular architecture
* BEM naming convention (`ui-*`)
* Fully reusable components
* Layout-driven design system
* Single CSS output (easy integration)

---

##  Preview

<p align="center">
  <img src="src/docs/images/brave_screenshot.png" width="45%">
  <img src="src/docs/images/brave_screenshot (1).png" width="45%">
</p>

<p align="center">
  <img src="src/docs/images/brave_screenshot (2).png" width="45%">
  <img src="src/docs/images/brave_screenshot (3).png" width="45%">
</p>

```
demo/index.html
```

---

##  Installation

Include the compiled CSS file:

```html
<link rel="stylesheet" href="dist/css/sayui.css">
```
---

## ⚠️ Global Styles

> [!IMPORTANT]  
> SayUI components rely on a minimal global stylesheet.  
> You must include these base styles before using any component. Otherwise, layout and spacing may break.  
> They behave similarly to a lightweight CSS reset.  
>  
> These styles ensure visual consistency across all components.

### Base Styles (required)

```css
* {
    box-sizing: border-box;
    border-width: 0;
    border-style: solid;
    border-color: var(--border-light);
}

html {
    font-size: 16px;
    line-height: 1.5;
    -webkit-text-size-adjust: 100%;
    -moz-tab-size: 4;
    tab-size: 4;
    font-family: ui-sans-serif, system-ui, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    font-feature-settings: normal;
    font-variation-settings: normal;
    -webkit-tap-highlight-color: transparent;
}

body {
    margin: 0;
    font-family: Manrope, sans-serif;
    line-height: inherit;
}

h1,
h2,
h3,
h4 {
    margin: 0;
    line-height: 1.2;
}

p {
    margin: 0;
}

a {
    text-decoration: none;
    color: inherit;
}

button {
    -webkit-appearance: button;
    appearance: button;
    background-color: transparent;
    font-family: inherit;
    font-variation-settings: inherit;
    margin: 0;
    padding: 0;
    cursor: pointer;
}
```
---

##  Project Structure
```
src/
  components/
    banner/
    footer/
    topbar/
    ui-sidebar/
    ui-post-card/
    ui-main-header/
    ui-post-grid/

  layouts/
    ui-page/
    ui-layout/
    ui-main/

  styles/
    foundations/
      _variables.scss

dist/
  css/
    sayui.css

demo/
  index.html
```

---

##  Components

### Banner

```html
<section class="ui-banner"></section>
```

### Sidebar

```html
<aside class="ui-sidebar"></aside>
```

### Post Card

```html
<article class="ui-post-card"></article>
```

---

##  Layout System

### Page Layout

```html
<div class="ui-page">
    <header class="ui-topbar"></header>

    <div class="ui-layout">
        <section class="ui-banner"></section>

        <div class="ui-layout__content">
            <main class="ui-main"></main>
            <aside class="ui-sidebar"></aside>
        </div>
    </div>

    <footer class="ui-footer"></footer>
</div>
```

---

##  Development

### Watch SCSS

```bash
sass src/styles/main.scss dist/css/sayui.css --watch
```

### Build (minified)

```bash
sass src/styles/main.scss dist/css/sayui.min.css --style=compressed
```

---

##  Demo

Run locally:

```
demo/index.html
```

Make sure it includes:

```html
<link rel="stylesheet" href="../dist/css/sayui.css">
```

---

##  Philosophy

SayUI follows a strict separation of concerns:

* **Layouts** → Structure and composition
* **Components** → Reusable UI blocks
* **Foundations** → Variables and design tokens

---

##  Guidelines

* Do not modify core styles directly
* Extend components with custom classes
* Keep naming consistent with `ui-*`

---

## Author

**Jonathan Ventura**
GitHub: [JVenturaDev](https://github.com/JVenturaDev)

---