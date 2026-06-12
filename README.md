<p align="center">
  <img src="assets/images/personal-homepage-builder-banner-wide.png" alt="Personal Homepage Builder banner" width="720">
</p>

<h1 align="center">Personal Homepage Builder</h1>

<p align="center">
  An agent skill for turning vague personal signals into a confirmed homepage or small personal site plan, then into a distinctive GitHub Pages friendly implementation.
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
- a single-page, hybrid, or small multi-page personal site
- a lightweight static homepage that can be published without a backend
- a richer media-forward homepage using photos, video, music, or generated visual assets
- an existing or in-progress homepage that needs better design suggestions, dynamic effects, or scoped refinements

## Current Status

This is a beta skill. The current direction treats `personal-homepage-builder` as a beginner-friendly requirement translator and orchestration workflow, not a one-shot page generator.

The skill now emphasizes:

- low-friction beginner conversations with choices, contrasts, and non-code probe sketches
- session state across the whole homepage-design conversation
- lightweight personal signal intake for users starting from zero
- zero-prep onboarding that explains what materials may be useful later instead of demanding everything upfront
- minimum viable requirements before implementation
- user-confirmed requirements summaries before code
- brief lifecycle rules for patches, new versions, and post-launch changes
- single-page, hybrid, or multi-page page-map decisions before implementation
- explicit confirmation before editing existing page adjustments
- implementation authorization snapshots before file edits
- required output gates before style, implementation, review, and publish
- brief-to-site audits before final delivery
- explicit companion skill routing for taste, theme, frontend, media, and review work
- structured static site implementation instead of monolithic HTML by default
- iteration handling for existing or in-progress homepages when users ask for new ideas or scoped changes
- post-first-version visual iteration when the first result feels too plain, generic, or not like the user
- optional motion design that can be disabled, subtle, moderate, or expressive depending on the person, audience, and content
- forward-test prompts for future regression checks
- no emoji by default unless the user explicitly asks for emoji

## What The Skill Helps Agents Do

The skill guides an agent through a gated homepage workflow:

1. **Orient**: inspect project context, deployment target, user goal, and delivery mode.
2. **Intake**: extract facts, links, media, tone clues, privacy risks, and gaps.
3. **Interview**: ask grounded questions and choice-driven prompts about identity, audience, first impression, taste, and privacy boundaries.
4. **Reflect**: separate confirmed facts, inferred positioning, taste hypotheses, and open questions.
5. **Probe**: when useful, show direction cards, a rough text wireframe, or a content gap map so the user can react.
6. **Taste discovery**: use `design-taste-frontend` or an equivalent taste skill when available.
7. **Requirements confirmation**: produce a user-readable plan before code.
8. **Brief**: produce a user-confirmed `personal_homepage_brief`.
9. **Design routing**: declare which companion skills and fallbacks will be used.
10. **Implement or iterate**: build the site, or inspect an existing page and propose scoped improvements before editing.
11. **Review and publish**: validate UI, responsiveness, accessibility, git scope, and GitHub Pages publishing.

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

For a known adjustment:

```text
Use $personal-homepage-builder. I want the project section to look better and add subtle motion. Please propose the change first, then wait for my confirmation before editing code.
```

The skill should then guide discovery in short rounds, offer concrete choices when you are unsure, show non-code direction sketches when helpful, tell you what materials may be useful later, produce a homepage brief, route design/frontend companion skills when available, and only move into implementation after the direction is clear.

## Default Mode

Beginners do not need to choose a tier or know internal workflow names. If you are unsure, the agent should first spend enough time understanding your identity, audience, content, privacy boundaries, and taste to make the homepage personal, while avoiding an oversized custom site.

Internally, the skill may map your request to modes such as:

- quick/simple/go live soon: `Quick Launch`
- photos/video/music/visual assets: add `Media Enhanced`
- research/CV/papers/talks: `Academic`
- premium/custom/polished launch: `Premium`
- publish/push/deploy: add `Publish`

## How The Agent Should Ask You

The agent should not start by asking "what style do you want?" A better conversation starts with concrete questions:

```text
Which feels closer: a professional online name card, a work portfolio, or a personal self-introduction?
Who should open this page first?
What should visitors remember about you after 10 seconds?
What are the three things that must appear?
What should not be public?
```

If you do not have prepared materials, answer briefly. The skill is designed to work from rough signals and refine them into a clear brief. If you cannot describe a preference, the agent should offer 2-3 concrete directions or a rough text wireframe instead of repeating abstract questions.

After each answer, the agent should summarize what is confirmed, explain what is still missing, and ask only the next useful questions. It should not end the discovery after a few short turns unless the core materials, privacy boundaries, taste clues, and implementation constraints are covered.

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

The skill can start from almost nothing. You do not need all materials upfront, but better materials produce a more personal homepage over time. Useful inputs include:

- resume, CV, short bio, or self-introduction
- GitHub, LinkedIn, X/Twitter, Instagram, YouTube, Bilibili, Xiaohongshu, or other social links
- project, publication, writing, service, product, or portfolio links
- photos, avatar, screenshots, videos, music references, or existing brand assets
- examples of personal sites you like or dislike
- a rough answer to: who should visit this page, and what should they remember about you?

To save tokens, prepare a short Personal Signal Pack before starting: who you are, who the homepage is for, what visitors should remember, what to show, what to keep private, and what visual styles you like or dislike. See `references/personal-signal-intake.md`.

## Optional Inspiration Sources

You do not need design references to start. But if you want a more personal and visually specific homepage, spend a few minutes collecting examples before or during the discovery conversation.

The recommended beginner workflow is:

