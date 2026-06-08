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
- an existing or in-progress homepage that needs better design suggestions, dynamic effects, or scoped refinements

## Current Status

This is a beta skill. The current direction treats `personal-homepage-builder` as a gated discovery and orchestration workflow, not a one-shot page generator.

The skill now emphasizes:

- session state across the whole homepage-design conversation
- lightweight personal signal intake for users starting from zero
- required output gates before style, implementation, review, and publish
- explicit companion skill routing for taste, theme, frontend, media, and review work
- structured static site implementation instead of monolithic HTML by default
- iteration handling for existing or in-progress homepages when users ask for new ideas or scoped changes
- optional motion design that can be disabled, subtle, moderate, or expressive depending on the person, audience, and content
- forward-test prompts for future regression checks
- no emoji by default unless the user explicitly asks for emoji

## What The Skill Helps Agents Do

The skill guides an agent through a gated homepage workflow:

1. **Orient**: inspect project context, deployment target, user goal, and delivery mode.
2. **Intake**: extract facts, links, media, tone clues, privacy risks, and gaps.
3. **Interview**: ask grounded questions about identity, audience, first impression, taste, and privacy boundaries.
4. **Reflect**: separate confirmed facts, inferred positioning, taste hypotheses, and open questions.
5. **Taste discovery**: use `design-taste-frontend` or an equivalent taste skill when available.
6. **Brief**: produce a user-confirmed `personal_homepage_brief`.
7. **Design routing**: declare which companion skills and fallbacks will be used.
8. **Implement or iterate**: build the site, or inspect an existing page and propose scoped improvements before editing.
9. **Review and publish**: validate UI, responsiveness, accessibility, git scope, and GitHub Pages publishing.

The core rule is simple: do not begin by asking "what style do you want?" Most users cannot answer that well. The skill pushes the agent to discover identity first, then derive design choices from evidence.

This skill is a discovery and orchestration layer. It helps clarify the user's identity and design requirements first, then routes taste, theme, frontend, image, and review work to the right companion skills when they are available.

## Install

Install the skill from this repository with any skill-compatible agent setup. For Codex or other environments that support the `skills` CLI, use:

```powershell
npx skills add https://github.com/hhhhao123/personal-homepage-builder --skill personal-homepage-builder
```

Restart your agent after installation so the new skill can be discovered.

## Quick Start For Beginners

After installing this skill and any companion skills, open your agent and start with one plain request. You do not need to know web design terms, choose a style name, or prepare a complete site plan.

For a new homepage:

```text
Use $personal-homepage-builder. I want to build a personal github.io homepage, but I do not know what style I want. Please guide me step by step.
```

For an existing or in-progress homepage:

```text
Use $personal-homepage-builder. My homepage is already partly built. Please inspect it and suggest how to improve the design before changing code.
```

For a design question with no clear idea yet:

```text
Use $personal-homepage-builder. I feel the homepage may need dynamic elements, but I do not know what would fit. Look at the current page and propose a few options.
```

The skill should then ask a small number of grounded questions, produce a homepage brief, route design/frontend companion skills when available, and only move into implementation after the direction is clear.

## Default Mode

Beginners do not need to choose a tier. If you are unsure, the agent should default to:

```yaml
delivery_mode: Deep Profile
quality_tier: Profile
motion_strategy.level: subtle
```

That means the agent will spend enough time understanding your identity, audience, content, privacy boundaries, and taste to make the homepage personal, while avoiding an oversized custom site.

The agent should change the mode when your request is clearer:

- quick/simple/go live soon: `Quick Launch`
- photos/video/music/visual assets: add `Media Enhanced`
- research/CV/papers/talks: `Academic`
- premium/custom/polished launch: `Premium`
- publish/push/deploy: add `Publish`

## How The Agent Should Ask You

The agent should not start by asking "what style do you want?" A better conversation starts with concrete questions:

```text
Who should visit this homepage?
What should they remember about you after 10 seconds?
Which links, projects, photos, or social accounts must be included?
What should not be public?
Do you want the page to feel quiet, technical, expressive, editorial, playful, formal, or something else?
```

If you do not have prepared materials, answer briefly. The skill is designed to work from rough signals and refine them into a clear brief.

## Suggested First Message

To save tokens and reduce back-and-forth, paste a compact Personal Signal Pack:

```text
Use $personal-homepage-builder.

Personal Signal Pack:
- Who I am:
- Audience:
- What visitors should remember:
- Must-show content:
- Do not publish:
- Links:
- Images or media:
- Visual styles I like:
- Visual styles I dislike:
- Existing homepage or repository:
- Motion preference: none / subtle / moderate / expressive / not sure
```

You can leave fields blank. The agent should ask only for the missing high-impact details.

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

To save tokens, prepare a short Personal Signal Pack before starting: who you are, who the homepage is for, what visitors should remember, what to show, what to keep private, and what visual styles you like or dislike. See `references/personal-signal-intake.md`.

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

```text
Use $personal-homepage-builder. My homepage is already partly built, but I think it may need dynamic elements. Look at the current page and suggest what would fit.
```

## What You Get

Depending on the request and available materials, the agent can produce:

