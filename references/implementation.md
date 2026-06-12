# Implementation Guidance

## Default Target: GitHub Pages

Default to a GitHub Pages compatible static site for ordinary personal homepages or small personal sites.

Prefer:
- repository name: `<username>.github.io`
- static output: plain HTML/CSS/JS or Jekyll
- profile data stored in `_data/profile.yml` or a simple JSON config when maintainability matters
- no required backend
- simple link/contact modules
- assets stored inside the repository
- one-page, hybrid, or multi-page structure based on the confirmed content

Avoid by default:
- server-only contact forms
- database/CMS requirements
- heavy React apps for a one-page profile
- deployment steps that require cloud configuration beyond GitHub Pages

## Implementation Readiness Rule

Do not treat an accepted brief as approval to start editing files. Implementation starts only after all of these are true:

- the current effective requirements summary and `personal_homepage_brief` are confirmed
- any post-brief request has a confirmed change plan or brief patch
- project files have been inspected, or the user has approved creating a new project structure
- companion skill routing has already happened, or each unavailable fallback is recorded
- the agent has produced a scoped implementation plan with target files, no-touch files, placeholder policy, validation, and GitHub Pages assumptions
- the user explicitly confirms that file edits may begin

If any item is missing, stop and produce the missing planning output instead of writing code.

## Brief-To-Implementation Plan

Before file edits, translate the confirmed brief into a practical build plan. Keep it compact, but include enough detail that the user can catch wrong assumptions before code changes.

```text
Implementation plan from the confirmed brief:
- Baseline: <requirements summary accepted? brief version/current effective? change plan if any?>
- Stack decision: <existing stack preserved / plain static / Jekyll / Astro / React etc. and why>
- Page model: <single-page / hybrid / multi-page and rationale>
- Page map: <paths, purpose, priority, sections, missing content>
- File plan:
  - Create:
  - Modify:
  - Delete:
  - Do not touch:
- Brief-to-file mapping: <which brief sections become which pages/data/assets>
- Content/data strategy: <HTML copy / assets/data/*.json / _data/*.yml / existing CMS/config>
- Asset strategy: <images, generated assets, icons, media, alt text, fallbacks>
- Placeholder policy: <allowed draft placeholders, removed-before-final items, no fake claims>
- Motion plan: <level, files affected, reduced-motion fallback, no-JS behavior>
- GitHub Pages assumptions: <relative paths, build/preview command, publish target if known>
- Validation: <preview/build, responsive, accessibility, reduced motion, link/path checks>
- Approval needed: <ask user to confirm before editing>
```

The `Brief-to-file mapping` is the guard against generic pages. Every created page or major section should trace back to a confirmed requirement, accepted reference interpretation, content module, or approved placeholder.

## Stack Choice Guardrails

- Preserve an existing coherent stack unless the user explicitly requests a rewrite or the stack cannot support the confirmed brief.
- For ordinary GitHub Pages personal sites, prefer plain static HTML/CSS/JS or Jekyll.
- Use Jekyll when `_data`, layouts, collections, posts, publications, or repeated content will reduce maintenance effort.
- Use Astro or another static component framework only when the confirmed site benefits from components, content collections, or richer static routing.
- Use React/Next-style applications only when the confirmed brief requires application-like interactivity, complex state, CMS-heavy behavior, or advanced routing.
- Do not add dependencies only to make a small profile page feel modern.
- When framework, CLI, SDK, or cloud behavior matters, consult the current official documentation path required by the host agent before implementation.

## Existing Project

- Read project files before deciding: config, package manifests, layouts, pages, assets, styles, scripts, git status.
- If the user supplied source materials, map extracted content into existing pages before inventing new copy.
- Preserve the existing stack unless a rewrite is explicitly requested.
- Identify deployment path: GitHub Pages, Vercel, Netlify, static files, or unknown.
- If the site already targets GitHub Pages, preserve that path unless the user explicitly wants another host.
- For mid-project feature or design requests, use `iteration-requests.md` and update the smallest coherent set of files.
- Do not edit visible page behavior, content, layout, style, navigation, media, or motion until the user confirms the compact change plan.
- Keep unrelated dirty worktree changes untouched.
- List files that should not be touched in the implementation plan, especially user drafts, unrelated docs, generated artifacts, and previous uncommitted changes.

## From Scratch

Choose the smallest stack and page model that fits the user's needs:

- Static HTML/CSS/JS: simple one-page homepage or small multi-page site.
- Jekyll/GitHub Pages: personal sites with repeated projects, writing, publications, or basic content collections.
- Astro: content-rich personal sites with components, collections, and static output.
- Next.js/React: interactive apps, CMS-heavy sites, advanced routing, or application-like personal products.

Use the current agent system's official documentation lookup tool for framework, library, SDK, CLI, or cloud docs before implementation. If no such tool is available, use official documentation or the best available retrieval path.
Use `github-pages-bootstrap.md` for GitHub Pages setup and publish details.
Use `site-structure.md` for default file organization.
For new plain static sites, use `assets/static-site-template/` as the preferred starting structure unless the confirmed page map, existing project, or user request makes another stack more appropriate.
Use `motion-design.md` when the brief allows motion.

## File Structure Rule

