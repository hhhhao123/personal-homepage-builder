# Iteration Requests

Use this file when a user already has a built or in-progress personal homepage and asks for a new requirement, such as adding dynamic elements, changing a section, improving interaction, adding media, revising layout, or asking whether an idea would be good.

## Principle

Treat iteration requests as design decisions on top of an existing page, not as a reason to restart the full homepage workflow.

When the user has no clear idea, do not ask them to invent the solution. Inspect the current page, infer what would fit, and offer a small set of grounded options.

For beginner users, keep the recommendation visual and concrete. Do not describe the request as a schema or gate. Explain what the visitor will notice and what tradeoff it creates.

## Intake

Before recommending or implementing, inspect available context:

- current page structure and key sections
- existing visual direction, density, and motion level
- confirmed homepage brief or prior user intent
- target audience and primary memory point
- current asset structure and implementation stack
- responsive/accessibility constraints
- whether the request changes public content, private information, or only presentation

If the page files are available, read them before proposing UI changes. If the page is not available, ask for a link, screenshot, repository, or short description.

## Response Pattern

For exploratory requests such as "Should we add dynamic elements?", "Can this page be more interesting?", or "What could we add here?", answer with:

```text
Based on the current homepage, I would consider these options:

1. <option name>
   Best location:
   Why it fits:
   Effect:
   Complexity:
   Risk:

Recommended choice:
```

Keep options concrete and limited to 2-4. Prefer one clear recommendation instead of an unranked menu.

## Recommendation Rules

- Tie every suggestion to the current page's content, layout, identity, and audience.
- Prefer small improvements that strengthen the existing direction over unrelated visual tricks.
- State when the current page should not add the requested effect.
- For motion requests, use `motion-design.md` and choose `none`, `subtle`, `moderate`, or `expressive`.
- If the user asks for an effect that conflicts with the page goal, propose a safer alternative.
- If implementation is requested, update only the affected files and preserve the existing structure.
- If the change affects identity, audience, privacy, core content priority, visual direction, or motion level, use the Change Control Gate in `output-contracts.md` before editing.

## Common Iteration Types

### Motion or Dynamic Elements

Recommend based on the current page:

- hero entrance only, when the page feels static but should remain restrained
- section reveal, when content is long and scroll-based pacing helps
- project card hover/focus states, when work samples need stronger affordance
- timeline reveal, when experience or research progression is central
- media hover preview, when the page is image/video-heavy
- active navigation state, when the page has several sections

Avoid:

- adding motion to every block
- heavy particle backgrounds without a personal rationale
- scroll hijacking
- cursor effects on formal or dense pages
- decorative motion when `motion_strategy.level` is `none`

### Section Additions

Before adding a section, ask what visitor task it serves. Suggested sections should strengthen one of:

- credibility
- selected work
- personal memory point
- contact/conversion
- media/storytelling

### Visual Refresh

For partial redesigns, preserve recognizable content and URLs unless the user asks for a broader redesign. Recommend focused changes to typography, spacing, hierarchy, image treatment, palette, or component states.

## Mini Gate

Before editing code for an iteration request, produce a compact change plan:

- current issue or opportunity
- recommended change
- target files
- motion level if relevant
- validation needed
- risks or tradeoffs

Ask for confirmation unless the user explicitly requested direct implementation and the change is low risk.

If a previous requirements summary or homepage brief was confirmed, add:

- whether this change updates the confirmed plan
- which part of the plan changes
- whether the user needs to reconfirm that part
