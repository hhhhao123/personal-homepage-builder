# Visual Iteration

Use this file after a first homepage version exists and the user is unhappy with the visual result, page feel, interaction quality, dynamic effects, element style, or overall fit.

This is not a full restart by default. Treat it as a focused design iteration on top of the current page and current effective brief.

## Core Principle

First versions are allowed to be imperfect. Convert the user's reaction into a clearer design adjustment:

```text
current page + user reaction + references if any
-> diagnose what feels wrong
-> preserve what still works
-> route only the necessary companion skills
-> propose a revision plan
-> confirm
-> update brief if needed
-> edit code
-> review
```

Do not ask the user to solve the design problem. If the user says "it looks bad", "not my style", "too plain", "too generic", or "I do not know what exactly is wrong", inspect the page and offer concrete diagnoses.

## Required Inputs

Before proposing a visual iteration, inspect or reconstruct:

- current page files, screenshot, preview, or URL
- current effective brief or last confirmed plan
- what the user dislikes or wants to change
- any reference links, screenshots, mood boards, CodePen effects, or examples
- current stack and asset structure
- current motion level and reduced-motion behavior
- whether the change affects audience, identity, page model, content priority, or only presentation

If no page preview, files, screenshot, or URL is available, ask for one before making visual claims.

## Dissatisfaction Types

Classify the user's reaction into one or more types:

| Reaction | Likely issue | Typical route |
| --- | --- | --- |
| "It does not feel like me" | Identity or taste mismatch | Revisit brief, use taste skill, possibly patch/new brief |
| "Too plain / too generic" | Weak visual direction, hierarchy, or component polish | Taste + frontend UI + maybe theme |
| "Too corporate / too formal" | Tone mismatch | Taste + copy/style adjustment |
| "Too flashy / too much movement" | Motion intensity mismatch | Motion revision, maybe no theme change |
| "Colors / fonts feel wrong" | Theme system mismatch | Theme skill + frontend UI if layout also shifts |
| "The first screen is not attractive" | Hero hierarchy, image, typography, or memory point issue | Taste + frontend UI + imagegen if visual asset needed |
| "The projects do not look good" | Component design, proof, media, or content structure issue | Frontend UI + maybe media/image strategy |
| "It feels static" | Motion/interaction gap | Motion design + frontend UI |
| "It feels crowded / empty" | Density, spacing, content priority issue | Frontend UI + brief patch if content priority changes |
| "I found a reference I like" | Inspiration translation needed | Inspiration intake + relevant design routes |

## Selective Companion Skill Routing

Do not call every companion skill for every iteration. Call every relevant available skill for the actual problem.

| Iteration need | Required when available | Usually not needed |
| --- | --- | --- |
| Overall visual direction feels wrong | `design-taste-frontend` or equivalent | `imagegen` unless assets are part of the issue |
| Colors, type, spacing, theme tokens feel wrong | `theme-factory` or equivalent | `web-artifacts-builder` for simple static sites |
| Layout, section design, cards, hero, navigation, or responsive UI needs polish | `frontend-design` or equivalent | `imagegen` unless visual assets are needed |
| Dynamic elements or interaction need adjustment | `frontend-design`; use `motion-design.md` | `theme-factory` unless visual system changes |
| Need a hero image, texture, portrait treatment, or original visual asset | `imagegen` | `web-artifacts-builder` unless complex artifact |
| Complex React/Tailwind/shadcn interaction or multi-state artifact | `web-artifacts-builder` | Plain static template unless stack changes |
| Final check after visual changes | `web-design-guidelines` or equivalent | None |

Record each route as `invoked`, `unavailable fallback`, or `not applicable`, with a short reason.

## Reaction Intake Prompts

Ask only 1-3 questions. Prefer concrete choices:

```text
Which part feels most wrong?
1. The first screen does not catch attention.
2. The page feels too generic or template-like.
3. The colors or typography do not feel right.
4. The layout feels crowded, empty, or unbalanced.
5. The motion is missing, too weak, or too distracting.
6. The page does not feel like me.
```

If the user has references:

```text
For each reference, tell me one thing you like and one thing we should not copy. I will translate the reference into a safer design direction before editing code.
```

If the user cannot explain:

```text
I will inspect the current page and give you 2-3 possible diagnoses. You can choose the one that feels closest.
```

## Visual Iteration Output

Before editing code, produce:

```text
Visual iteration diagnosis:
- Current issue:
- What should stay:
- What should change:
- Reference interpretation, if any:
- Brief impact:
- Companion skills to invoke:
- Target files:
- Visitor-facing result:
- Risks:
- Validation:

Please confirm this revision plan before I edit the files.
```

## Revision Levels

Use the smallest level that can solve the problem:

1. **Polish pass**: spacing, hierarchy, states, text fit, small motion, accessibility.
2. **Section redesign**: hero, project cards, contact, writing list, media block, navigation.
3. **Style refresh**: color, typography, image treatment, density, visual language.
4. **Motion pass**: hover, reveal, active state, media interactions, reduced-motion cleanup.
5. **Structural revision**: page model, navigation, supporting pages, content priority.
6. **Direction pivot**: significant identity, audience, or visual direction change; usually requires a new brief version.

## Brief Lifecycle

Use `brief-lifecycle.md` for every visual iteration after a brief exists.

- No brief update: small polish that keeps the same direction.
- Brief patch: style keywords, motion level, accepted references, section design, content priority, or page map changes within the same direction.
- New brief version: the user rejects the overall identity, audience, purpose, page model, or visual direction.

Do not implement a style pivot from an old brief.

## Review Loop

After implementation:

- run available build/tests or explain why not
- invoke `web-design-guidelines` or equivalent when available
- summarize what changed visually
- tell the user what to inspect
- ask for the next reaction if this is an iterative design pass

Do not keep editing repeatedly without fresh confirmation.

