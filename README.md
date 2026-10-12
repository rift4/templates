# templates

A minimal, reusable front-end design system for personal websites, portfolios, and landing pages.

Built around editorial typography, deliberate spacing, and a restrained visual language. Plain HTML, CSS, and JavaScript — no frameworks, no dependencies, just a foundation you can make your own.

## Features

- **Design tokens** — centralized colors, typography, spacing, layout, and motion values
- **Theme controller** — cycle between system, light, and dark modes
- **Reusable site header** — dynamically rendered navigation controls, profile link, and theme toggle
- **Responsive layouts** — adaptable landing page and project presentation patterns
- **Editorial typography** — Neue Comet variable font with system fallbacks
- **Accessible interactions** — semantic controls, descriptive labels, and reduced-motion support
- **Framework-free** — built with standard web technologies

## Structure

```text
templates/
├── assets/
│    ├── js/
│        ├── theme.js
│        ├── site-header.js
├── style.css
└── LICENSE
```

## Getting started

Add the stylesheet and scripts to your HTML page:

```html
<link rel="stylesheet" href="style.css" />

<script src="site-header.js" defer></script>
<script src="theme.js" defer></script>
```

Add a header placeholder and set the initial theme on the body:

```html
<body data-theme="system">
  <div id="site-header"></div>

  <main>
    <section id="home">
      <h1 class="home-title">Your next idea.</h1>
    </section>
  </main>
</body>
```

The header script replaces `#site-header` with the shared site header. Load `site-header.js` before `theme.js` so the theme controller can find the toggle button it creates.

## Theming

The theme controller cycles through three modes:

| Mode | Behavior |
| --- | --- |
| `system` | Follows the operating system's color preference |
| `light` | Forces the light theme |
| `dark` | Forces the dark theme |

Set the initial mode using `data-theme` on the `body` element. The selected mode is applied through CSS, and theme changes dispatch a `site:themechange` custom event.

## Site header

The shared header includes a GitHub profile link and a theme toggle. Add `data-show-home-link` to the header placeholder to include a home link.

The placeholder also supports optional configuration:

| Attribute | Purpose |
| --- | --- |
| `data-site-root` | Sets the root URL used to resolve site assets |
| `data-github-url` | Overrides the GitHub profile URL |
| `data-show-home-link` | Enables the home link |
| `data-home-page` | Overrides the home page path |

For example:

```html
<div
  id="site-header"
  data-site-root="/"
  data-github-url="https://github.com/rift4"
  data-show-home-link
  data-home-page="index.html"
></div>
```

## Customization

Start with the design tokens near the top of `style.css`. CSS custom properties control the visual system, including colors, typography, spacing, layout dimensions, and animation timing.

```css
:root {
  --color-orange: #ff4b24;
  --font-family-body: "Neue Comet", system-ui, sans-serif;
  --layout-page-gutter: 24px;
}
```

Modify existing tokens or introduce your own to adapt the system to your project.

## License

MIT
