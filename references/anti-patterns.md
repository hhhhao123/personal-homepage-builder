# Anti-Patterns

Avoid these failures when using `personal-homepage-builder`.

## Discovery Failures

- Asking "what style do you want?" before understanding identity and audience.
- Asking beginners to choose delivery modes, quality tiers, or design systems before translating their plain-language needs.
- Asking beginners to provide "functional requirements", "non-functional requirements", "content model", "motion strategy", or "deployment constraints" as a form.
- Exposing internal schema names, output gate names, or state-machine labels to ordinary users.
- Treating MBTI, zodiac, hobbies, or favorite media as deterministic personality facts.
- Publishing personal details without confirming public boundaries.
- Asking too many questions at once.
- Accepting source materials as final intent without user confirmation.
- Repeating abstract questions after the user says they do not know, instead of offering choices or a probe sketch.
- Refusing to provide any concrete direction until a perfect requirements document exists.

## Brief Failures

- Mixing confirmed facts and agent inference without labels.
- Omitting audience, first impression, or remembered-for.
- Omitting explicit avoids.
- Omitting the motion decision, including whether motion is disabled or enabled.
- Omitting companion skill routing.
- Omitting whether the project should be one page, a homepage with supporting pages, or a multi-page site.
- Using emoji by default.
- Writing a generic portfolio brief that could fit anyone.
- Treating a probe sketch or direction card as a confirmed brief.
- Letting a confirmed brief drift after user changes without reconfirming the affected part.
- Treating a user's broad adjustment request as permission to edit files before a concrete change plan is confirmed.
- Continuing to implement from an old brief after audience, purpose, page model, privacy, content priority, or visual direction changed.
- Creating multiple competing active briefs instead of marking one current effective version.

## Design Failures

- Jumping into UI before identity reflection and taste discovery.
- Treating a non-code probe sketch as permission to begin implementation.
- Ignoring `design-taste-frontend` or equivalent taste routing when available.
- Producing a generic hero, three equal cards, and social icons layout without personal rationale.
- Letting a hobby dominate the whole site when it should only be an accent.
- Using rich media because it is available rather than because it supports identity or audience.
- Forcing dynamic effects after the user asked for no motion.
- Adding heavy motion because it looks impressive rather than because it supports the person's content.
- Answering mid-project design questions with generic option lists instead of inspecting the current homepage.
- Editing UI, layout, motion, navigation, copy, or content before the user confirms the proposed adjustment.

## Implementation Failures

- Ignoring the existing stack and project conventions.
- Creating one large monolithic HTML file for a real homepage when a maintainable `assets/css`, `assets/js`, and `assets/images` structure would fit.
- Forcing all content into one long page when projects, writing, publications, services, or media clearly need supporting pages.
- Adding empty supporting pages only because multi-page sites seem more complete.
- Implementing multiple pages without confirming page names, paths, navigation, and which content belongs on each page.
- Generating HTML/CSS/JS during the requirement-discovery phase unless the user explicitly asked for a disposable prototype and a minimal brief exists.
- Hard-coding maintainable profile data when a data file or schema would fit better.
- Referencing generated assets that were not saved into the project.
- Adding backend-only features to a simple GitHub Pages site.
- Adding motion that ignores `prefers-reduced-motion`, causes layout shift, blocks reading, or depends on JavaScript for core content.
- Rebuilding the whole homepage for a small iteration request when a scoped edit would solve it.
- Applying "you decide" or "make it better" as implicit approval to change files without discussion.
- Updating code for a brief-impacting change without patching or versioning the brief first.
- Staging unrelated files.

## Review Failures

- Declaring completion without build/test or a stated reason.
- Skipping responsive, accessibility, text-fit, and visual hierarchy checks.
- Shipping visible placeholder copy.
- Pushing without user approval.
- Force pushing without explicit overwrite approval.
