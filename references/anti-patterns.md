# Anti-Patterns

Avoid these failures when using `personal-homepage-builder`.

## Discovery Failures

- Asking "what style do you want?" before understanding identity and audience.
- Treating MBTI, zodiac, hobbies, or favorite media as deterministic personality facts.
- Publishing personal details without confirming public boundaries.
- Asking too many questions at once.
- Accepting source materials as final intent without user confirmation.

## Brief Failures

- Mixing confirmed facts and agent inference without labels.
- Omitting audience, first impression, or remembered-for.
- Omitting explicit avoids.
- Omitting the motion decision, including whether motion is disabled or enabled.
- Omitting companion skill routing.
- Using emoji by default.
- Writing a generic portfolio brief that could fit anyone.

## Design Failures

- Jumping into UI before identity reflection and taste discovery.
- Ignoring `design-taste-frontend` or equivalent taste routing when available.
- Producing a generic hero, three equal cards, and social icons layout without personal rationale.
- Letting a hobby dominate the whole site when it should only be an accent.
- Using rich media because it is available rather than because it supports identity or audience.
- Forcing dynamic effects after the user asked for no motion.
- Adding heavy motion because it looks impressive rather than because it supports the person's content.
- Answering mid-project design questions with generic option lists instead of inspecting the current homepage.

## Implementation Failures

- Ignoring the existing stack and project conventions.
- Creating one large monolithic HTML file for a real homepage when a maintainable `assets/css`, `assets/js`, and `assets/images` structure would fit.
- Hard-coding maintainable profile data when a data file or schema would fit better.
- Referencing generated assets that were not saved into the project.
- Adding backend-only features to a simple GitHub Pages site.
- Adding motion that ignores `prefers-reduced-motion`, causes layout shift, blocks reading, or depends on JavaScript for core content.
- Rebuilding the whole homepage for a small iteration request when a scoped edit would solve it.
- Staging unrelated files.

## Review Failures

- Declaring completion without build/test or a stated reason.
- Skipping responsive, accessibility, text-fit, and visual hierarchy checks.
- Shipping visible placeholder copy.
- Pushing without user approval.
- Force pushing without explicit overwrite approval.
