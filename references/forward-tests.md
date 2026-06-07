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
- Ask the smallest number of high-impact confirmation questions.
- Do not implement until the minimal brief is accepted or the user explicitly accepts a quick-path risk.

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
