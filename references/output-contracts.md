# Output Contracts And Gates

Use this file to decide whether the agent may move to the next phase.

These gates are internal controls. For beginner users, do not present them as process bureaucracy or ask them to fill every field directly. Use plain-language summaries and choices.

## Gate 0: Minimum Viable Requirements

Required before implementation, formal homepage/site brief, or final design direction.

Must include:

- primary audience: who should open the homepage first
- main purpose: what the homepage should help the visitor understand or do
- core content modules: at least three sections or content types
- page model: whether the content fits one page, a homepage plus supporting pages, or a multi-page site
- style tendency or explicit visual dislikes
- privacy boundary: what must not be public
- contact or next action
- material status: provided, missing, placeholder-ready, and what to prepare next

Must also include a coverage status for each required item:

```text
Requirement coverage:
- Audience: known / missing / explicitly deferred
- Purpose: known / missing / explicitly deferred
- Core modules: known / missing / explicitly deferred
- Page model: known / missing / explicitly deferred
- Style or avoids: known / missing / explicitly deferred
- Privacy boundary: known / missing / explicitly deferred
- Contact or next action: known / missing / explicitly deferred
- Materials: known / missing / explicitly deferred
```

Do not mark the gate ready if audience, purpose, core modules, privacy boundary, or next action are missing. Lower-risk details may be explicitly deferred only if the user understands the tradeoff and the brief records the assumption.

If a field is missing, ask only for the missing high-impact item or offer 2-4 choices. A compressed quick path may defer lower-risk details, but it may not skip audience, purpose, core modules, privacy, or next action.

Do not show the term "minimum viable requirements" to ordinary users unless they ask for process details.

## Gate 1: Identity Reflection

Required before style directions or UI work.

Must include:

- inferred or selected delivery mode
- inferred or selected quality tier
- confirmed facts
- inferred positioning
- tentative taste signals
- assumptions that need user correction
- material readiness: provided, missing, placeholders, and what the user should prepare next
- audience
- first impression
- remembered-for statement
- privacy concerns
- private or sensitive material that is quarantined and will not be published by default
- open questions

Do not present it as final truth. Ask the user to correct it.

## Optional Gate: Probe Sketch

Allowed after at least one useful identity, audience, content, or taste signal exists. Use when the user cannot describe what they want or needs something concrete to react to.

May include:

- 2-3 direction cards
- a rough text wireframe
- a plain version vs richer version contrast
- a content gap map
- an inspiration read when the user provides references, screenshots, or effect links

Must not include:

- final UI code
- claims that the direction is final
- unexplained internal field names
- companion skill routing details unless the user is technical

Probe sketches help discovery; they do not replace Gate 0, Gate 2, or Gate 3.

## Gate 2: Taste Discovery

Required before UI customization.

Must include:

- companion taste skill actually invoked, or unavailable fallback stated
- inspiration read from `references/inspiration-intake.md` when visual references, screenshots, dynamic effect links, or inspiration sites were supplied
- design read in one sentence
- layout variance
- visual density
- motion intensity
- motion level: none, subtle, moderate, or expressive
- style avoids
- anti-template constraints

## Gate 3: Homepage Brief

Required before implementation.

Required after a user-readable requirements summary has been produced and accepted or corrected.

Must use `references/homepage-brief.md`.

Must include `delivery_mode` and `quality_tier`.

Must include a motion strategy, even when the decision is `level: none`.

For zero-prep users, must include a materials status summary: provided materials, missing materials, placeholders, and materials to prepare next.

Must include:

- Gate 0 status
- requirement coverage status: known, missing, or explicitly deferred for each Gate 0 item
- requirements summary status: draft, accepted, corrected, or needs revision
- brief version, status, and whether this is the current effective baseline
- inspiration interpretation, accepted ideas, rejected ideas, and copy/license cautions when references were provided
- functional requirements
- information architecture: page model, page map, and navigation plan when more than one page is needed
- content model for repeated items such as projects, links, posts, publications, or media
- placeholder policy: allowed draft placeholders, items that must be removed before final delivery, and approved placeholders if any remain
- non-functional requirements: responsive behavior, accessibility, SEO basics, performance, maintainability, reduced motion
- constraints and assumptions: hosting, language, external resources, placeholders, user-provided assets

The user must accept or correct the requirements summary and brief before code changes begin. Even in a compressed path, produce and confirm a minimal brief first.

After acceptance, treat the brief and requirements summary as the current build baseline. Use `brief-lifecycle.md` for all later changes.

## Gate 4: Design Routing

Required before implementation.

Must include:

- taste route: invoked skill, unavailable fallback, or not applicable with reason
- theme route: invoked skill, unavailable fallback, or not applicable with reason
- frontend route: invoked skill, unavailable fallback, or not applicable with reason
- media route: invoked skill, unavailable fallback, or not applicable with reason
- artifact route: `web-artifacts-builder` invoked, unavailable fallback, or not applicable with reason
- review route: planned invoked skill, unavailable fallback, or not applicable with reason
- motion plan and reduced-motion fallback
- fallback notes