- a concise personal homepage brief
- an inferred delivery mode and quality tier, so beginners do not need to choose one manually
- a content structure and public-facing profile summary
- homepage archetype and section recommendations
- visual direction, color, typography, image, media, and optional motion guidance
- a GitHub Pages compatible static site or updates to an existing site, with CSS, JavaScript, images, and optional data separated under `assets/` by default
- scoped suggestions for existing pages, including where an effect belongs, why it fits, implementation complexity, and risks
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
  motion_strategy:
    level: "subtle"
    reduced_motion: "disable reveal animations and keep hover/focus feedback immediate"
  constraints:
    hosting: "GitHub Pages"
    emoji_policy: "no emoji unless explicitly requested"
  implementation:
    companion_skills: ["design-taste-frontend", "frontend-design", "theme-factory", "web-design-guidelines"]
```

## Recommended Companion Skills

This skill works on its own, but homepage quality improves when these companion skills are available:

| Skill | Why install it | Install / source |
| --- | --- | --- |
| `design-taste-frontend` | Reads the brief and infers the right design direction, visual density, motion level, and anti-template constraints before UI work begins. | [`npx skills add https://github.com/Leonxlnx/taste-skill --skill design-taste-frontend`](https://www.skills.sh/leonxlnx/taste-skill/design-taste-frontend) |
| `frontend-design` | Produces more distinctive, production-grade homepage UI instead of generic layouts. | [`npx skills add https://github.com/anthropics/skills --skill frontend-design`](https://www.skills.sh/anthropics/skills/frontend-design) |
| `theme-factory` | Helps create or apply consistent color and typography systems. | [`npx skills add https://github.com/anthropics/skills --skill theme-factory`](https://www.skills.sh/anthropics/skills/theme-factory) |
| `web-design-guidelines` | Provides a final UI, UX, and accessibility review pass. | [`npx skills add https://github.com/vercel-labs/agent-skills --skill web-design-guidelines`](https://www.skills.sh/vercel-labs/agent-skills/web-design-guidelines) |
| `web-artifacts-builder` | Useful only when the homepage is implemented as a complex React/Tailwind/shadcn artifact. | [`npx skills add https://github.com/anthropics/skills --skill web-artifacts-builder`](https://www.skills.sh/anthropics/skills/web-artifacts-builder) |
| `find-skills` | Helps users discover and install additional skills when the current set is not enough. | [`npx skills add https://github.com/vercel-labs/add-skill --skill find-skills`](https://www.skills.sh/vercel-labs/add-skill/find-skills) |
| `skill-installer` | Codex system skill for installing skills from curated lists or GitHub paths; usually already available in Codex. | [Source: `openai/skills`](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) |

The skill does not install companion skills automatically. Install them separately if you want your agent to use them during homepage creation.

When this skill is active in a homepage-design conversation, the agent should keep using this workflow for the rest of that conversation unless the user explicitly exits it. During taste interpretation and UI customization, it should use the relevant companion design/frontend skills when available. Emoji are disabled by default in briefs, copy, UI labels, and generated content unless the user explicitly asks for them.

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
    |-- anti-patterns.md             # Failure modes to avoid
    |-- archetypes.md                # Homepage archetypes and structures
    |-- content-intake.md            # Source material extraction schema
    |-- delivery-modes.md            # Quick/deep/media/publish routing
    |-- forward-tests.md             # Test prompts for future validation
    |-- github-pages-bootstrap.md    # GitHub Pages setup guidance
    |-- homepage-brief.md            # Canonical homepage brief schema
    |-- implementation.md            # Stack-aware implementation guidance
    |-- interview.md                 # Discovery question bank
    |-- iteration-requests.md        # Existing-site change and suggestion workflow
    |-- media-assets.md              # Image, video, audio, and embed handling
    |-- motion-design.md             # Optional motion levels and interaction patterns
    |-- output-contracts.md          # Gates before design, implementation, review, and publish
    |-- personal-signal-intake.md    # Lightweight user signal intake
    |-- profile-schema.md            # Maintainable profile data contract
    |-- profile-signals.md           # Optional identity and taste signals
    |-- quality-checklist.md         # Final review checklist
    |-- session-protocol.md          # Conversation state and phase transitions
    |-- site-structure.md            # Default static site file organization
    |-- skill-routing.md             # Companion skill routing and fallbacks
    |-- social-links.md              # Contact and platform display rules
    `-- style-directions.md          # Style direction translation patterns
```

## Roadmap

Planned improvements for later beta iterations:

- add more forward-test transcripts from real usage
- refine academic, creator, freelancer, and researcher homepage archetypes
- add richer examples of accepted and rejected homepage briefs
- improve fallback behavior when companion skills are unavailable
- add example homepage projects generated from the workflow

## Design Philosophy

Personal homepages should not all look like the same portfolio template. A strong homepage should make the visitor understand three things quickly:

- who this person is
- what they want to be known for
- why their work, story, or taste is memorable

This skill is built around that premise. It treats resumes, MBTI labels, hobbies, favorite media, screenshots, photos, work links, and social platforms as signals. Some are strong evidence, some are just clues. The agent is instructed to confirm the meaning with the user before turning those signals into public-facing design and content.

The intended sequence is: clarify the person, produce a stronger design brief, then use specialized taste and frontend skills to implement a more customized personal homepage.
