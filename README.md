<p align="center">
  <img src="assets/images/personal-homepage-builder-banner-wide.png" alt="Personal Homepage Builder banner" width="720">
</p>

<h1 align="center">Personal Homepage Builder</h1>

<p align="center">
  An agent skill for turning a person's identity, materials, taste, and publishing constraints into a distinctive GitHub Pages friendly personal homepage.
</p>

<p align="center">
  <a href="https://github.com/hhhhao123/personal-homepage-builder"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-personal--homepage--builder-24292f?logo=github"></a>
  <img alt="Agent Skill" src="https://img.shields.io/badge/Agent-Skill-0A7EBA">
  <img alt="GitHub Pages" src="https://img.shields.io/badge/GitHub%20Pages-ready-2E6B3F">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-E95D3C">
</p>

<p align="center">
  English | <a href="README.zh-CN.md">简体中文</a>
</p>

---

## Why This Skill Exists

Most people do not start a personal homepage project with a clean sitemap, brand system, and content strategy. They start with scattered materials: a resume, a GitHub profile, a few social links, some photos, half-formed preferences, and a vague sense of how they want to be seen.

`personal-homepage-builder` gives AI coding agents a reusable workflow for that messy beginning. It helps the agent ask better questions, extract useful material, translate personal signals into design direction, and build a homepage that feels specific instead of template-shaped.

Use it when you want to create or redesign:

- a `username.github.io` personal homepage
- a portfolio, resume site, creator page, or academic profile
- a personal brand site with social links and selected work
- a lightweight static homepage that can be published without a backend
- a richer media-forward homepage using photos, video, music, or generated visual assets

## What The Skill Helps Agents Do

The skill guides an agent through a complete homepage workflow:

1. **Orient**: inspect the existing project or choose a GitHub Pages friendly starting point.
2. **Extract**: read resumes, bios, notes, links, photos, screenshots, and other source materials.
3. **Interview**: ask grounded questions about identity, audience, first impression, taste, and privacy boundaries.
4. **Reflect**: summarize what is known, what is inferred, and what still needs confirmation.
5. **Classify**: choose a homepage archetype and section structure.
6. **Define style**: turn personality, culture, references, and dislikes into a concrete visual direction.
7. **Brief**: produce a `personal_homepage_brief` that can drive implementation.
8. **Implement**: build or update the site using the current project stack.
9. **Review and publish**: test the result and prepare it for GitHub Pages.

The core rule is simple: do not begin by asking "what style do you want?" Most users cannot answer that well. The skill pushes the agent to discover identity first, then derive design choices from evidence.

## Install

Install the skill from this repository with any skill-compatible agent setup. For Codex or other environments that support the `skills` CLI, use:

```powershell
npx skills add https://github.com/hhhhao123/personal-homepage-builder --skill personal-homepage-builder
```

Restart your agent after installation so the new skill can be discovered.

## Use With Other Agents

This repository is not tied to one agent runtime. If your agent system does not support the `skills` CLI, give the agent this repository, or copy `SKILL.md` plus the `references/` folder into that system's skill, instruction, or knowledge format.

At minimum, the agent needs:

- `SKILL.md` for the main workflow
- `references/` for interview prompts, content extraction, style directions, implementation guidance, and quality checks
- optional companion skills or equivalent design/front-end capabilities when available

## What To Prepare

The skill can start from almost nothing, but better materials produce a more personal homepage. Useful inputs include:

- resume, CV, short bio, or self-introduction
- GitHub, LinkedIn, X/Twitter, Instagram, YouTube, Bilibili, Xiaohongshu, or other social links
- project, publication, writing, service, product, or portfolio links
- photos, avatar, screenshots, videos, music references, or existing brand assets
- examples of personal sites you like or dislike
- a rough answer to: who should visit this page, and what should they remember about you?

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

Depending on the request and available materials, the agent can produce:

- a concise personal homepage brief
- a content structure and public-facing profile summary
- homepage archetype and section recommendations
- visual direction, color, typography, image, media, and motion guidance
- a GitHub Pages compatible static site or updates to an existing site
- a publish-ready commit and push workflow when the user asks for GitHub publishing

## Example Brief

The skill asks the agent to create a compact brief before implementation, so design and code are driven by confirmed intent instead of guesses:

```yaml
personal_homepage_brief:
  identity:
    primary_role: "AI researcher and builder"
    personal_elements: ["open-source projects", "writing", "selected photos"]
  audience:
    primary: "collaborators, recruiters, and peers"
  goal:
    first_impression: "thoughtful, technical, approachable"
    remembered_for: "turning research ideas into usable tools"
  content:
    required_sections: ["intro", "projects", "writing", "social links"]
  style:
    direction_name: "quiet technical editorial"
    must_avoid: ["generic portfolio grid", "overly flashy effects"]
  constraints:
    hosting: "GitHub Pages"
```

## Recommended Companion Skills

This skill works on its own, but homepage quality improves when these companion skills are available:

| Skill | Why install it | Install / source |
| --- | --- | --- |
| `frontend-design` | Produces more distinctive, production-grade homepage UI instead of generic layouts. | [`npx skills add https://github.com/anthropics/skills --skill frontend-design`](https://www.skills.sh/anthropics/skills/frontend-design) |
| `theme-factory` | Helps create or apply consistent color and typography systems. | [`npx skills add https://github.com/anthropics/skills --skill theme-factory`](https://www.skills.sh/anthropics/skills/theme-factory) |
| `web-design-guidelines` | Provides a final UI, UX, and accessibility review pass. | [`npx skills add https://github.com/vercel-labs/agent-skills --skill web-design-guidelines`](https://www.skills.sh/vercel-labs/agent-skills/web-design-guidelines) |
| `web-artifacts-builder` | Useful only when the homepage is implemented as a complex React/Tailwind/shadcn artifact. | [`npx skills add https://github.com/anthropics/skills --skill web-artifacts-builder`](https://www.skills.sh/anthropics/skills/web-artifacts-builder) |
| `find-skills` | Helps users discover and install additional skills when the current set is not enough. | [`npx skills add https://github.com/vercel-labs/add-skill --skill find-skills`](https://www.skills.sh/vercel-labs/add-skill/find-skills) |
| `skill-installer` | Codex system skill for installing skills from curated lists or GitHub paths; usually already available in Codex. | [Source: `openai/skills`](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) |

The skill does not install companion skills automatically. Install them separately if you want your agent to use them during homepage creation.

## Repository Layout

```text
personal-homepage-builder/
|-- LICENSE                          # MIT license
|-- SKILL.md                         # Main skill instructions
|-- README.md                        # Human-facing repository overview
|-- README.zh-CN.md                  # Simplified Chinese repository overview
|-- agents/
|   `-- openai.yaml                  # Optional OpenAI/Codex UI metadata
|-- assets/
|   `-- images/
|       `-- personal-homepage-builder-banner-wide.png
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

This skill is built around that premise. It treats resumes, MBTI labels, hobbies, favorite media, screenshots, photos, work links, and social platforms as signals. Some are strong evidence, some are just clues. The agent is instructed to confirm the meaning with the user before turning those signals into public-facing design and content.
