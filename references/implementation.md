# Implementation Guidance

## Default Target: GitHub Pages

Default to a GitHub Pages compatible static site for ordinary personal homepages.

Prefer:
- repository name: `<username>.github.io`
- static output: plain HTML/CSS/JS or Jekyll
- profile data stored in `_data/profile.yml` or a simple JSON config when maintainability matters
- no required backend
- simple link/contact modules
- assets stored inside the repository

Avoid by default:
- server-only contact forms
- database/CMS requirements
- heavy React apps for a one-page profile
- deployment steps that require cloud configuration beyond GitHub Pages

## Existing Project

- Read project files before deciding: config, package manifests, layouts, pages, assets, styles, scripts, git status.
- If the user supplied source materials, map extracted content into existing pages before inventing new copy.
- Preserve the existing stack unless a rewrite is explicitly requested.
- Identify deployment path: GitHub Pages, Vercel, Netlify, static files, or unknown.
- If the site already targets GitHub Pages, preserve that path unless the user explicitly wants another host.
- Keep unrelated dirty worktree changes untouched.

## From Scratch

Choose the smallest stack that fits the user's needs:

- Static HTML/CSS/JS: simple one-page homepage.
- Jekyll/GitHub Pages: default for simple personal homepages, resume sites, academic profiles, and creator link hubs.
- Astro: content-rich personal sites with components and static output.
- Next.js/React: interactive apps, CMS-heavy sites, or advanced routing.

Use Context7 for framework/library/cloud docs before implementation.
Use `github-pages-bootstrap.md` for GitHub Pages setup and publish details.

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
- profile data outline when maintainability is requested
- extracted content summary when source materials were provided
- implementation plan
- optional generated theme

For an implementation request:
- modified or created site files
- generated assets saved in the workspace
- media assets or covers saved in the workspace when used
- build/test results
- local preview instructions
- GitHub Pages publish steps or direct push when requested
