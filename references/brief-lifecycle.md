# Brief Lifecycle

Use this file whenever a confirmed homepage brief already exists and the user asks for a change, redesign, new page, motion adjustment, content update, or implementation change.

## Core Rule

Maintain one current effective brief for the homepage or personal site.

The brief is the active design and requirement baseline. A change plan is the local plan for one adjustment. Do not let the site drift away from the active brief.

## Outputs

- **Brief**: current whole-site baseline.
- **Change plan**: one proposed adjustment before code edits.
- **Brief patch**: a small update to the current brief after a confirmed change.
- **New brief version**: a replacement baseline when the change meaningfully changes the site.

## Classification

### No Brief Update Required

Use this when the change does not alter the site's intent or structure.

Examples:

- fixing spacing, focus states, responsive text fit, or accessibility issues
- improving hover feedback while keeping the same motion level
- replacing placeholder URLs with real URLs
- correcting typos or factual wording without changing positioning
- small CSS cleanup that preserves the confirmed design direction

Still produce and confirm a change plan before editing visible UI.

### Brief Patch Required

Use this when the change updates a confirmed part of the plan but does not change the overall direction.

Examples:

- adding or removing one optional section
- changing the motion level within the same design direction
- adding a project, writing item, publication, social link, media asset, or contact route
- changing the page map in a small way, such as adding `projects.html`
- updating content priority while keeping the same audience and purpose
- refining style keywords without changing the visual direction

After confirmation, update the relevant brief fields and record the change.

### New Brief Version Required

Use this when the old brief would become misleading.

Examples:

- primary audience changes
- main purpose changes
- identity positioning changes
- site changes from resume/profile to creator brand, academic profile, service page, or product-like portfolio
- single-page site becomes a content-rich multi-page site
- information architecture changes substantially
- privacy boundary changes materially
- language strategy changes, such as English-only to bilingual launch
- visual direction changes substantially
- hosting, stack, or implementation target changes in a way that affects design or maintenance

Create a new brief version, such as `brief v2`, and ask the user to confirm it before implementation.

## Required Workflow

1. Reconstruct the current effective brief from conversation, files, or existing docs.
2. Classify the user request: no brief update, brief patch, or new brief version.
3. Produce a change plan that includes the lifecycle decision.
4. Ask for explicit confirmation before editing files.
5. If confirmed, update the brief when the classification requires it.
6. Implement only after the relevant brief or change plan is confirmed.

## Change Plan Addendum

Every change plan after a confirmed brief must include:

```text
Brief impact:
- Current brief:
- Classification: no brief update / brief patch / new brief version
- Brief fields affected:
- Does this need reconfirmation before code:
```

## Versioning

Use simple human-readable versions:

- `v1`: first confirmed brief
- `v1.1`, `v1.2`: patches that preserve the same direction
- `v2`: a meaningful direction change

Do not create multiple active briefs. Keep one current effective brief and mark older versions as superseded when a new version is confirmed.

## User-Facing Language

For beginner users, avoid saying "brief lifecycle" unless they ask. Say:

```text
This change affects the plan we confirmed earlier, so I will update that plan before changing code.
```

or:

```text
This is a small visual adjustment, so the original plan can stay the same. I will still confirm the exact change before editing.
```
