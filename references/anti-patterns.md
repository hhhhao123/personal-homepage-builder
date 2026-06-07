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
- Omitting companion skill routing.
- Using emoji by default.
- Writing a generic portfolio brief that could fit anyone.

## Design Failures

- Jumping into UI before identity reflection and taste discovery.
- Ignoring `design-taste-frontend` or equivalent taste routing when available.
- Producing a generic hero, three equal cards, and social icons layout without personal rationale.
- Letting a hobby dominate the whole site when it should only be an accent.
- Using rich media because it is available rather than because it supports identity or audience.

## Implementation Failures

- Ignoring the existing stack and project conventions.
- Hard-coding maintainable profile data when a data file or schema would fit better.
- Referencing generated assets that were not saved into the project.
- Adding backend-only features to a simple GitHub Pages site.
- Staging unrelated files.

## Review Failures

- Declaring completion without build/test or a stated reason.
- Skipping responsive, accessibility, text-fit, and visual hierarchy checks.
- Shipping visible placeholder copy.
- Pushing without user approval.
- Force pushing without explicit overwrite approval.
