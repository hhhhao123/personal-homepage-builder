# Output Contracts And Gates

Use this file to decide whether the agent may move to the next phase.

## Gate 1: Identity Reflection

Required before style directions or UI work.

Must include:

- inferred or selected delivery mode
- inferred or selected quality tier
- confirmed facts
- inferred positioning
- tentative taste signals
- audience
- first impression
- remembered-for statement
- privacy concerns
- open questions

Do not present it as final truth. Ask the user to correct it.

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

The user must accept or correct the brief before code changes begin, unless the user explicitly requests a compressed quick path. Even in a compressed path, produce a minimal brief first.

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
- site structure, including whether CSS, JS, images, and data will be separated under `assets/`
- asset strategy
- content data strategy
- validation commands
- git scope

## Iteration Mini Gate

Required before editing an existing or in-progress homepage for a new requirement.

Must include:

- current issue or opportunity
- recommended change
- why it fits the current homepage
- target files or modules
- companion skill routing if design/UI work is involved
- motion level and reduced-motion fallback if relevant
- validation needed
- risks or tradeoffs

If the user is asking for suggestions rather than implementation, provide options first and do not edit until a direction is chosen.

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