If a relevant companion skill is available and the stage applies, the gate does not pass until that skill has been invoked. Do not accept "will use later" as equivalent to invocation, except for the review route, which may be planned here and must be invoked before Gate 6.

## Gate 5: Implementation Plan

Required before editing a project.

Must include:

- source baseline: accepted requirements summary, current effective brief version, and change plan or brief patch if applicable
- project inspection snapshot: current stack, pages/routes, assets, data/config files, GitHub Pages or deployment clues, existing user changes to preserve, and files that should not be touched
- target files or modules
- file plan: files to create, modify, delete, and explicitly not touch
- stack and deployment target
- site structure, including whether the project is single-page, hybrid, or multi-page
- page map, paths, shared navigation, and which content belongs on each page
- brief-to-file mapping: how confirmed modules, content, style, motion, privacy, and placeholders map into pages, data, and assets
- whether CSS, JS, images, and data will be separated under `assets/`
- asset strategy
- starter template decision: whether `assets/static-site-template/` will be copied/adapted, skipped because an existing stack exists, or skipped for a specific reason
- content data strategy
- placeholder policy: which placeholders are allowed, which must be removed, and which user materials are still missing
- GitHub Pages readiness: static/Jekyll compatibility, relative paths, external dependency assumptions, build or preview command, and publish target if known
- companion skill routing evidence from Gate 4, not only a future promise
- validation commands
- git scope
- explicit user confirmation before file edits

The plan must include the implementation authorization snapshot from `references/enforcement-checklist.md`. Do not edit files if the confirmed brief or confirmed iteration plan, project inspection, companion routing/fallback, target files, placeholder policy, validation plan, or explicit user confirmation is missing.

Brief approval alone is not file-edit approval. If the user has accepted the brief but has not approved the scoped implementation plan, ask for confirmation before editing.

## Iteration Mini Gate

Required before editing an existing or in-progress homepage/site for any visible user-facing adjustment.

Must include:

- issue or opportunity
- visual iteration diagnosis when the user is unhappy with the current style, elements, motion, or first-version result
- what should be preserved from the current version
- recommended change
- why it fits the active brief
- brief impact classification: no brief update needed, implementation-only fix, brief patch, new brief version, or publish-only action
- brief fields affected, if any
- target files or modules
- visible user-facing impact
- companion skill routing or fallback
- motion and reduced-motion impact if relevant
- validation needed
- risks or tradeoffs
- exact confirmation question
- confirmation status

If the user is asking for suggestions rather than implementation, provide options first and do not edit until a direction is chosen and confirmed.

If the user asks to directly edit, still produce the mini gate and wait for explicit confirmation before editing.

Never treat "make it better", "you decide", "adjust it", or "add something" as approval to edit files.

## Change Control Gate

Required when the user changes identity, audience, content priority, privacy boundary, visual direction, motion level, or implementation target after a requirements summary or brief was confirmed.

Must include:

- previous understanding
- requested change
- brief lifecycle decision: no brief update needed, implementation-only fix, brief patch, new brief version, or publish-only action
- new brief version number if a new version is required
- affected sections or files
- impact on content, design, motion, privacy, or implementation
- updated confirmation question
- confirmation status

Do not silently merge a major change into an old brief. Reconfirm the affected part before editing.

Implementation-only fixes and publish-only actions should not trigger this gate unless they also affect identity, audience, content priority, privacy boundary, visual direction, page model, motion level, or implementation target.

## Gate 6: Review Report

Required before final delivery.

Must include:

- build/test result, or why it was not run
- UI/UX review result, including `web-design-guidelines` or equivalent actually invoked when available, or fallback stated
- brief-to-site audit against the current effective brief: identity, audience, memory point, core modules, page model, visual direction, motion level, explicit avoids, and contact/privacy strategy
- placeholder and fake-content audit: no unapproved fake names, fake projects, fake metrics, fake testimonials, fake links, broken image references, or unmarked lorem ipsum remain
- maintainability audit: repeatable content is stored in data/config where reasonable, assets are saved in the project, and CSS/JS/images are not unnecessarily embedded into one monolithic file
- implementation-plan audit: created/modified files match the approved file plan, no-touch files were preserved, and any deviation is explained
- GitHub Pages compatibility audit: static paths, page links, supported features, and publish assumptions fit the target repository
- responsive behavior check
- accessibility/text-fit check
- motion/reduced-motion check: the implemented behavior matches the confirmed motion level and keeps core content available without JavaScript
- known risks

## Gate 7: Publish Approval

Required before commit, push, or deployment.

Must include:

- user approval to publish
- target repository and branch
- Pages source or deployment target
- latest build/test/preview result or reason unavailable
- staged file scope
- confirmation that staged files match the approved implementation or publish-only plan
- whether push is normal or force push

Never force push unless the user explicitly asks to overwrite remote content.
