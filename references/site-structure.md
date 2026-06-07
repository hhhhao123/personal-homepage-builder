# Site Structure

Use this file when implementing a new plain static personal homepage or reorganizing an unstructured one.

## Default Rule

Do not default to one giant HTML file for a real homepage implementation. Prefer a small structured static site with separate assets unless the user explicitly asks for a disposable prototype or the existing project already uses a single-file pattern.

## Plain Static Site

Default structure:

```text
/
|-- index.html
|-- assets/
|   |-- css/
|   |   |-- base.css
|   |   |-- components.css
|   |   |-- animations.css
|   |   `-- home.css
|   |-- js/
|   |   |-- main.js
|   |   `-- interactions.js
|   |-- images/
|   `-- data/
|       `-- profile.json
```

Use fewer files for very small sites, but keep CSS and JS out of `index.html` by default:

```text
/
|-- index.html
|-- assets/
|   |-- css/
|   |   `-- styles.css
|   |-- js/
|   |   `-- main.js
|   `-- images/
```

## Responsibilities

- `index.html`: semantic document structure, sections, metadata, and links to assets.
- `assets/css/base.css`: reset, variables, typography, layout primitives.
- `assets/css/components.css`: reusable cards, buttons, link groups, media blocks, nav, footer.
- `assets/css/animations.css`: optional reusable motion styles when motion is enabled.
- `assets/css/home.css`: page-specific composition and responsive layout.
- `assets/js/main.js`: initialization and safe progressive enhancement.
- `assets/js/interactions.js`: optional interactions, motion toggles, filters, or small UI behavior.
- `assets/data/profile.json`: optional user-editable content data for maintainability.

## Jekyll Or GitHub Pages With Data

For maintainable Jekyll sites, prefer:

```text
/
|-- _config.yml
|-- _data/
|   `-- profile.yml
|-- _includes/
|-- _layouts/
|-- index.html
|-- assets/
|   |-- css/
|   |-- js/
|   `-- images/
```

Use `_data/profile.yml` for content the user may edit later.

## Implementation Rules

- Follow the existing project structure if one already exists.
- Keep HTML semantic and readable.
- Keep CSS modular enough to maintain, but do not over-split tiny projects.
- Keep JavaScript optional where possible. The page should still show core content without JS.
- Use kebab-case file names.
- Save generated or user-provided images under `assets/images/`.
- Avoid inline CSS and inline JS except for tiny critical snippets with a clear reason.
- Use responsive CSS from the start.
- Respect `prefers-reduced-motion` for animations.

## When A Single HTML File Is Acceptable

Use a single file only when:

- the user explicitly asks for a quick disposable prototype
- the environment requires a single artifact
- the site is a temporary preview before real implementation

If using a single file, say it is a prototype and recommend splitting assets before publishing.
