# Forward Tests

Use these prompts to test future versions of the skill. A passing run should follow the session protocol, respect output gates, route companion skills when available, and avoid emoji by default.

For a complete first-person beginner transcript, use `beginner-validation-scenario.md`.

## Test 1: No Materials

Prompt:

```text
Use $personal-homepage-builder. I want a personal homepage but I do not know what style I want.
```

Expected behavior:

- Do not ask "what style do you want?"
- Use the beginner conversation patterns and Quick Start path.
- Internally default to `Deep Profile`, `Profile` quality, and `subtle` motion unless the user gives a stronger signal, but do not expose those labels to a beginner.
- Explain that discovery will happen in short rounds before code.
- Give a light materials roadmap instead of demanding all materials upfront.
- Ask 1-3 questions or choices about identity, audience, first impression, remembered-for, and privacy.
- Offer concrete choices if the user cannot answer abstract questions.
- Optionally provide a non-code direction card, page map, or text wireframe as a probe.
- Do not assume the result must be one page; determine whether a one-page, hybrid, or multi-page structure fits.
- Do not collapse zero-prep discovery into a final brief after only a few short turns unless the minimum coverage is actually satisfied or the user explicitly chooses a quick path.
- Build a session state.
- Do not implement yet.

## Test 2: Resume And Links

Prompt:

```text
Use $personal-homepage-builder. Here is my resume, GitHub, LinkedIn, and project list. Turn it into a homepage.
```

Expected behavior:

- Extract source materials first.
- Identify privacy risks and missing links.
- Produce identity reflection before style direction.
- Ask targeted confirmation questions.

## Test 3: Existing Homepage Redesign

Prompt:

```text
Use $personal-homepage-builder to redesign my existing github.io site. It feels generic.
```

Expected behavior:

- Inspect project stack and current pages.
- Audit what feels generic.
- Preserve user-approved content and URLs.
- Use taste and frontend routing before UI changes.

## Test 4: Academic Profile

Prompt:

```text
Use $personal-homepage-builder to build an academic profile for my papers, CV, talks, and contact links.
```

Expected behavior:

- Prioritize credibility, publications, research themes, and contact.
- Avoid over-stylized creator-site patterns unless user asks.
- Confirm public/private boundaries around CV and email.

## Test 5: Media-Forward Creator

Prompt:

```text
Use $personal-homepage-builder. I want photos, video links, music references, and social links in the site.
```

Expected behavior:

- Use media asset guidance.
- Explain muted video and audio autoplay constraints.
- Do not add rich media unless it supports identity and audience.
- Include media strategy in the brief.

## Test 6: User Tries To Skip Gates

Prompt:

```text
Just code it now. Make it look cool.
```

Expected behavior:

- Compress the workflow but do not skip gates silently.
- Produce minimal identity reflection and brief.
- Select an inferred delivery mode and quality tier internally instead of asking the user to understand the tier system.
- Ask the smallest number of high-impact confirmation questions.
- Do not implement until the minimal brief is accepted or the user explicitly accepts a quick-path risk.

## Test 12: Beginner Preference Discovery

Prompt:

```text
Use $personal-homepage-builder. I am a beginner and only know that I want the homepage to feel like me. I do not know what style, structure, or effects I want.
```

Expected behavior:

- Use the preference discovery ladder from `personal-signal-intake.md`.
- Ask easy personal questions and choice-driven prompts before design terms.
- Tell the user what materials may be useful in later rounds.
- Translate answers into delivery mode, quality tier, style direction, content structure, and motion level internally.
- Clearly label confirmed facts versus inferred design direction.
- Offer 2-3 design directions and recommend one before implementation.
- Do not ask the user to manually choose between `Basic`, `Profile`, `Creator`, `Academic`, or `Premium` unless they ask to control the tier.
- For a full end-to-end version of this test, run `beginner-validation-scenario.md`.

## Test 7: Publishing

Prompt:

```text
Push this to GitHub Pages.
```

Expected behavior:

- Confirm repository, branch, and publish intent.
- Check git scope.
- Do not stage unrelated files.
- Do not force push unless overwrite is explicitly requested.

## Test 8: New Static Site Implementation

Prompt:

```text
Use $personal-homepage-builder to build my personal homepage from scratch as a static GitHub Pages site.
```

Expected behavior:

- Produce a confirmed brief before implementation.
- Use the site structure guidance.
- Confirm whether the site is single-page, hybrid, or multi-page.
- Create `index.html` plus any confirmed supporting pages and separated assets such as `assets/css/`, `assets/js/`, and `assets/images/`.
- Avoid a large monolithic HTML file unless the user explicitly requests a disposable prototype.

## Test 8B: Multi-Page Personal Site

Prompt:

```text
Use $personal-homepage-builder. I want a personal site with an intro, several projects, writing notes, and a contact page. I am not sure whether this should be one page or multiple pages.
```

Expected behavior:

- Ask what should be immediately visible on the homepage versus what needs its own space.
- Recommend a page model: one page, hybrid, or multi-page.
- Produce a page map before implementation, including page names, paths, purpose, and core content.
- Confirm navigation labels and whether placeholders are acceptable.
- Do not force all content into one long homepage.
- Do not create empty pages just to make the site feel larger.

## Test 9: Optional Motion

Prompt:

```text
Use $personal-homepage-builder. I want the page to feel more dynamic, but not distracting.
```

Expected behavior:

- Discuss motion as an optional design choice.
- Propose a `subtle` or `moderate` motion strategy based on content and audience.
- Include entrance, scroll reveal, hover/focus, state feedback, and reduced-motion fallback in the brief.
- Do not add heavy particle effects, scroll hijacking, autoplay sound, or motion that blocks reading.

## Test 10: Motion Disabled

Prompt:

```text
Use $personal-homepage-builder. I want a simple personal homepage with no animation or dynamic effects.
```

Expected behavior:

- Set `motion_strategy.level` to `none`.
- Do not later reintroduce reveal animations, parallax, cursor effects, autoplay media, or decorative motion during design or implementation.
- Keep instant hover/focus feedback for usability where appropriate.
- Still respect `prefers-reduced-motion` and keep the page readable without JavaScript.

## Test 11: Mid-Project Dynamic Request

Prompt:

```text
Use $personal-homepage-builder. The homepage is already partly built. I feel like it may need some dynamic elements, but I do not know what would fit. What do you think?
```

Expected behavior:

- Treat this as an iteration request, not a full restart.
- Inspect the current page files, screenshot, or link before recommending effects; ask for one if unavailable.
- Offer 2-4 specific options tied to current sections and page goals.
- Recommend one option with rationale, complexity, and risk.
- Use `motion-design.md` for the motion level and reduced-motion fallback.
- Produce a compact change plan after the user chooses a direction.
- Do not implement until the user explicitly confirms the change plan.

## Test 11B: Direct Adjustment Request

Prompt:

```text
Use $personal-homepage-builder. My homepage is already built. Please make the project section look better and add some motion.
```

Expected behavior:

- Inspect current page files, screenshot, or link before recommending changes; ask for one if unavailable.
- Treat the request as permission to analyze and propose, not permission to edit.
- Explain 2-4 concrete options tied to the current page.
- Produce a compact change plan with target files, visible effect, motion level, validation, and risk.
- Ask for explicit confirmation before editing code.
- Do not modify files immediately, even though the user asked to "make" the change.
