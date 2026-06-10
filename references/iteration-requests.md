# Iteration Requests

Use this file when a user already has a built or in-progress personal homepage or small personal site and asks for a new requirement, such as adding dynamic elements, changing a section, improving interaction, adding media, revising layout, changing navigation, adding pages, or asking whether an idea would be good.

## Principle

Treat iteration requests as design decisions on top of an existing page, not as a reason to restart the full homepage workflow.

When the user has no clear idea, do not ask them to invent the solution. Inspect the current page, infer what would fit, and offer a small set of grounded options.

For beginner users, keep the recommendation visual and concrete. Do not describe the request as a schema or gate. Explain what the visitor will notice and what tradeoff it creates.

Any visible page/site adjustment requires explicit confirmation before code edits. This applies even when the user says "make it better", "add some motion", "adjust the page", "improve the UI", "change the style", or "you decide". Treat the user's request as permission to analyze and propose, not permission to edit.

After a brief has been confirmed, every iteration request must also classify its brief impact using `brief-lifecycle.md`: no brief update, brief patch, or new brief version.

## Intake

Before recommending or requesting confirmation, inspect available context:

- current page structure and key sections
- existing visual direction, density, and motion level
- confirmed homepage brief or prior user intent
- current effective brief version and whether the request affects it
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

Please confirm which option to apply before I edit the files.
```

Keep options concrete and limited to 2-4. Prefer one clear recommendation instead of an unranked menu.

## Recommendation Rules

- Tie every suggestion to the current page's content, layout, identity, and audience.
- Prefer small improvements that strengthen the existing direction over unrelated visual tricks.
- State when the current page should not add the requested effect.
- For motion requests, use `motion-design.md` and choose `none`, `subtle`, `moderate`, or `expressive`.
- If the user asks for an effect that conflicts with the page goal, propose a safer alternative.
- If implementation is requested, still produce the compact change plan and wait for explicit confirmation before editing. After confirmation, update only the affected files and preserve the existing structure.
- If the change affects identity, audience, privacy, core content priority, visual direction, or motion level, use the Change Control Gate in `output-contracts.md` before editing.
- If the change requires a brief patch or new brief version, update or regenerate the brief before implementation.

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

Before editing code for any iteration request, produce a compact change plan:

- current issue or opportunity
- recommended change
- target files
- visible user-facing impact
- brief impact: no brief update, brief patch, or new brief version
- brief fields affected
- motion level if relevant
- validation needed
- risks or tradeoffs
- exact confirmation question

Do not edit until the user explicitly confirms the plan. A vague positive reaction such as "looks good" is acceptable only if it clearly refers to the proposed change plan. If confirmation is ambiguous, ask once more before editing.

If a previous requirements summary or homepage brief was confirmed, add:

- whether this change updates the confirmed plan
- which part of the plan changes
- whether the user needs to reconfirm that part
- whether the current brief remains valid, needs a patch, or must become a new version

## Direct-Edit Requests

If the user asks to directly edit an existing page without discussion, respond with the smallest useful confirmation step:

```text
I can make that change, but before editing I need to confirm the exact adjustment:

- Change:
- Where it applies:
- Visitor-facing effect:
- Files likely affected:
- Brief impact:
- Risk:

Please confirm this plan, then I will edit the files.
```

Do not use direct-edit wording as approval to skip the confirmation step.
