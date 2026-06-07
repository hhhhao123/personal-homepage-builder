# Skill Routing

Use this file to decide which companion skills or equivalent capabilities to invoke during personal homepage work.

## Routing Table

| Stage | Use when available | Purpose | Fallback |
| --- | --- | --- | --- |
| Taste discovery | `design-taste-frontend`, `taste-skill`, `taste`, or equivalent | Infer design direction, layout variance, visual density, motion level, and anti-template constraints from the brief and user signals. | Use `references/style-directions.md` and state that no taste skill is available. |
| Theme system | `theme-factory` or equivalent | Choose or create color, typography, spacing, and token systems. | Define a compact theme directly in the brief. |
| Frontend UI | `frontend-design` or equivalent | Produce distinctive, production-quality page composition and responsive UI. | Use local frontend rules plus `references/implementation.md`. |
| Complex artifact | `web-artifacts-builder` | Build complex React, Tailwind, shadcn, or multi-state web artifacts. | Keep implementation static or use the existing stack. |
| Image/media asset | `imagegen` | Generate hero images, portrait treatments, textures, or other raster visuals. | Use typography-first layout, user-provided assets, or simple code-native visuals. |
| Review | `web-design-guidelines` or equivalent | Final UI, UX, accessibility, responsive, and text-fit review. | Use `references/quality-checklist.md` and document the fallback. |
| Docs lookup | Context7 or equivalent official docs lookup | Fetch current library, framework, SDK, CLI, or cloud docs. | Use official documentation or the best available retrieval path. |

## Required Behavior

- Before UI customization, attempt taste routing first.
- Before implementation, attempt frontend UI routing first.
- Before final delivery, attempt review routing first.
- If a companion skill is unavailable, do not stop unless the user explicitly required it. State the fallback and continue.
- Do not install companion skills automatically.
- Do not claim a companion skill was used unless it was actually available and invoked.

## Routing Statement Template

Use this before implementation:

```text
Design routing:
- Taste: <skill used or fallback>
- Theme: <skill used or fallback>
- Frontend/UI: <skill used or fallback>
- Media: <skill used or not needed>
- Motion: <level and rationale, or none>
- Review: <planned skill or fallback>
```
