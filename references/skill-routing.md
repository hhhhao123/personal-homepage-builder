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

- If a companion skill is installed or otherwise available in the current agent runtime and its stage is applicable, invocation is mandatory. Use the skill before producing the matching design, implementation, or review output.
- Do not merely name a companion skill in the routing statement. The routing statement must reflect actual use: `invoked`, `unavailable fallback`, or `not applicable`.
- Do not skip an available companion skill because the base agent can do the work without it. The purpose of this skill is to route to specialized taste, theme, frontend, media, and review support when available.
- Before UI customization, invoke taste routing first when `design-taste-frontend`, `taste-skill`, `taste`, or an equivalent skill is available.
- Before choosing or finalizing colors, type, spacing, tokens, or visual system rules, invoke `theme-factory` or an equivalent theme skill when available.
- Before implementation or substantial visual redesign, invoke `frontend-design` or an equivalent frontend/UI skill when available.
- Before final delivery, invoke `web-design-guidelines` or an equivalent review skill when available.
- Invoke `web-artifacts-builder` when the confirmed project is a complex React, Tailwind, shadcn, routed, or multi-state web artifact and the skill is available.
- Invoke `imagegen` when the confirmed direction needs original raster imagery, hero art, portrait treatment, textures, or generated visual assets and the skill is available.
- If a companion skill is unavailable, do not stop unless the user explicitly required it. State the fallback and continue.
- Do not install companion skills automatically.
- Do not claim a companion skill was used unless it was actually available and invoked.
- `Not applicable` is allowed only with a concrete reason, such as "no raster asset needed", "static HTML/CSS site, not a complex React artifact", or "no external framework docs needed".

## Routing Statement Template

Use this before implementation:

```text
Design routing:
- Taste: <invoked skill, unavailable fallback, or not applicable with reason>
- Theme: <invoked skill, unavailable fallback, or not applicable with reason>
- Frontend/UI: <invoked skill, unavailable fallback, or not applicable with reason>
- Media: <invoked skill, unavailable fallback, or not applicable with reason>
- Motion: <level and rationale, or none>
- Artifact complexity: <web-artifacts-builder invoked, fallback, or not applicable with reason>
- Review: <planned invoked skill, unavailable fallback, or not applicable with reason>
```
