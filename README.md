# templates

A minimal, reusable CSS design system for personal websites, portfolios, and landing pages.

Built around editorial typography, thoughtful spacing, responsive layouts, and light/dark theme support. Framework-free and easy to adapt to any static HTML project.

## Repository contents

- `style.css` — the stylesheet containing tokens, layout primitives, components, and theme rules
- `LICENSE` — MIT license

Note: this repository currently provides a stylesheet and design system rather than a full starter site (no HTML files or font binaries are included). If you prefer a ready-to-run starter I can add an `index.html` and demo assets.

## Features

- Token-based design system (colors, spacing, type, motion)
- Light and dark themes controlled via `data-theme` on the `body` element
- Responsive layout patterns for landing pages and project lists
- Framework-free (works with plain HTML)
- Small, easy-to-customize surface area for quick iteration

## Theme behavior (how "system" works)

The stylesheet supports three theme modes via `body[data-theme]`:

- `light` — force the light theme
- `dark` — force the dark theme
- `system` — follow the user's OS/browser preference when available

Implementation details: the CSS uses the `prefers-color-scheme` media query together with `body[data-theme="system"]` to switch variables when the OS is in dark mode. This means no JavaScript is required for basic system-theme behavior — browsers that support `prefers-color-scheme` will apply the dark tokens automatically when `data-theme="system"` is set. If you need more advanced runtime switching (persisting a user choice across pages), a small JS helper can toggle the `data-theme` attribute and store the preference in localStorage — tell me if you want that added.

## Fonts and assets

- `style.css` references a variable font (`assets/fonts/NeueCometVariable.woff2`) for the intended appearance. That font file is not included in this repo.
- The MIT license in this repository applies to the code and stylesheet only and does not automatically grant rights to third-party font files. If you plan to redistribute or bundle a font, verify the font's license separately.
- If you don't have the font, you can either replace the `--font-family-body` token with system fonts or add a webfont from a provider you have rights to.

Example replacement snippet:

```css
:root {
  --font-family-body: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
```

## Quick start

1. Copy `style.css` into your project.
2. Include it in your HTML:

```html
<link rel="stylesheet" href="style.css">
```

3. Minimal page structure to get started:

```html
<body data-theme="system">
  <header class="topbar">
    <nav>
      <a href="#home">Home</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <main>
    <section id="home">
      <h1 class="home-title">Your name</h1>
      <div class="home-navigation">
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </div>
    </section>

    <section id="projects">
      <article class="project-card">
        <h2 class="project-card-title">Project title</h2>
        <p class="project-card-description">Short project description.</p>
      </article>
    </section>
  </main>
</body>
```

## Preview / demo suggestions

A screenshot or a GitHub Pages demo helps people evaluate the visual style before cloning. If you want, I can:

- Add a small `index.html` demo page to this repo and wire it to GitHub Pages
- Add a `preview.png` screenshot to the README

Tell me which you prefer and I’ll add it.

## License

This repository is licensed under the MIT License. See `LICENSE` for details.
