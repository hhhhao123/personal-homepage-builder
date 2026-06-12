# Requirements Template

Use this file after discovery has collected enough information to form a requirements baseline. The requirements document is a user-readable artifact. It should be understandable to a non-developer and useful to another developer or agent.

Do not write a file unless the user is working in a repository or asks for one. In a planning-only conversation, output the same structure in chat.

## When To Produce

Produce a requirements summary before implementation when any of these are true:

- The user asks to build, redesign, publish, or materially change a homepage.
- The user started from zero and has now passed the minimum viable requirements gate.
- The user approved a direction card or text wireframe and is ready for a buildable plan.
- A confirmed brief exists but the user introduces a change that affects identity, audience, content, privacy, or design direction.

## User-Facing Confirmation Prompt

```text
Here is the plan I would build from. Please check whether it represents you correctly. If anything feels wrong, tell me which part to change before I start implementation.
```

## Compact Requirements Summary

Use this before the full requirements document or brief when the user is a beginner, wants a quick result, or has provided scattered material. It is the bridge between discovery and `personal_homepage_brief`.

Keep it short and user-readable:

```markdown
## Homepage Plan To Confirm

### What I Understand

- Public identity:
- Primary visitors:
- What visitors should remember:
- Main action visitors should take:
- Must-show content:

### What I Am Inferring

- Positioning:
- Visual direction:
- Page shape:
- Motion:

### Boundaries

- Do not publish:
- Needs confirmation before public use:
- Placeholder-ready:

### Materials Roadmap

- Provided:
- Missing but useful later:
- Safe placeholder plan:

### Proposed Structure

- Page model:
- Homepage sections:
- Supporting pages, if any:

Please confirm what feels right, what feels wrong, and anything private or exaggerated before I turn this into the build brief.
```

Rules:

- Keep confirmed facts separate from inference.
- List missing materials without blocking progress when placeholders are safe.
- Do not include raw private details; describe their category instead.
- Do not use the compact summary as implementation approval.
- After the user confirms or corrects it, create the `personal_homepage_brief`.

## Requirements Document

```markdown
# Personal Homepage Requirements

## 1. Project Overview

- Current brief version:
- Brief status:
- Public name:
- Homepage type:
- Page model: one page / homepage plus detail pages / multi-page site
- Main purpose:
- Primary visitors:
- Desired first impression:
- What visitors should remember:
- Desired next action:

## 2. Confirmed User Signals

- Confirmed facts:
- Inferred positioning:
- Taste clues:
- Strong dislikes:
- Privacy boundaries:
- Open questions:

## 3. Inspiration And References

- References provided:
- What the user likes:
- What the user dislikes:
- Transferable ideas:
- Ideas that should not be copied:
- Asset or license cautions:
- Confirmation status:

## 4. Minimum Viable Requirements

- Primary audience:
- Main purpose:
- Core content modules:
- Style direction or explicit avoids:
- Public/private boundaries:
- Contact or next action:
- Material status:

### Coverage Status

| Item | Status | Notes |
| --- | --- | --- |
| Audience | known / missing / explicitly deferred | |
| Purpose | known / missing / explicitly deferred | |
| Core modules | known / missing / explicitly deferred | |
| Page model | known / missing / explicitly deferred | |
| Style or avoids | known / missing / explicitly deferred | |
| Privacy boundary | known / missing / explicitly deferred | |
| Contact or next action | known / missing / explicitly deferred | |
| Materials | known / missing / explicitly deferred | |

## 5. Page Structure

### Page Map

| Page | Path | Purpose | Priority | Main content | Missing material |
| --- | --- | --- | --- | --- | --- |
| Home | `/` or `index.html` | | Must | | |
| Supporting page | | | Nice | | |

### Homepage Sections

| Section | Priority | Purpose | Required content | Missing material |
| --- | --- | --- | --- | --- |
| Hero / first screen | Must | | | |
| About | Must | | | |
| Selected work | Must | | | |
| Contact / links | Must | | | |
| Optional section | Nice | | | |

## 6. Functional Requirements

### Must Have

- TBD

### Nice To Have

- TBD

## 7. Content Model

### Project / Work Item

- Title:
- Short description:
- Role or contribution:
- Link:
- Image or screenshot:
- Tags:
- Status:

### Link / Social Item

- Label:
- URL:
- Public priority:
- Display style:

### Media Asset

- Type:
- Source:
- Usage:
- Fallback:

## 8. Non-Functional Requirements

- Responsive behavior:
- Accessibility:
- SEO basics:
- Loading performance:
- Maintainability:
- Reduced-motion behavior:

## 9. Visual And Interaction Direction

- Style keywords:
- Layout direction:
- Color notes:
- Typography notes:
- Image strategy:
- Motion level:
- Motion should support:
- Motion should avoid:

## 10. Constraints And Assumptions

- Hosting:
- Repository or deployment target:
- Language:
- External resources:
- Available materials:
- Placeholders allowed:
- Assumptions to confirm:

## 11. Companion Skill Routing

- Taste/design direction:
- Theme:
- Frontend implementation:
- Image/media:
- Review:

## 12. Implementation Plan

- Project inspection:
- Site structure:
- Page model and page map:
- Target files:
- Asset organization:
- Content/data strategy:
- Placeholder policy:
- GitHub Pages assumptions:
- Companion skill routing:
- Starter template decision:
- Validation:
- Publishing:
- Confirmation before editing:

## 13. Final Review Baseline

Before final delivery, the built site should be checked against this requirements document and the current brief:

- identity, audience, purpose, and memory point are visible
- confirmed sections and page map are present
- visual direction, explicit avoids, and motion level are respected
- public/private boundaries are honored
- placeholders and fake content are removed or explicitly approved
- GitHub Pages paths and publishing assumptions work

## 14. Change Baseline

This requirements document and the confirmed brief are the current build baseline. If identity, audience, content priority, page model, privacy, or visual direction changes, update the affected section and reconfirm before implementation continues.

## 15. Adjustment Approval Rule

For later page adjustments, do not edit files from a broad request alone. First summarize:

- what will change
- where it will change
- what visitors will notice
- which files are likely affected
- how it will be validated

Then wait for explicit user confirmation.

## 16. Brief Lifecycle Rule

- Small visual or technical adjustments may keep the current brief unchanged.
- Changes to confirmed sections, page map, motion level, content items, links, or media should patch the current brief.
- Changes to audience, purpose, identity positioning, major page structure, privacy boundary, or visual direction require a new brief version.
- Only one brief version is current at a time.
```

## Change Confirmation Template

Use this when the user changes requirements after a baseline has been confirmed.

```text
This changes the confirmed plan in one area:

- Previous:
- New:
- Impact:
- Files or sections affected:
- Brief impact:
- Brief fields affected:

Please confirm this change before I update the build plan.
```

## Minimum Viable Requirements Check

The requirements baseline is not ready until these are known or explicitly deferred:

- primary audience
- main purpose
- at least three core content modules
- page model: one page, hybrid, or multi-page
- style tendency or explicit visual dislikes
- public/private boundaries
- contact or visitor next action
- available materials and missing placeholders

If one item is missing, ask only for that item or offer choices.
