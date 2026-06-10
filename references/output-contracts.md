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
- material readiness: provided, missing, placeholders, and what the user should prepare next
- audience
- first impression
- remembered-for statement
- privacy concerns
- open questions

Do not present it as final truth. Ask the user to correct it.

## Optional Gate: Probe Sketch

Allowed after at least one useful identity, audience, content, or taste signal exists. Use when the user cannot describe what they want or needs something concrete to react to.

May include:

- 2-3 direction cards
- a rough text wireframe
- a plain version vs richer version contrast
- a content gap map

Must not include:

- final UI code
- claims that the direction is final
- unexplained internal field names
- companion skill routing details unless the user is technical

Probe sketches help discovery; they do not replace Gate 0, Gate 2, or Gate 3.

## Gate 2: Taste Discovery

Required before UI customization.

Must include:

- companion taste skill used, or fallback stated
- design read in one sentence
- layout variance
- visual density
- motion intensity
- motion level: none, subtle, moderate, or expressive
- style avoids
- anti-template constraints

## Gate 3: Homepage Brief

Required before implementation.

Must use `references/homepage-brief.md`.

Must include `delivery_mode` and `quality_tier`.

Must include a motion strategy, even when the decision is `level: none`.

For zero-prep users, must include a materials status summary: provided materials, missing materials, placeholders, and materials to prepare next.

Must include:

- Gate 0 status
- brief version, status, and whether this is the current effective baseline
- functional requirements
- information architecture: page model, page map, and navigation plan when more than one page is needed
- content model for repeated items such as projects, links, posts, publications, or media
- non-functional requirements: responsive behavior, accessibility, SEO basics, performance, maintainability, reduced motion
- constraints and assumptions: hosting, language, external resources, placeholders, user-provided assets

The user must accept or correct the requirements summary and brief before code changes begin. Even in a compressed path, produce and confirm a minimal brief first.

After acceptance, treat the brief and requirements summary as the current build baseline. Use `brief-lifecycle.md` for all later changes.

## Gate 4: Design Routing

Required before implementation.

Must include:

- taste route
- theme route
- frontend route
- media route
- review route
- motion plan and reduced-motion fallback
- fallback notes

## Gate 5: Implementation Plan

Required before editing a project.

Must include:

- target files or modules
- stack and deployment target
- site structure, including whether the project is single-page, hybrid, or multi-page
- page map, paths, shared navigation, and which content belongs on each page
- whether CSS, JS, images, and data will be separated under `assets/`
- asset strategy
- content data strategy
- validation commands
- git scope
- explicit user confirmation before file edits

## Iteration Mini Gate

Required before editing an existing or in-progress homepage/site for any visible user-facing adjustment.

Must include:

- current issue or opportunity
- recommended change
- why it fits the current homepage
- brief impact: no brief update, brief patch, or new brief version
- brief fields affected, if any
- target files or modules
- visible user-facing impact
- companion skill routing if design/UI work is involved
- motion level and reduced-motion fallback if relevant
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
- brief lifecycle decision: brief patch or new brief version
- new brief version number if a new version is required
- affected sections or files
- impact on content, design, motion, privacy, or implementation
- updated confirmation question
- confirmation status

Do not silently merge a major change into an old brief. Reconfirm the affected part before editing.

## Gate 6: Review Report

Required before final delivery.

Must include:

- build/test result, or why it was not run
- UI/UX review result
- responsive behavior check
- accessibility/text-fit check
- known risks

## Gate 7: Publish Approval

Required before commit, push, or deployment.

Must include:

- user approval to publish
- target repository and branch
- staged file scope
- whether push is normal or force push

Never force push unless the user explicitly asks to overwrite remote content.
