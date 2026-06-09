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

## Requirements Document

```markdown
# Personal Homepage Requirements

## 1. Project Overview

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

## 3. Minimum Viable Requirements

- Primary audience:
- Main purpose:
- Core content modules:
- Style direction or explicit avoids:
- Public/private boundaries:
- Contact or next action:
- Material status:

## 4. Page Structure

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

## 5. Functional Requirements

### Must Have

- TBD

### Nice To Have

- TBD

## 6. Content Model

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

## 7. Non-Functional Requirements

- Responsive behavior:
- Accessibility:
- SEO basics:
- Loading performance:
- Maintainability:
- Reduced-motion behavior:

## 8. Visual And Interaction Direction

- Style keywords:
- Layout direction:
- Color notes:
- Typography notes:
- Image strategy:
- Motion level:
- Motion should support:
- Motion should avoid:

## 9. Constraints And Assumptions

- Hosting:
- Repository or deployment target:
- Language:
- External resources:
- Available materials:
- Placeholders allowed:
- Assumptions to confirm:

## 10. Companion Skill Routing

- Taste/design direction:
- Theme:
- Frontend implementation:
- Image/media:
- Review:

## 11. Implementation Plan

- Site structure:
- Page model and page map:
- Target files:
- Asset organization:
- Validation:
- Publishing:
- Confirmation before editing:

## 12. Change Baseline

This requirements document is the current build baseline. If identity, audience, content priority, privacy, or visual direction changes, update the affected section and reconfirm before implementation continues.

## 13. Adjustment Approval Rule

For later page adjustments, do not edit files from a broad request alone. First summarize:

- what will change
- where it will change
- what visitors will notice
- which files are likely affected
- how it will be validated

Then wait for explicit user confirmation.
```

## Change Confirmation Template

Use this when the user changes requirements after a baseline has been confirmed.

```text
This changes the confirmed plan in one area:

- Previous:
- New:
- Impact:
- Files or sections affected:

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
