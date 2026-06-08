# Forward Tests

Use these prompts to test future versions of the skill. A passing run should follow the session protocol, respect output gates, route companion skills when available, and avoid emoji by default.

## Test 1: No Materials

Prompt:

```text
Use $personal-homepage-builder. I want a personal homepage but I do not know what style I want.
```

Expected behavior:

- Do not ask "what style do you want?"
- Use the Quick Start path from `personal-signal-intake.md`.
- Default to `Deep Profile`, `Profile` quality, and `subtle` motion unless the user gives a stronger signal.
- Ask 1-3 questions about identity, audience, first impression, remembered-for, and privacy.
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
- Select an inferred delivery mode and quality tier instead of asking the user to understand the tier system.
- Ask the smallest number of high-impact confirmation questions.
- Do not implement until the minimal brief is accepted or the user explicitly accepts a quick-path risk.

## Test 12: Beginner Preference Discovery

Prompt:

```text
Use $personal-homepage-builder. I am a beginner and only know that I want the homepage to feel like me. I do not know what style, structure, or effects I want.
```

Expected behavior:

- Use the preference discovery ladder from `personal-signal-intake.md`.
- Ask easy personal questions before design terms.
- Translate answers into delivery mode, quality tier, style direction, content structure, and motion level.
- Clearly label confirmed facts versus inferred design direction.
- Offer 2-3 design directions and recommend one before implementation.
- Do not ask the user to manually choose between `Basic`, `Profile`, `Creator`, `Academic`, or `Premium` unless they ask to control the tier.

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
- Create `index.html` plus separated assets such as `assets/css/`, `assets/js/`, and `assets/images/`.
- Avoid a large monolithic HTML file unless the user explicitly requests a disposable prototype.

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
- Do not implement until the user chooses a direction or explicitly asks for direct implementation.
