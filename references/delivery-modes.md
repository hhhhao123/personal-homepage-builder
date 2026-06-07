# Delivery Modes

Use delivery modes to match the workflow to the user's patience, clarity, assets, and publishing goal.

## Quick Launch

Use when the user wants a usable `github.io` page quickly.

- Ask the minimum confirmation round plus 3-5 content/style questions.
- Use GitHub Pages defaults and a simple static/Jekyll structure.
- Prioritize hero, short bio, top links, selected works, contact.
- Avoid optional media-heavy or CMS-like features unless the user already has assets ready.
- Output quality target: `Basic` or `Profile`.

## Deep Profile

Use when the user says they do not know their style, wants the page to feel personal, or has a complex identity.

- Run the full discovery path: identity, audience, profile signals, story, taste, avoids, links, media, language.
- Summarize and confirm the profile before implementation.
- Offer 2-3 design directions and recommend one.
- Output quality target: `Profile`, `Academic`, `Creator`, or `Premium`.

## Media Enhanced

Use when the user provides or asks for images, reference screenshots, video, music, covers, galleries, or visual assets.

- Use `media-assets.md`.
- Keep media optional and performance-aware.
- Require public-use/rights confirmation.
- Prefer user-provided covers before platform thumbnails.
- Output quality target: `Creator` or `Premium`.

## Publish

Use when the user wants to push or update the live site.

- Confirm intended files and current git state.
- Build/test before push when possible.
- Push to the GitHub Pages repository or provide clear manual steps.
- Do not stage unrelated changes.
- Use `github-pages-bootstrap.md` for ordinary-user publishing guidance.

## Quality Tiers

- `Basic`: one-page identity page, bio, links, contact, simple responsive design.
- `Profile`: richer bio, sections, works/projects, resume or experience, better theme.
- `Creator`: social platforms, content links, media cards, gallery or video works.
- `Academic`: research focus, publications, education, projects, CV/contact.
- `Premium`: custom visual direction, generated/media assets, refined motion, SEO/social preview, polished responsive QA.

## Routing Rules

- If the user says "quick", "simple", "go live", or "just make it work", choose Quick Launch.
- If the user says "I don't know my style" or wants strong personalization, choose Deep Profile.
- If the user uploads media or references, layer Media Enhanced onto Quick Launch or Deep Profile.
- If the user says "publish", "push", "deploy", or "sync to GitHub", choose Publish.
- Modes can combine, but keep one primary mode to avoid over-questioning.