For a real static homepage implementation, do not default to one large HTML file. Prefer a maintainable structure with `index.html`, optional supporting pages such as `about.html`, `projects.html`, or `writing.html`, `assets/css/`, `assets/js/`, `assets/images/`, and optional `assets/data/`. For a new plain static site, copy or adapt the starter structure in `assets/static-site-template/` rather than inventing a monolithic file. Keep single-file HTML only for disposable prototypes, constrained artifact environments, or when the user explicitly asks for it.

Before editing, decide and state:

- page model: single page, hybrid, or multi-page
- page map: page names, paths, purpose, and primary sections
- navigation: header/footer links, active states, and mobile behavior
- shared assets: CSS, JavaScript, data, images, and reusable components
- content ownership: which content appears on the homepage summary versus supporting pages
- confirmation status: whether the user has approved this implementation plan

## Content Integrity Rule

Build from confirmed material only. Do not invent achievements, project outcomes, metrics, testimonials, publications, clients, employer names, photos, contact links, social handles, legal names, or locations to make the page feel complete.

When material is missing:

- use clearly marked draft placeholders only if the user approved them
- prefer neutral labels such as "Project details coming soon" over fake specificity
- record placeholders in the brief and implementation plan
- remove or report every remaining placeholder before final delivery
- keep private or needs-confirmation data out of rendered pages

## Motion Rule

Motion is optional and must match the brief. If motion is enabled, implement it as progressive enhancement with `prefers-reduced-motion` support. Prefer `opacity` and `transform`, keep core content visible without JavaScript, and place reusable motion styles or scripts in asset files instead of inline code.

## Skill Orchestration

- Use `theme-factory` to create or adapt a visual theme.
- Use `frontend-design` for distinctive UI implementation.
- Use `imagegen` for hero images, textures, portraits, or visual assets when raster visuals would improve identity.
- Use `web-design-guidelines` to review UI/accessibility.
- Use `web-artifacts-builder` only when creating a complex React/Tailwind/shadcn artifact; do not use it for simple static or Jekyll sites unless intentionally scaffolding a new artifact.
- Use `find-skills` or `skill-installer` when a needed support skill is missing and the user asks to extend capabilities.

## Asset Strategy

- If the user has photos or existing assets, inspect and reuse them when appropriate.
- If assets are missing, offer one of: generated hero image, abstract texture, typography-first design, or photo placeholder strategy.
- Save project-bound generated assets in the repository, with descriptive non-destructive filenames.

## Profile Data Strategy

- For maintainable GitHub Pages sites, create or update profile data before rendering pages.
- Use `profile-schema.md` as the data contract.
- For future requests like adding a new work, social link, publication, or video, update profile data first.
- Hard-code content only for a throwaway static page or when the existing project has no data layer and the user wants a fast edit.
- Repeated items such as projects, publications, writing, social links, media, talks, or services should usually live in data/config when the stack supports it.
- Each rendered item must be public-safe, confirmed, or explicitly approved as a draft placeholder.

## Media Strategy

- Keep media optional. Default to static images for speed and simplicity.
- For decorative background video, use muted autoplay with `loop`, `playsinline`, and a poster fallback.
- Do not promise audible autoplay. Provide a play button or sound toggle after user interaction.
- For project/work videos, prefer cards with cover images and links/embeds.
- Use user-uploaded covers first; platform thumbnails are optional and should not be brittle.
- Compress large files and avoid bloating GitHub Pages repositories.
- Respect `prefers-reduced-motion` by pausing or replacing video/motion with poster imagery.

## Social Link Strategy

- Represent contact and social links as structured data when the stack supports it, for example Jekyll `_data/social.yml`, JSON, or a small config object.
- Include platform label, URL, optional handle, group, and priority.
- Show 3-6 highest-priority links prominently; place the rest in a compact social/contact section.
- Use platform icons only when the project already has an icon system or when adding icons is low-friction. Text links are acceptable for GitHub Pages v1.
- For QR-code-first platforms such as WeChat Official Account, support an image asset plus label.
- Never invent social links or handles. Use only user-provided URLs/handles.

## Deliverables

For a planning-only request:
- personal homepage brief
- page model and page map recommendation
- profile data outline when maintainability is requested
- extracted content summary when source materials were provided
- implementation plan
- optional generated theme

For an implementation request:
- modified or created site files
- generated assets saved in the workspace
- CSS and JavaScript separated into project asset files unless intentionally building a prototype
- page files separated when the confirmed page map requires multiple pages
- motion behavior implemented according to the confirmed `motion_strategy`, or explicitly omitted when motion is disabled
- media assets or covers saved in the workspace when used
- build/test results
- local preview instructions
- GitHub Pages publish steps or direct push when requested

## Final Implementation Review

Before final delivery, produce a short review report using `quality-checklist.md`.

The report must cover:

- whether the built files match the confirmed brief and page map
- whether CSS, JS, media, and data are separated or why an exception was necessary
- remaining placeholders or missing materials
- responsive, accessibility, reduced-motion, and link/path checks
- GitHub Pages compatibility and local preview/build result
- files changed and files intentionally left untouched
- publish status, making clear that commit, push, or deployment requires explicit user approval unless already requested
