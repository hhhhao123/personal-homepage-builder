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
