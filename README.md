<p align="center">
  <img src="assets/images/personal-homepage-builder-logo.svg" alt="Personal Homepage Builder logo" width="720">
</p>

<h1 align="center">Personal Homepage Builder</h1>

<p align="center">
  A Codex skill for turning a person's identity, materials, taste, and publishing constraints into a distinctive GitHub Pages friendly personal homepage.
</p>

<p align="center">
  <a href="https://github.com/hhhhao123/personal-homepage-builder"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-personal--homepage--builder-24292f?logo=github"></a>
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-0A7EBA">
  <img alt="GitHub Pages" src="https://img.shields.io/badge/GitHub%20Pages-ready-2E6B3F">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-E95D3C">
</p>

---

## Why This Skill Exists

Most people do not start a personal homepage project with a clean sitemap, brand system, and content strategy. They start with scattered materials: a resume, a GitHub profile, a few social links, some photos, half-formed preferences, and a vague sense of how they want to be seen.

`personal-homepage-builder` gives Codex a reusable workflow for that messy beginning. It helps the agent ask better questions, extract useful material, translate personal signals into design direction, and build a homepage that feels specific instead of template-shaped.

Use it when you want to create or redesign:

- a `username.github.io` personal homepage
- a portfolio, resume site, creator page, or academic profile
- a personal brand site with social links and selected work
- a lightweight static homepage that can be published without a backend
- a richer media-forward homepage using photos, video, music, or generated visual assets

## What The Skill Helps Codex Do

The skill guides Codex through a complete homepage workflow:

1. **Orient**: inspect the existing project or choose a GitHub Pages friendly starting point.
2. **Extract**: read resumes, bios, notes, links, photos, screenshots, and other source materials.
3. **Interview**: ask grounded questions about identity, audience, first impression, taste, and privacy boundaries.
4. **Reflect**: summarize what is known, what is inferred, and what still needs confirmation.
5. **Classify**: choose a homepage archetype and section structure.
6. **Define style**: turn personality, culture, references, and dislikes into a concrete visual direction.
7. **Brief**: produce a `personal_homepage_brief` that can drive implementation.
8. **Implement**: build or update the site using the current project stack.
9. **Review and publish**: test the result and prepare it for GitHub Pages.

The core rule is simple: do not begin by asking "what style do you want?" Most users cannot answer that well. The skill pushes Codex to discover identity first, then derive design choices from evidence.

## Install

Install the skill from this repository:

```powershell
npx skills add https://github.com/hhhhao123/personal-homepage-builder --skill personal-homepage-builder
```

Restart Codex after installation so the new skill can be discovered.

## Example Prompts

```text
Use $personal-homepage-builder to help me build a personal github.io homepage.
```

```text
Use $personal-homepage-builder. I have a resume, GitHub profile, photos, and a few social links. Help me turn them into a homepage.
```

```text
Use $personal-homepage-builder to redesign my existing personal site so it feels more like me and less like a template.
```

```text
Use $personal-homepage-builder to create a portfolio homepage for my research, projects, writing, and contact links.
```

## What You Get

Depending on the request and available materials, Codex can produce:

- a concise personal homepage brief
- a content structure and public-facing profile summary
- homepage archetype and section recommendations
- visual direction, color, typography, image, media, and motion guidance
- a GitHub Pages compatible static site or updates to an existing site
- a publish-ready commit and push workflow when the user asks for GitHub publishing

## Companion Skills

This skill works on its own, but homepage quality improves when these companion skills are available:

| Skill | Why it helps |
| --- | --- |
| `frontend-design` | Improves page composition, visual polish, responsive behavior, and product-level UI quality. |
| `theme-factory` | Helps create or apply a coherent color and typography system. |
| `web-design-guidelines` | Adds a final UI, UX, accessibility, and responsive design review pass. |
| `web-artifacts-builder` | Useful for complex React, Tailwind, or shadcn-based homepage artifacts. |
| `find-skills` | Helps discover extra skills when a project needs something outside this workflow. |

The skill does not install companion skills automatically. Install them separately if you want Codex to use them during homepage creation.

## Repository Layout

```text
personal-homepage-builder/
|-- SKILL.md                         # Main skill instructions
|-- README.md                        # Human-facing repository overview
|-- agents/
|   `-- openai.yaml                  # Codex UI metadata
|-- assets/
|   `-- images/
|       `-- personal-homepage-builder-logo.svg
`-- references/
    |-- archetypes.md                # Homepage archetypes and structures
    |-- content-intake.md            # Source material extraction schema
    |-- delivery-modes.md            # Quick/deep/media/publish routing
    |-- github-pages-bootstrap.md    # GitHub Pages setup guidance
    |-- implementation.md            # Stack-aware implementation guidance
    |-- interview.md                 # Discovery question bank
    |-- media-assets.md              # Image, video, audio, and embed handling
    |-- profile-schema.md            # Maintainable profile data contract
    |-- profile-signals.md           # Optional identity and taste signals
    |-- quality-checklist.md         # Final review checklist
    |-- social-links.md              # Contact and platform display rules
    `-- style-directions.md          # Style direction translation patterns
```

## Design Philosophy

Personal homepages should not all look like the same portfolio template. A strong homepage should make the visitor understand three things quickly:

- who this person is
- what they want to be known for
- why their work, story, or taste is memorable

This skill is built around that premise. It treats resumes, MBTI labels, hobbies, favorite media, screenshots, photos, work links, and social platforms as signals. Some are strong evidence, some are just clues. Codex is instructed to confirm the meaning with the user before turning those signals into public-facing design and content.
