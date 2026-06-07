---
name: personal-homepage-builder
description: Conversationally discover a person's identity, audience, story, taste, constraints, goals, source materials, media assets, and social links, then turn that understanding into a distinctive GitHub Pages friendly personal homepage brief and implementation. Use when users want to create, redesign, personalize, or publish a github.io homepage, personal homepage, portfolio, academic profile, creator site, resume site, freelancer page, or personal brand site, especially when they are unsure what style or structure they want, want to upload/paste content for the agent to organize, or want to include reference images, photos, videos, music, or work links.
---

# Personal Homepage Builder

## Purpose

Guide a user from vague self-expression or raw personal materials to a buildable personal homepage. The default target is a low-configuration `github.io` personal site: one repository, static output, easy links, and no required backend. The skill prioritizes discovery before design or code: understand the person, extract what they want to show, summarize the emerging identity, then use frontend/design/image/media skills to implement a homepage that feels specific to them.

## Core Rule

Do not ask "what style do you want?" as the first design question. Most users cannot answer that. Ask grounded questions about identity, audience, memory, taste, personality signals, and dislikes; translate those answers into design choices.

When this skill is invoked for a homepage discovery, design, redesign, personalization, or publishing conversation, treat it as the controlling workflow for the rest of that conversation until the user explicitly exits this workflow or gives a superseding instruction. Do not jump directly into page design, UI customization, code implementation, or publishing outside this skill's discovery, reflection, brief, implementation, and review sequence.

Use this skill as the discovery and orchestration layer. Its job is to help the user understand and articulate their identity, taste, audience, constraints, and content priorities, then route specialized work to the right companion skills. It is not a substitute for dedicated frontend, taste, theme, image, or UI review skills.

Do not use emoji in homepage briefs, agent questions, homepage copy, UI labels, status text, generated markdown, or final content unless the user explicitly asks for emoji. Prefer precise words, icons from the implementation's icon system, or plain labels.

Treat MBTI, zodiac signs, enneagram, hobbies, favorite media, and similar inputs as optional self-expression clues, not scientific truths or fixed personality rules. Use them to open conversation and generate aesthetic hypotheses; always confirm the actual design meaning with the user.

Treat images, videos, music, reference screenshots, and platform links as optional advanced customization. Keep the default site light and GitHub Pages friendly; add rich media only when it supports the user's identity, work, or audience.

Always run a clarification dialogue before finalizing the brief. Uploaded materials can reduce repeated questions, but they cannot replace user-confirmed intent, audience, public/private boundaries, and desired first impression.

Companion skills such as `design-taste-frontend` from Taste Skill, `frontend-design`, `theme-factory`, `web-design-guidelines`, and `web-artifacts-builder` are optional enhancements. When these companion skills or equivalent capabilities are available in the current agent system, explicitly use them at the relevant workflow stages before falling back to general capability. Do not assume they are installed, do not try to install them automatically, and do not block the homepage workflow if they are unavailable. If a relevant companion skill is unavailable, say so briefly and continue with the matching bundled reference file or general capability. If the user asks how to improve design quality before using this skill, point them to the repository README for recommended companion skill installation.

Use companion skills with this routing:

- Use `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent taste/design-direction skill when interpreting the user's taste, references, aesthetic dislikes, homepage vibe, layout variance, motion intensity, and visual density.
- Use `theme-factory` or an equivalent theme skill when choosing or creating color, typography, spacing, and token systems.
- Use `frontend-design` or an equivalent frontend design skill before implementing or substantially redesigning homepage UI.
- Use `web-artifacts-builder` only when the homepage is implemented as a complex React/Tailwind/shadcn artifact.
- Use `web-design-guidelines` or an equivalent review skill before final delivery for UI, UX, accessibility, responsive behavior, and text-fit checks.

## Workflow

1. **Orient**
   - Inspect the current project if one exists: stack, pages, assets, deployment path, git state.
   - If no project exists, default to a GitHub Pages compatible static site unless the user needs a different host.
   - Prefer a `username.github.io` repository for ordinary personal homepages because it has the lowest publishing friction.
   - If the user provides documents, pasted text, media assets, or reference screenshots, treat them as source materials and extract homepage-ready content before asking broad questions.
   - Choose a primary delivery mode from `references/delivery-modes.md`.
   - When asking about or working with libraries, frameworks, SDKs, CLIs, or cloud services, use the current agent system's official documentation lookup tool when available, such as Context7. If no such tool is available, rely on official documentation or the environment's best available retrieval path.

2. **Extract Materials**
   - Read uploaded or pasted materials when available: resume/CV, bio, personal notes, social profile text, portfolio lists, publications, service descriptions, articles, transcripts, link collections, media references, photos, video links, or music links.
   - Extract candidate facts, stories, sections, links, achievements, tone clues, media assets, and gaps.
   - Use `references/content-intake.md` for the extraction schema.
   - Use `references/media-assets.md` for media handling and autoplay constraints.
   - Do not publish sensitive or private content unless the user confirms it belongs on the public homepage.

3. **Interview**
   - Ask 1-3 high-impact questions per round.
   - Prefer broad multiple-choice options plus an "Other" path when the UI supports it.
   - Start with identity, audience, and desired first impression before visual details, unless source materials already answer them.
   - Offer choices that cover professional goals, personality, cultural taste, life atmosphere, and visual avoids.
   - When taste signals become central, use `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent taste skill if available to interpret the user's aesthetic clues before committing to a design direction.
   - Collect contact and social links as first-class content, including domestic and international platforms.
   - If source materials were provided, ask a targeted confirmation round instead of skipping the interview.
   - If no source materials were provided, run the broader discovery path.
   - Use `references/interview.md` for question prompts.

