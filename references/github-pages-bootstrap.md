# GitHub Pages Bootstrap

Default to GitHub Pages for ordinary personal homepages unless the user asks for another host.

## Default Repository

- Use `<username>.github.io` for a user homepage.
- The repository name must match the GitHub username or organization.
- The published URL is `https://<username>.github.io`.
- A custom domain is optional; the repository naming convention still matters.

## Recommended Site Types

- Plain HTML/CSS/JS for the simplest one-page site.
- Jekyll for maintainable data-driven static sites using `_data/profile.yml`, layouts, and Liquid.
- Avoid heavy app frameworks for ordinary profile pages unless the user needs routing, CMS-like behavior, or advanced interactivity.
- For plain static sites, keep `index.html`, CSS, JavaScript, images, and optional data files separated under `assets/` by default. See `site-structure.md`.

## Jekyll Rules

- Put site-wide settings in `_config.yml`.
- Use `_data/profile.yml` or similar for user-editable profile content.
- Use `{{ "/path" | relative_url }}` for internal assets and links.
- Store images, covers, videos, and QR codes under `assets/`.
- Exclude non-site docs such as skill notes or development docs from output when needed.

## Local Preview

For Jekyll:

```bash
bundle install
bundle exec jekyll build
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

For plain static sites:

```bash
python -m http.server 4000
```

Then open `http://127.0.0.1:4000`.

## Publish Flow

1. Confirm the target repository is `<username>.github.io`.
2. Confirm the branch used by GitHub Pages, usually `main`.
3. Build or preview locally when possible.
4. Stage only intended files.
5. Commit with a concise message.
6. Push to GitHub.
7. Wait for GitHub Pages to rebuild and propagate.

Do not commit, push, or publish unless the user explicitly approves that action. A request to build or preview a homepage is not approval to publish.

## Publish Readiness Snapshot

Before claiming a site is GitHub Pages ready, record:

- target repository, branch, and Pages source if known
- static/Jekyll compatibility and whether a build step is required
- local preview or build command and result
- relative asset/link strategy
- generated assets saved inside the repository
- unsupported backend/server features absent or clearly replaced
- remaining placeholders or private/unconfirmed content status
- staged-file scope if publishing was requested
- whether commit/push/deployment has been approved

If any item is unknown, state the assumption and the risk instead of presenting the site as ready.

## Compatibility Rules

- Use relative links such as `assets/css/styles.css` for plain static user sites unless the existing project has a different convention.
- For Jekyll project pages, use `relative_url` where needed.
- Do not reference local absolute paths like `C:\...` or `/Users/...` in deployable HTML, CSS, JS, data, or markdown.
- Avoid server-only form handlers, private APIs, local build artifacts, or environment-variable-dependent runtime features on plain GitHub Pages.
- Ensure every linked page in navigation exists before final delivery.
- Keep large media files compressed or link externally when repository size and load time would become a problem.

## Common Problems

- `404`: repository name is wrong, Pages source is wrong, branch not pushed, or build failed.
- Broken CSS/images: asset paths are absolute or missing `relative_url` on Jekyll project pages.
- Old page still showing: browser cache or GitHub Pages propagation delay.
- Build fails: unsupported plugin, missing dependency, invalid YAML, or malformed Liquid.
- Custom domain not working: DNS/CNAME not configured or HTTPS certificate still provisioning.

## Ordinary-User Guidance

- Do not require users to understand build tools unless necessary.
- Prefer one clear live URL and one editable profile file.
- Explain that GitHub Pages may take a few minutes to update.
- Keep instructions copy-pasteable and avoid unnecessary branching.
- When publishing is not requested, give preview instructions and stop before git commit/push.
