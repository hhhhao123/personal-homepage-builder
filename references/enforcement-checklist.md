# Enforcement Checklist

Use this file as the hard-stop checklist for real runs. It exists to prevent the skill from sounding rigorous while still behaving like a one-shot page generator.

## Failure Mode Enforcement Matrix

| Failure mode | Required enforcement | Evidence to show or record |
| --- | --- | --- |
| Vague prompt becomes immediate code | Gate 0 coverage and a confirmed brief are required before implementation. | Coverage status plus accepted brief version. |
| Agent says requirements are ready with missing essentials | Mark each core requirement as known, missing, or explicitly deferred. | Coverage table in the requirements summary or brief. |
| User is forced through technical bureaucracy | Keep gate names and schema fields internal for beginners. | Plain-language summary and 1-3 questions at a time. |
| Companion skills are mentioned but not actually used | Applicable installed companion skills must be invoked before their matching output. | Routing statement with invoked, unavailable fallback, or not applicable. |
| First implementation drifts into a generic template | Run brief-to-site checks before final delivery. | Audit showing identity, audience, memory point, page model, and personal content are represented. |
| Repository edits start without project inspection | Inspect the current stack, file structure, assets, data, and deployment target before editing. | Project inspection snapshot in the implementation plan. |
| Site becomes hard to maintain | Separate repeatable content into data/config when reasonable and keep CSS/JS/assets structured. | Content/data strategy and target file map. |
| Fake placeholders ship as real content | Every placeholder must be labeled, approved, or removed before final delivery. | Placeholder policy and final placeholder audit. |
| GitHub Pages assumptions break the site | Confirm static/Jekyll compatibility, relative paths, build command, and publish target. | GitHub Pages readiness notes and validation command. |
| Post-brief changes mutate the site silently | Classify changes as no brief update, brief patch, or new brief version before editing. | Change control or iteration mini gate confirmation. |
| Confirmed brief becomes unscoped implementation | Translate the brief into a file plan before editing. | Brief-to-file mapping, create/modify/delete/no-touch lists, and user approval. |
| Publishing happens as part of implementation | Separate build/preview from commit, push, and deploy. | Publish approval status and staged-file scope. |

## Implementation Authorization Snapshot

Before creating or editing homepage/site files for a visible change, produce a compact snapshot. For beginner users, keep the wording plain; do not call it a gate unless they ask for process detail.

```text
Before I edit files, here is what I will build/change:
- Confirmed baseline:
- Brief version:
- Requirement coverage:
- Current project inspection:
- Page model and target paths:
- Brief-to-file mapping:
- Companion skills used or fallbacks:
- Files to create/modify/delete:
- Files I will not touch:
- Content/data strategy:
- Asset and placeholder policy:
- Motion and reduced-motion plan:
- GitHub Pages/deployment assumptions:
- Validation I will run:
- Publish boundary:
- What visitors will notice:

Please confirm this plan before I edit the files.
```

Implementation is not allowed if any of these are missing:

- accepted requirements summary or accepted brief for a new build
- confirmed iteration/change plan for an existing site adjustment
- project inspection snapshot
- companion skill routing evidence or fallback
- target files and asset/data plan
- files not to touch
- brief-to-file mapping
- placeholder policy
- validation plan
- explicit user confirmation

## Project Inspection Snapshot

Before implementation, inspect enough of the repository or existing site to avoid destructive or incompatible edits.

Include:

- detected stack or static-site type
- existing pages and routes
- existing asset folders
- existing data/config files
- GitHub Pages or deployment clues
- relevant user changes that must be preserved
- files that should not be touched

If no repository or page files are available, ask for the missing files, URL, screenshot, or permission to create a new project structure.

## Placeholder Policy

Allowed placeholders:

- clearly marked content the user approved for a draft
- temporary local image blocks or sample data used only for preview
- typography-first fallbacks when the user has no public media yet

Not allowed in a final deliverable:

- fake names, fake projects, fake testimonials, fake metrics, fake social links, or invented awards
- unmarked lorem ipsum or generic portfolio copy
- references to missing images, scripts, pages, or downloads
- private or unconfirmed information

When placeholders remain by user choice, state exactly where they are and how to replace them later.

## Brief-To-Site Audit

Before final delivery, compare the built site or proposed final change against the current effective brief.

Check:

- the first viewport identifies the person, not a generic template
- primary audience and visitor action are visible
- at least the confirmed core modules are present
- page model and navigation match the confirmed page map
- personal signals are represented without stereotyping
- visual direction, explicit avoids, and motion level are respected
- social/contact strategy matches public/private boundaries
- repeatable content is maintainable where reasonable
- CSS, JavaScript, media, and optional data are separated according to the approved plan, or the exception is documented
- placeholders, fake content, and unused pages are absent or explicitly approved
- GitHub Pages constraints and validation steps are satisfied

If the site fails this audit, fix the mismatch or reopen the affected requirement with the user before final delivery.