4. **Reflect**
   - After each meaningful round, summarize the current understanding in plain language.
   - Include identity, audience, tone, memory point, content priorities, visual likes, and visual avoids.
   - Include which user-provided signals are strong evidence and which are only tentative clues.
   - Distinguish extracted facts from inferred positioning and from user-confirmed choices.
   - Invite corrections before committing to a design direction.
   - Do not proceed to implementation until the user has accepted or corrected the summarized profile.

5. **Classify**
   - Choose a homepage archetype from `references/archetypes.md`.
   - Hybridize when needed, but name the primary archetype.
   - Convert vague preferences into concrete homepage structure and design implications.

6. **Define Style**
   - Offer 2-3 style directions based on the user's answers, not generic templates.
   - Use `references/style-directions.md` for direction patterns and translation rules.
   - Before finalizing a style direction or UI customization plan, use `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent taste skill when available. Use its output to sharpen the design read, anti-template constraints, layout variance, motion intensity, and visual density.
   - Create or choose a theme with `theme-factory` when available.
   - Use `imagegen` when a distinctive raster hero image, portrait treatment, texture, or visual asset would make the page feel personal.

7. **Create The Brief**
   - Produce a concise `personal-homepage-brief` before implementation.
   - Include: identity, audience, goal, tone, memory point, source materials, content modules, visual system, image strategy, technical constraints, and explicit avoids.
   - For maintainable sites, map the brief into the profile schema described in `references/profile-schema.md`.
   - If the user asks for execution and enough information exists, implement directly after the brief.

8. **Implement**
   - Prefer the existing project stack and conventions.
   - For new GitHub Pages sites, use `references/github-pages-bootstrap.md`.
   - Use `frontend-design` for page/interface design quality before implementing or revising UI.
   - Use `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent taste skill when available before translating the brief into concrete visual layout, motion, density, and anti-template decisions.
   - Use `web-artifacts-builder` only for new complex React/Tailwind/shadcn artifacts; do not force it onto static/Jekyll sites.
   - Keep changes scoped to the homepage/site request.
   - Save generated project assets inside the workspace, not only in a tool output directory.

9. **Review And Publish**
   - Build/test the site with the repo's existing commands.
   - Use `web-design-guidelines` for final UI/accessibility review when available.
   - If the user wants GitHub publishing, commit and push intentionally; do not stage unrelated changes silently.

## Brief Template

```yaml
personal_homepage_brief:
  identity:
    primary_role:
    secondary_traits:
    personal_elements:
    personality_signals:
    signal_confidence:
  audience:
    primary:
    secondary:
  goal:
    first_impression:
    remembered_for:
  content:
    source_materials:
    extracted_facts:
    inferred_positioning:
    needs_confirmation:
    priority_order:
    required_sections:
    optional_sections:
    social_links:
    media_assets:
  style:
    direction_name:
    tone_keywords:
    color_notes:
    typography_notes:
    image_strategy:
    video_strategy:
    audio_strategy:
    motion_strategy:
  constraints:
    stack:
    hosting: GitHub Pages by default
    timeline:
    emoji_policy: no emoji unless explicitly requested
    companion_skill_routing:
    must_keep:
    must_avoid:
  implementation:
    delivery_mode:
    quality_tier:
    pages:
    assets:
    validation:
```

## Decision Guidance

- If the user is unsure, ask about feelings and examples instead of design vocabulary.
- If the user uploads or pastes content, extract and organize first, then ask only for missing or high-impact choices.
- If source materials seem complete, still confirm the public-facing identity, primary audience, first impression, and privacy boundaries.
- If the user gives a profession, infer likely audience needs but confirm the emotional tone.
- If the user gives MBTI, zodiac, or similar labels, ask what parts feel accurate and what parts should not be represented.
- If the user has a strong hobby or taste, use it as a memorable accent, not necessarily the whole site.
- If the user wants speed, generate a smaller brief and implement a polished v1.
- If the user wants depth, run a longer interview and produce a richer design system.
- If the site should be maintained over time, create or update profile data first instead of hard-coding content into HTML.
- If the user has many social platforms, group them by purpose instead of showing every link with equal visual weight.
- If the user wants simple publishing, choose GitHub Pages and avoid backend-only features such as server contact forms.
- If the user has no assets, propose an image strategy: generated hero, abstract texture, typography-first, or existing photo treatment.
- If the user wants music or video, explain that muted background video is feasible, but audio autoplay is unreliable and should use a visible play control.
- If the user has video links, support embedded or linked work cards with user-provided covers or platform thumbnails when feasible.

## References

- `references/interview.md`: staged question bank for discovering user needs and taste.
- `references/content-intake.md`: extraction workflow for uploaded documents and pasted text.
- `references/media-assets.md`: images, reference screenshots, video, music, embeds, covers, and autoplay guidance.
- `references/delivery-modes.md`: quick/deep/media/publish routing and quality tiers.
- `references/profile-schema.md`: maintainable profile data contract for future edits.
- `references/github-pages-bootstrap.md`: ordinary-user GitHub Pages setup and publish guidance.
- `references/archetypes.md`: homepage archetypes and recommended section structures.
- `references/style-directions.md`: style direction patterns and preference translation rules.
- `references/profile-signals.md`: optional identity/personality/culture signals and how to use them safely.
- `references/implementation.md`: stack-aware implementation guidance.
- `references/social-links.md`: supported contact/social platforms and display rules.
- `references/quality-checklist.md`: final review checklist.
