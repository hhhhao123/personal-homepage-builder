# Site Structure

Use this file when implementing a new plain static personal homepage or reorganizing an unstructured one.

## Default Rule

Do not default to one giant HTML file for a real homepage implementation. Prefer a small structured static site with separate assets unless the user explicitly asks for a disposable prototype or the existing project already uses a single-file pattern.

Do not assume every personal homepage should be a single page. Choose the smallest site shape that fits the confirmed content:

- **Single page**: best for a simple identity page, compact portfolio, link hub, or quick launch.
- **Hybrid**: one strong landing page plus 1-3 supporting pages, best when the first screen should stay focused but some content needs room.
- **Multi-page**: best for blogs, publications, project case studies, galleries, services, speaking, teaching, or a detailed academic/creator profile.

Ask in user-facing language when unclear:

```text
Should everything live on one scrollable page, or should some things have their own pages, such as Projects, Writing, About, or Contact?
```

## Plain Static Site

Default single-page structure:

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

Default multi-page plain static structure:

```text
/
|-- index.html
|-- about.html
|-- projects.html
|-- writing.html
|-- contact.html
|-- assets/
|   |-- css/
|   |   |-- base.css
|   |   |-- components.css
|   |   |-- animations.css
|   |   |-- layout.css
|   |   `-- pages.css
|   |-- js/
|   |   |-- main.js
|   |   `-- interactions.js
|   |-- images/
|   `-- data/
|       |-- profile.json
|       |-- projects.json
|       `-- writing.json
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

## Starter Template

For a new plain static GitHub Pages friendly site, use `assets/static-site-template/` as the starting point when it fits the confirmed brief.

The template provides:

- `index.html` with semantic sections and asset links
- `assets/css/base.css` for variables, typography, reset, and layout primitives
- `assets/css/components.css` for navigation, buttons, cards, panels, and shared pieces
- `assets/css/animations.css` for optional reveal behavior with `prefers-reduced-motion`
- `assets/css/home.css` for homepage composition
- `assets/js/main.js` for lightweight initialization
- `assets/js/interactions.js` for progressive reveal behavior
- `assets/data/profile.json` as an optional maintainable content seed
- `assets/images/` for user-provided, licensed, or generated visuals

Adapt the template to the confirmed brief. Do not keep placeholder text, fake links, or unused sections in the final homepage.

Skip the template when:

- the repository already has a coherent stack or design system
- the confirmed stack is Jekyll, Astro, Next.js, React, or another framework
- the user explicitly requests a different structure
- the work is a small patch to an existing page

## Responsibilities

- `index.html`: semantic document structure, sections, metadata, and links to assets.
- supporting HTML pages: focused content that would make the homepage too long, such as about, projects, writing, publications, speaking, gallery, services, or contact.
- `assets/css/base.css`: reset, variables, typography, layout primitives.
- `assets/css/components.css`: reusable cards, buttons, link groups, media blocks, nav, footer.
- `assets/css/animations.css`: optional reusable motion styles when motion is enabled.
- `assets/css/home.css` or `assets/css/pages.css`: page-specific composition and responsive layout.
- `assets/js/main.js`: initialization and safe progressive enhancement.
- `assets/js/interactions.js`: optional interactions, motion toggles, filters, or small UI behavior.
- `assets/data/profile.json`: optional user-editable profile content for maintainability.
- `assets/data/projects.json`, `writing.json`, or similar files: optional repeated content data for multi-page sites.

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
|-- about.md
|-- projects.md
|-- writing.md
|-- assets/
|   |-- css/
|   |-- js/
|   `-- images/
```

Use `_data/profile.yml` for content the user may edit later.

For content-heavy sites, use collections when appropriate:

```text
/
|-- _projects/
|-- _posts/
|-- _publications/
|-- _layouts/
|-- _includes/
|-- index.html
```

Use collections only when they reduce maintenance effort. Do not add Jekyll complexity for a tiny site.

## Page Model Decision

Prefer a single page when:

- the homepage has fewer than 5-6 compact sections
- the user has limited content or wants a fast launch
- visitor action is simple, such as contact, follow, or view top projects
- the site should feel like one focused introduction

Prefer multiple pages when:

- projects, writing, publications, services, gallery, speaking, or teaching each need their own space
- there are repeated items that need filtering, indexing, tags, dates, or detail views
- the homepage would become too long or unfocused
- different audiences need different paths, such as recruiters vs readers vs clients
- SEO, shareable project pages, or article pages matter

For hybrid sites, keep `index.html` as the strongest summary page and link to supporting pages for depth.

## Page Model To File Plan

Use the confirmed brief to choose the smallest maintainable structure. Do not create pages only because a template has them.

| Confirmed need | Recommended structure | File-plan notes |
| --- | --- | --- |
| One focused identity, 3-5 compact modules, simple next action | Single page | `index.html` plus separated `assets/css/`, `assets/js/`, `assets/images/`, optional `assets/data/profile.json`. |
| Strong first screen plus deeper projects, writing, gallery, research, or services | Hybrid | `index.html` for overview, 1-3 supporting pages for depth, shared navigation/footer, shared assets. |
| Repeated content with detail views, articles, publications, posts, galleries, services, talks, or audience-specific paths | Multi-page | Page/index files plus data/config or collections where the stack supports it. |
| Existing coherent project | Existing structure | Preserve stack conventions and add only the pages/assets/data needed by the confirmed plan. |

Before implementation, write a file plan:

```text
Page model:
Page map:
- index.html:
- <supporting page>:
Shared assets:
Data/config:
Images/media:
Do not touch:
Reason this is not a monolithic HTML file:
Reason this is not over-engineered:
```

## Navigation Rules

- Confirm the page map before implementation.
- Keep navigation labels short and human-readable: Home, About, Projects, Writing, Research, Gallery, Contact.
- Avoid adding pages with no real content. Use placeholders only when the user confirms they are acceptable.
- Make the current page clear with an active state.
- Keep footer links and social/contact links consistent across pages.
- For multi-page sites, include canonical metadata and page-specific titles/descriptions when practical.
- Do not add navigation links to empty, fake, or unconfirmed pages.
- If a supporting page is planned but content is missing, either keep it out of navigation until ready or label it as an approved draft placeholder.

## Implementation Rules

- Follow the existing project structure if one already exists.
- Keep HTML semantic and readable.
- Keep CSS modular enough to maintain, but do not over-split tiny projects.
- Keep JavaScript optional where possible. The page should still show core content without JS.
- Share layout, navigation, footer, theme variables, and reusable components across pages.
- Use kebab-case file names.
- Save generated or user-provided images under `assets/images/`.
- Avoid inline CSS and inline JS except for tiny critical snippets with a clear reason.
- Use responsive CSS from the start.
- Respect `prefers-reduced-motion` for animations.
- Keep shared navigation, footer, theme variables, and repeated card styles in shared asset files instead of duplicating them across pages.
- For repeated content, prefer `assets/data/*.json`, `_data/*.yml`, collections, or the existing project's data layer when it makes updates easier.
- Render only confirmed public content or approved draft placeholders.
- Do not leave template sections, placeholder links, or unused starter code in final delivery.

## When A Single HTML File Is Acceptable

Use a single file only when:

- the user explicitly asks for a quick disposable prototype
- the environment requires a single artifact
- the site is a temporary preview before real implementation

If using a single file, say it is a prototype and recommend splitting assets before publishing.
