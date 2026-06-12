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
- During post-first-version visual iteration, do not call every companion skill automatically. Use `visual-iteration.md` to decide which installed skills are actually relevant, then invoke those relevant skills before the matching output.
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

## Implementation Evidence

The implementation plan must include routing evidence, not only future intentions:

- Taste/design direction: invoked before finalizing visual direction, or fallback recorded.
- Theme: invoked before finalizing color/type/spacing tokens when that work is needed, or fallback recorded.
- Frontend/UI: invoked before building or substantially redesigning visible UI when available, or fallback recorded.
- Media/image: invoked when generated raster imagery, portrait treatment, textures, or original visual assets are needed, or marked not applicable.
- Artifact builder: invoked only for confirmed complex React/Tailwind/shadcn or multi-state artifacts, or marked not applicable.
- Review: planned before implementation and actually invoked before final delivery when available, or fallback recorded.

If a companion skill is unavailable, continue with the relevant bundled reference files unless the user explicitly made that skill a hard requirement. Do not block a GitHub Pages site only because an optional companion skill is missing.

## Iteration Routing

For post-brief changes, route only the skills relevant to the classified change:

- No brief update needed: invoke companion skills only if the visible UI/design/motion work needs them.
- Implementation-only fix: usually no taste/theme/frontend routing is needed unless the fix changes visible UI; still use review fallback or `quality-checklist.md` when accessibility, responsive, motion, or GitHub Pages compatibility is involved.
- Brief patch: invoke the relevant taste, theme, frontend, media, or motion route before producing the updated plan when that area changes.
- New brief version: rerun the applicable design routing because the old taste/theme/frontend assumptions may no longer apply.
- Publish-only action: do not invoke design/frontend skills unless validation reveals a visible defect; use publish checks and git scope instead.

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

## Visual Iteration Routing Template

Use this when the user is unhappy with the first version or asks to revise style:

```text
Visual iteration routing:
- Diagnosis route: <visual-iteration.md used>
- Taste: <invoked skill, unavailable fallback, or not applicable with reason>
- Theme: <invoked skill, unavailable fallback, or not applicable with reason>
- Frontend/UI: <invoked skill, unavailable fallback, or not applicable with reason>
- Media/Image: <invoked skill, unavailable fallback, or not applicable with reason>
- Motion: <level, change, and reduced-motion fallback>
- Artifact complexity: <web-artifacts-builder invoked, fallback, or not applicable with reason>
- Review: <planned invoked skill, unavailable fallback, or not applicable with reason>
```