1. Browse the sites below for 10-20 minutes.
2. Save 3-5 links or screenshots that feel close to what you want.
3. For each reference, write one short note: what you like, what you dislike, and what should not be copied.
4. Paste those references into the agent and ask it to translate them into a homepage direction before writing code.

For dynamic effects and interaction ideas:

| Source | How to use it |
| --- | --- |
| [CodePen](https://codepen.io/) | Find specific hover effects, scroll reveals, cursor interactions, card transitions, animated backgrounds, or small visual experiments. Share direct links to the effects you like. |
| [React Bits](https://www.reactbits.dev/) | Useful for React-based homepages that need polished animated text, interactive components, backgrounds, or motion patterns. |
| [SiteInspire](https://www.siteinspire.com/) | Study how real sites use motion in context, so the homepage does not become a pile of disconnected effects. |

For page design, visual mood, and hero references:

| Source | How to use it |
| --- | --- |
| [Pinterest](https://www.pinterest.com/) | Collect mood boards, color references, typography feelings, layout references, and possible hero-image directions. |
| [Behance](https://www.behance.net/) | Find portfolio, personal brand, editorial, and visual identity references with stronger art direction. |
| [Awwwards Portfolio Websites](https://www.awwwards.com/websites/portfolio/) | Explore highly designed portfolio examples, especially for layout, motion rhythm, and first-screen impact. |
| [SiteInspire](https://www.siteinspire.com/) | Find cleaner, more mature website references that may be easier to adapt to a lightweight personal homepage. |

Both approaches are valid:

- **User-led reference gathering** is usually best for beginners because your own taste matters, and it saves tokens.
- **Agent-assisted reference research** is useful when you have a confirmed brief but no design references. Ask the agent to inspect specific links or find examples that match the brief, then summarize what should be borrowed and what should be avoided.

References should be used as inspiration, not copied. Ask the agent to adapt the layout logic, motion feeling, spacing, image strategy, or interaction pattern to your own identity and content. Do not copy proprietary layouts, code, images, or brand assets. If you want a strong first-screen background image, use your own photo, a properly licensed image, or ask the agent to generate an original visual asset.

Example prompt:

```text
Use $personal-homepage-builder. I found these references:
- CodePen link: I like the subtle hover and scroll reveal.
- Behance link: I like the editorial first screen and typography.
- Pinterest image: I like the color mood, but not the layout.

Please extract a design direction from these references, explain what fits my homepage brief, and wait for my confirmation before changing code.
```

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

- direction cards, rough text wireframes, and content gap maps during discovery
- a user-readable requirements summary before implementation
- a concise personal homepage brief
- a page model and page map: one page, homepage plus supporting pages, or a small multi-page site
- an internally inferred scope and quality target, so beginners do not need to choose workflow labels manually
- a content structure and public-facing profile summary
- homepage archetype and section recommendations
- visual direction, color, typography, image, media, and optional motion guidance
- a GitHub Pages compatible static site or updates to an existing site, with page files, CSS, JavaScript, images, and optional data kept maintainable by default
- scoped suggestions for existing pages, including where an effect belongs, why it fits, implementation complexity, and risks
- visual iteration diagnosis for first versions that need stronger style, better elements, references, or more fitting motion
- confirmed change plans before editing existing page adjustments
- brief patches or new brief versions when later changes alter the confirmed direction
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
  information_architecture:
    page_model: "hybrid"
    page_map:
      - path: "index.html"
        purpose: "focused overview and primary links"
      - path: "projects.html"
        purpose: "selected project details"
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

When these companion skills are installed and relevant to the current stage, the workflow expects the agent to actually invoke them, not just mention them. Taste, frontend/UI, and final review routing are mandatory when available; theme, image generation, and complex artifact routing are mandatory when that type of work is needed.

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
|   |-- images/
|   |   `-- personal-homepage-builder-banner-wide.png
|   `-- static-site-template/        # Starter structure for plain static sites
`-- references/
    |-- anti-patterns.md             # Failure modes to avoid
    |-- archetypes.md                # Homepage archetypes and structures
    |-- brief-examples.md            # Good and bad brief examples
    |-- brief-lifecycle.md           # Brief versioning and iteration rules
    |-- beginner-conversation-patterns.md # Low-friction beginner interaction patterns
    |-- beginner-validation-scenario.md # End-to-end beginner validation script
    |-- content-intake.md            # Source material extraction schema
    |-- delivery-modes.md            # Quick/deep/media/publish routing
    |-- enforcement-checklist.md     # Hard-stop authorization, placeholder, and brief-to-site checks
    |-- forward-tests.md             # Test prompts for future validation
    |-- github-pages-bootstrap.md    # GitHub Pages setup guidance
    |-- homepage-brief.md            # Canonical homepage brief schema
    |-- implementation.md            # Stack-aware implementation guidance
    |-- inspiration-intake.md        # Reference site and inspiration analysis workflow
    |-- interview.md                 # Discovery question bank
    |-- iteration-requests.md        # Existing-site change and suggestion workflow
    |-- media-assets.md              # Image, video, audio, and embed handling
    |-- motion-design.md             # Optional motion levels and interaction patterns
    |-- output-contracts.md          # Gates before design, implementation, review, and publish
    |-- personal-signal-intake.md    # Lightweight user signal intake
    |-- profile-schema.md            # Maintainable profile data contract
    |-- profile-signals.md           # Optional identity and taste signals
    |-- quality-checklist.md         # Final review checklist
    |-- requirements-template.md     # Requirements document and change baseline
    |-- session-protocol.md          # Conversation state and phase transitions
    |-- site-structure.md            # Default static site file organization
    |-- skill-routing.md             # Companion skill routing and fallbacks
    |-- social-links.md              # Contact and platform display rules
    |-- visual-iteration.md          # First-version visual diagnosis and revision workflow
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
