# Output Contracts And Gates

Use this file to decide whether the agent may move to the next phase.

## Gate 1: Identity Reflection

Required before style directions or UI work.

Must include:

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
- style avoids
- anti-template constraints

## Gate 3: Homepage Brief

Required before implementation.

Must use `references/homepage-brief.md`.

The user must accept or correct the brief before code changes begin, unless the user explicitly requests a compressed quick path. Even in a compressed path, produce a minimal brief first.

## Gate 4: Design Routing

Required before implementation.

Must include:

- taste route
- theme route
- frontend route
- media route
- review route
- fallback notes

## Gate 5: Implementation Plan

Required before editing a project.

Must include:

- target files or modules
- stack and deployment target
- asset strategy
- content data strategy
- validation commands
- git scope

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
