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
- **Implementation-only fix**: a scoped technical or bug fix that preserves the active brief and does not change the user's represented identity, content strategy, page model, privacy boundaries, or design direction.
- **Publish-only action**: validation, staging, commit, push, or GitHub Pages publishing work that changes no site requirements or visible page behavior.

## Classification

Classify every post-brief request into exactly one primary category before editing or publishing. If a request contains multiple changes, split it into separate items and classify each item.

### No Brief Update Required

Use this when the change does not alter the site's intent or structure.

Examples:

- fixing spacing, focus states, responsive text fit, or accessibility issues
- improving hover feedback while keeping the same motion level
- polishing visual hierarchy, component spacing, or element states while preserving the confirmed style direction
- replacing placeholder URLs with real URLs
- correcting typos or factual wording without changing positioning
- small CSS cleanup that preserves the confirmed design direction

Still produce and confirm a change plan before editing visible UI.

### Implementation-Only Fix

Use this when the change is primarily technical and preserves the active brief.

Examples:

- fixing a broken asset path, broken anchor link, build error, invalid metadata, malformed CSS, or JavaScript bug
- restoring responsive behavior that was already required by the brief
- fixing an accessibility issue such as missing focus state, missing alt text, or incorrect heading order
- removing unused starter code, unused files, or dead references when the visible result and brief remain unchanged
- adjusting implementation to satisfy GitHub Pages compatibility without changing page content or design direction

If the fix changes visible layout, copy, navigation, content, motion, or media, still produce the iteration mini gate and ask for confirmation. Do not use this category to smuggle in redesign work.

### Brief Patch Required

Use this when the change updates a confirmed part of the plan but does not change the overall direction.

Examples:

- adding or removing one optional section
- changing the motion level within the same design direction
- accepting a new reference idea that refines the existing style without changing the overall direction
- revising colors, typography, image treatment, or component style within the same identity and audience
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
- the user rejects the first version's overall feeling as "not like me" and chooses a different style direction
- hosting, stack, or implementation target changes in a way that affects design or maintenance

Create a new brief version, such as `brief v2`, and ask the user to confirm it before implementation.

### Publish-Only Action

Use this when the user asks to preview, prepare, commit, push, deploy, or publish without changing the site plan or files beyond publishing metadata that was already approved.

Examples:

- preparing GitHub Pages publishing for an already approved implementation
- checking target repository, branch, Pages source, staged files, and build/preview status
- committing and pushing only after the user explicitly approves the publish action
- explaining propagation delay after a successful push

Publish-only actions do not patch or version the brief, but they require publish approval, clean git scope, and validation evidence. Never treat "ready to publish?" as approval to push.

## Decision Examples

| User request | Classification | Required handling |
| --- | --- | --- |
| Replace a placeholder GitHub link with the user's real GitHub URL | No brief update needed, unless it changes contact strategy | Confirm target URL, update only link/data files, validate link. |
| Fix spacing in the contact section or correct a typo | No brief update needed | Produce a small change plan, preserve style direction, validate responsive/text fit. |
| Add subtle card hover and section reveal motion when the brief already allows subtle motion | No brief update needed or brief patch if the exact motion pattern becomes part of the plan | Confirm motion locations, reduced-motion fallback, and target files before editing. |
| Add a writing section to an existing one-page profile | Brief patch | Confirm visitor purpose, content source, location, navigation, placeholders, and affected brief fields. |
| Split projects and writing into separate pages | Brief patch or new brief version depending on scale | Reconfirm page model, page map, navigation, content ownership, and GitHub Pages paths. |
| Change an academic profile into a bold creator portfolio | New brief version | Reconfirm audience, identity positioning, content priority, style direction, motion level, and privacy impact. |
| Remove sensitive personal info from the page | Brief patch if privacy boundary changes, implementation-only fix if removing accidental leakage to match existing privacy rules | Remove from rendered files/data, audit public/private boundaries, validate no remaining references. |
| Switch from no motion to expressive motion | New brief version in most cases | Reconfirm visual direction, audience fit, reduced-motion behavior, performance risk, and companion routing. |
| Prepare GitHub Pages publishing | Publish-only action | Confirm repo/branch/Pages source, run available checks, stage intended files only, and push only with explicit approval. |

## Required Workflow

1. Reconstruct the current effective brief from conversation, files, or existing docs.
2. Classify the user request: no brief update needed, implementation-only fix, brief patch, new brief version, or publish-only action.
3. Produce a change plan that includes the lifecycle decision.
4. Ask for explicit confirmation before editing visible files, changing data, or publishing.
5. If confirmed, update the brief when the classification requires it.
6. Implement only after the relevant brief, brief patch, new brief version, implementation-only plan, or publish plan is confirmed.

## Change Plan Addendum

Every change plan after a confirmed brief must include:

```text
Brief impact:
- Current brief:
- Classification: no brief update needed / implementation-only fix / brief patch / new brief version / publish-only action
- Brief fields affected:
- Does this need a brief patch or new brief version before code:
- Does this need publish approval:
```

## Versioning

Use simple human-readable versions:

- `v1`: first confirmed brief
- `v1.1`, `v1.2`: patches that preserve the same direction
- `v2`: a meaningful direction change

Do not create multiple active briefs. Keep one current effective brief and mark older versions as superseded when a new version is confirmed.

Implementation-only fixes and publish-only actions do not change the brief version. Record them in the change history or final report when useful, but do not inflate `v1.1`, `v1.2`, or `v2` unless the brief itself changes.

## User-Facing Language

For beginner users, avoid saying "brief lifecycle" unless they ask. Say:

```text
This change affects the plan we confirmed earlier, so I will update that plan before changing code.
```

or:

```text
This is a small visual adjustment, so the original plan can stay the same. I will still confirm the exact change before editing.
```

For implementation-only fixes:

```text
This fixes how the site works without changing the plan we agreed on. I will still confirm the files affected before editing.
```

For publish-only actions:

```text
This is only about preparing or publishing the approved site. I will check the target repo, branch, staged files, and validation result before asking you to confirm the push.
```
