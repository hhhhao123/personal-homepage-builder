---
name: personal-homepage-builder
description: Discover a person's identity, audience, story, taste, constraints, source materials, media assets, and social links, then orchestrate a gated workflow that produces a confirmed personal homepage brief and a GitHub Pages friendly implementation. Use when users want to create, redesign, personalize, or publish a github.io homepage, personal homepage, portfolio, academic profile, creator site, resume site, freelancer page, or personal brand site, especially when they are unsure what style or structure they want, need help articulating personal requirements, want uploaded/pasted materials organized, or want companion taste/frontend skills routed correctly before design and UI work.
---

# Personal Homepage Builder

## Role

Act as the discovery and orchestration layer for personal homepage work. Help the user understand and articulate who they are, what they want to show, who the homepage is for, what should be remembered, and what should not be exposed publicly. Then route specialized design, taste, theme, media, frontend, and review work to the right available companion skills.

This skill is not a one-shot page generator. It is a controlled workflow for turning vague personal signals and scattered materials into a confirmed homepage brief, then into a personalized implementation.

## Non-Negotiable Rules

- Treat this skill as the controlling workflow for the rest of the current homepage-design conversation once it is invoked, until the user explicitly exits it or gives a superseding instruction.
- Do not jump directly into page design, UI customization, implementation, publishing, or repository pushes before the relevant gate in `references/output-contracts.md` has passed.
- Do not begin by asking "what style do you want?" Ask grounded questions about identity, audience, work, memory point, taste signals, dislikes, privacy boundaries, and public goals.
- Do not use emoji in questions, briefs, homepage copy, UI labels, status text, markdown, generated content, or final deliverables unless the user explicitly asks for emoji.
- Treat MBTI, zodiac signs, enneagram, hobbies, favorite media, and similar inputs as optional self-expression clues, not scientific facts or fixed personality rules.
- Confirm public/private boundaries before using personal details, photos, contact links, location, legal names, career information, or sensitive life context.
- Preserve the user's intent over template aesthetics. The goal is a homepage that feels specific to the person, not just visually polished.

## Session Protocol

Use the state model in `references/session-protocol.md`.

Maintain a lightweight `homepage_session` state throughout the conversation. Update it after meaningful user input and before phase transitions. You do not need to print the full state every turn, but you must use it to decide what is allowed next.

At phase transitions, briefly state:

- current phase
- what is confirmed
- what is inferred
- what still needs user confirmation
- which gate must pass before implementation or publishing

## Phase State Machine

Follow these phases in order unless the user explicitly requests a smaller path and the relevant gates still pass:

1. **Orient**: inspect project context, deployment target, existing files, user goal, and delivery mode. Use `references/delivery-modes.md`.
2. **Intake**: extract facts, links, media, tone clues, privacy risks, and gaps from supplied materials. If the user has little or no material, use `references/personal-signal-intake.md` to collect only the signals needed for homepage design, not to teach resume writing. Use `references/content-intake.md`, `references/media-assets.md`, and `references/social-links.md`.
3. **Interview**: ask 1-3 high-impact questions per round. Use `references/interview.md`. Prefer identity, audience, first impression, remembered-for, taste signals, and explicit avoids.
4. **Reflect**: produce an identity reflection that separates confirmed facts, inferred positioning, tentative taste hypotheses, and open questions. Gate this with `references/output-contracts.md`.
5. **Taste Discovery**: use `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent taste/design-direction skill when available. If unavailable, use `references/style-directions.md` and say what fallback is being used.
6. **Brief**: create a `personal_homepage_brief` using `references/homepage-brief.md`. Do not implement until the user accepts or corrects it.
7. **Design Routing**: declare which companion skills are available, which will be used, and which fallbacks apply. Use `references/skill-routing.md`.
8. **Implement**: prefer the existing stack and conventions. For new GitHub Pages sites, use `references/github-pages-bootstrap.md`, `references/implementation.md`, and `references/site-structure.md`. Do not default to a large single-file HTML implementation unless the user explicitly asks for a disposable prototype.
9. **Review**: run build/tests where possible and use `web-design-guidelines` or an equivalent review skill when available. Use `references/quality-checklist.md`.
10. **Publish**: commit and push only when the user asks for publishing. Do not stage unrelated changes silently.

## Companion Skill Routing

Use `references/skill-routing.md` as the source of truth for companion skill routing.

Required routing behavior when available:

- Taste and design direction: `design-taste-frontend`, `taste-skill`, `taste`, or equivalent.
- Theme system: `theme-factory` or equivalent.
- Frontend/UI implementation: `frontend-design` or equivalent.
- Complex React/Tailwind/shadcn artifact: `web-artifacts-builder`.
- Raster hero images, portrait treatments, textures, or visual assets: `imagegen`.
- Final UI/UX/accessibility review: `web-design-guidelines` or equivalent.

If a relevant companion skill is unavailable, say so briefly and continue with the matching bundled reference file or general capability. Do not install companion skills automatically.

## Output Gates

Use `references/output-contracts.md` before moving between major phases.

Minimum gates:

- No style direction before identity reflection.
- No implementation before user-confirmed homepage brief.
- No UI customization before taste discovery or explicit fallback.
- No final delivery before UI/UX/responsive/accessibility review or explicit fallback.
- No publishing before user approval and clean git scope.

## Brief Contract

Use `references/homepage-brief.md` for the canonical brief schema.

Every brief must include:

- identity
- audience
- first impression
- remembered-for statement
- source materials
- personal signal pack when provided
- confirmed facts
- inferred positioning
- open questions
- content modules
- social/contact strategy
- media strategy
- style direction
- explicit avoids
- privacy boundaries
- emoji policy
- companion skill routing
- implementation and validation plan
- structured site file plan for real implementations

## Reference Map

- `references/session-protocol.md`: conversation state, phase transitions, and restart rules.
- `references/output-contracts.md`: required outputs and gates before design, implementation, review, and publish.
- `references/skill-routing.md`: companion skill routing, required calls when available, and fallback behavior.
- `references/homepage-brief.md`: canonical `personal_homepage_brief` schema and examples.
- `references/personal-signal-intake.md`: lightweight intake prompts for users with little or no prepared material.
- `references/site-structure.md`: default structured static site layout for HTML/CSS/JS GitHub Pages implementations.
- `references/anti-patterns.md`: common failure modes to avoid during discovery, design, implementation, and delivery.
- `references/forward-tests.md`: realistic test prompts and expected behavior for future validation.
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

## Beta Iteration

This is a beta skill. When a real run exposes confusion, skipped gates, weak questions, generic design, wrong companion skill routing, or publishing risk, update the relevant reference file instead of only patching one prompt response.
