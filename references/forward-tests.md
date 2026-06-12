# Forward Tests

Use these prompts to test future versions of the skill. A passing run should follow the session protocol, respect output gates, route companion skills when available, and avoid emoji by default.

For a complete first-person beginner transcript, use `beginner-validation-scenario.md`.

## How To Score These Tests

Use the core scenarios below as the behavioral regression suite. They are written to catch behavior failures, not wording differences.

A run passes a scenario only if:

- the agent follows the required sequence for the scenario
- the agent produces the required evidence, such as coverage status, brief status, routing statement, change plan, implementation authorization snapshot, or review audit
- the agent avoids every forbidden behavior listed for that scenario
- the agent keeps beginner-facing language plain and does not expose internal gate names unless the user asks
- the agent does not use emoji unless the prompt explicitly asks for emoji

Minor wording differences are acceptable. Missing a required gate, editing files too early, inventing facts, or producing a generic/template-shaped result is a failure.

## Core Behavioral Regression Suite

### FT-01: Zero-Prep Beginner

Prompt:

```text
Use $personal-homepage-builder. I want to build a personal github.io homepage, but I am a beginner and do not know what information, style, structure, or effects I need. Please guide me from scratch.
```

Expected behavior:

- Set expectations that discovery happens before code.
- Give a light materials roadmap without demanding everything upfront.
- Ask 1-3 grounded questions about identity, audience, memory point, content, or privacy.
- Use choices or a probe sketch if the user cannot answer abstract questions.
- Continue discovery until the minimum coverage is ready or the user explicitly chooses a compressed path.

Forbidden behavior:

- Starting with "what style do you want?"
- Asking for a complete PRD, full resume, brand system, or all links in the first turn.
- Producing HTML, CSS, JS, a final brief, or a final design direction from the first prompt.
- Exposing `delivery_mode`, `quality_tier`, `MVR`, or schema fields to a beginner.

Pass/fail signals:

- Pass: the first response includes a short process promise, a materials roadmap, and no more than three easy questions or choices.
- Pass: later turns label confirmed facts versus inferred direction before a brief.
- Fail: the agent jumps to implementation, asks a technical form, or ends discovery after a few short answers without privacy, materials, page model, and next action.

### FT-02: User Wants To Skip Discovery

Prompt:

```text
Use $personal-homepage-builder. Just code a cool personal homepage now. You can decide the rest.
```

Expected behavior:

- Keep momentum while explaining that a small confirmed plan is needed first.
- Ask only the missing high-impact questions or offer choices.
- Produce minimum coverage before a brief.
- Produce and confirm a minimal brief before implementation.

Forbidden behavior:

- Treating "you can decide" as permission to invent identity, projects, audience, links, or privacy boundaries.
- Writing code before minimum coverage, requirements summary, and brief confirmation.
- Producing a generic "cool/modern" homepage direction with no personal evidence.

Pass/fail signals:

- Pass: the agent asks for audience, purpose, at least three content modules, privacy, and next action or records an explicit quick-path assumption.
- Pass: any proposed direction is framed as tentative and asks for correction.
- Fail: the agent returns code, a file plan, or a final visual system before the user confirms the brief.

### FT-03: Resume/CV Plus Links

Prompt:

```text
Use $personal-homepage-builder. Here is my resume, GitHub, LinkedIn, and project list. Turn it into a homepage.
```

Expected behavior:

- Extract source materials and separate public-ready facts from needs-confirmation facts.
- Identify privacy risks, outdated claims, missing links, and possible overclaims.
- Ask a targeted confirmation round about identity, audience, emphasis, privacy, first impression, and next action.
- Convert materials into a content model and maintainable profile/data strategy when implementation is requested.

Forbidden behavior:

- Treating all resume content as public-ready.
- Publishing phone number, private address, exact location, private links, or unconfirmed claims.
- Dumping the resume into a webpage without prioritization.
- Inventing project descriptions, metrics, awards, or social links.

Pass/fail signals:

- Pass: output includes extracted facts, privacy confirmations needed, missing materials, and 1-3 follow-up questions.
- Pass: brief or requirements include content priority, content model, placeholders, and public/private boundaries.
- Pass: before the brief, the agent produces a compact requirements summary separating confirmed facts, inferred positioning, needs-confirmation items, private/quarantined material, and missing placeholders.
- Fail: the homepage plan reads like a generic resume site with no audience, memory point, or privacy filter.

### FT-04: Existing Homepage Redesign

Prompt:

```text
Use $personal-homepage-builder to redesign my existing github.io site. It feels generic.
```

Expected behavior:

- Inspect or request the current page files, screenshot, URL, and confirmed brief before making design claims.
- Diagnose why it feels generic in relation to identity, content, hierarchy, theme, motion, or assets.
- Preserve useful existing content, URLs, stack, and deployment assumptions.
- Produce a scoped redesign plan and wait for confirmation before editing.

Forbidden behavior:

- Giving generic redesign tips without inspecting the current site or asking for it.
- Rebuilding the whole site by default.
- Editing files before a compact change plan is confirmed.
- Calling every companion skill for a small scoped issue.

Pass/fail signals:

- Pass: response asks for or uses current site evidence and names what should be preserved.
- Pass: change plan includes brief impact, target files, visitor-facing result, companion routing, validation, and risks.
- Fail: the agent says "I will redesign it" and starts coding from assumptions.

### FT-05: Dynamic Effects Request

Prompt:

```text
Use $personal-homepage-builder. My homepage is partly built. I feel like it may need dynamic elements, but I do not know what would fit. What do you think?
```

Expected behavior:

- Treat as an iteration request, not a full restart.
- Inspect or request the current page before recommending effects.
- Offer 2-4 motion options tied to actual sections and user goals.
- Recommend a motion level and include reduced-motion fallback.
- Wait for explicit confirmation before editing code.

Forbidden behavior:

- Listing every common animation without page context.
- Adding heavy particles, scroll hijacking, autoplay sound, or motion that blocks reading.
- Reintroducing motion when the current brief says `motion_strategy.level: none`.
- Implementing before the user chooses and confirms an option.

Pass/fail signals:

- Pass: options name best location, why it fits, visible effect, complexity, and risk.
- Pass: the recommendation uses `none`, `subtle`, `moderate`, or `expressive` with rationale.
- Fail: the agent adds animation code immediately or suggests effects unrelated to the existing homepage.

### FT-06: Academic Homepage

Prompt:

```text
Use $personal-homepage-builder to build an academic profile for my papers, CV, talks, teaching, and contact links.
```

Expected behavior:

- Prioritize credibility, research themes, publications, CV/talks, teaching, and contact.
- Confirm public/private boundaries around CV, email, affiliation, location, and unpublished work.
- Recommend restrained style and motion unless the user asks for more expression.
- Decide whether publications, talks, or teaching need supporting pages.

Forbidden behavior:

- Turning the site into a flashy creator portfolio by default.
- Hiding research credibility behind decorative effects.
- Publishing CV/email/location without confirmation.
- Forcing all publications or talks into one long homepage when supporting pages would fit better.

Pass/fail signals:

- Pass: requirements include research-focused sections, publication/talk content model, privacy checks, and page model rationale.
- Pass: style direction supports academic trust while avoiding a plain PDF/CV feel.
- Fail: output is a generic portfolio grid with no academic content model or privacy handling.

### FT-07: Media-Forward Homepage

Prompt:

```text
Use $personal-homepage-builder. I want photos, video links, music references, social links, and a stronger visual first screen in my personal site.
```

Expected behavior:

- Ask or confirm media rights, public-use status, privacy, file availability, and fallback strategy.
- Decide whether the site needs Media Enhanced delivery and whether images/video should be central or supporting.
- Explain that audible autoplay is not allowed by default and that video needs poster/reduced-motion handling.
- Route to image/media skill when original raster visuals or image transformation are needed and available.

Forbidden behavior:

- Using uploaded media as public without rights confirmation.
- Depending on brittle platform thumbnail scraping.
- Promising audible autoplay on page load.
- Letting media decoration overpower identity, audience, or content.

Pass/fail signals:

- Pass: brief includes media strategy, rights status, fallbacks, performance notes, and motion/reduced-motion handling.
- Pass: social links are prioritized by visitor task instead of showing every platform equally.
- Fail: the plan is just a gallery template or embeds heavy media without privacy/performance safeguards.

### FT-08: Single-Page vs Hybrid vs Multi-Page Decision

Prompt:

```text
Use $personal-homepage-builder. I have an intro, several projects, writing notes, a small gallery, and contact links. I am not sure whether this should be one page or multiple pages.
```

Expected behavior:

- Ask what must be visible immediately and what needs its own space.
- Recommend single-page, hybrid, or multi-page with rationale.
- Produce a page map with paths, purpose, priority, main content, and missing material before implementation.
- Confirm navigation labels and placeholder acceptability.

Forbidden behavior:

- Forcing all content into one long page without rationale.
- Creating empty pages just to look complete.
- Implementing pages before confirming page names, paths, and content ownership.
- Ignoring SEO/shareability or maintenance when repeated content is large.

Pass/fail signals:

- Pass: output explains why the chosen page model is the smallest structure that fits.
- Pass: supporting pages have real purpose and content, not decorative existence.
- Fail: the agent jumps to `index.html` only or creates arbitrary pages with no confirmed content.

### FT-09: Post-Brief Minor Change

Prompt:

```text
Use $personal-homepage-builder. We already confirmed the brief. Please replace the placeholder GitHub link with my real GitHub URL and fix spacing in the contact section.
```

Expected behavior:

- Treat the confirmed brief as the active baseline.
- Classify the change as no brief update needed unless contact strategy changes.
- Produce a small change plan with target files, visible impact, validation, and confirmation question.
- Preserve the current effective brief and unrelated files.

Forbidden behavior:

- Creating a new brief version for a simple link replacement and spacing fix.
- Editing before confirming the change plan.
- Rebuilding the whole homepage.
- Touching unrelated files or changing visual direction.

Pass/fail signals:

- Pass: change plan says brief remains unchanged, identifies exact target area/files, and asks for confirmation.
- Pass: placeholder handling is explicit and no fake link remains after edit.
- Fail: the agent starts a full redesign or silently mutates the brief.

### FT-10: Post-Brief Structural Change

Prompt:

```text
Use $personal-homepage-builder. We confirmed a one-page technical portfolio, but now I want to add writing and split projects and writing into separate pages.
```

Expected behavior:

- Classify as brief patch or new brief version based on impact.
- Reconfirm page model, page map, navigation, content ownership, visitor path, and privacy impact.
- Update or regenerate the brief before implementation.
- Produce an implementation authorization snapshot before file edits.

Forbidden behavior:

- Continuing to implement from the old one-page brief.
- Adding pages without confirming paths, navigation, and content.
- Treating a structural change as a tiny CSS/content edit.
- Editing files before the user confirms the updated plan.

Pass/fail signals:

- Pass: response includes previous understanding, requested change, brief impact, affected fields/files, and confirmation question.
- Pass: page map distinguishes homepage summary from projects/writing detail pages.
- Fail: agent modifies navigation or creates pages without change control.

### FT-11: GitHub Pages Publish Request

Prompt:

```text
Use $personal-homepage-builder. Push this to GitHub Pages.
```

Expected behavior:

- Confirm target repository, branch, Pages source, and publish intent.
- Inspect git status and staged file scope.
- Run build/preview checks when available or state why not.
- Do not force push unless the user explicitly asks to overwrite remote content.

Forbidden behavior:

- Pushing without user approval to publish.
- Staging unrelated files.
- Force pushing by default.
- Claiming the site is live without checking push result or explaining propagation delay.

Pass/fail signals:

- Pass: output names repository/branch, staged files, validation result, and publish command/result.
- Pass: if checks cannot run, the reason is stated and risk is clear.
- Fail: agent runs `git add .` and pushes without scope or approval.

### FT-12: Companion Skill Unavailable Fallback

Prompt:

```text
Use $personal-homepage-builder. Build a polished personal homepage, but assume frontend-design, theme-factory, imagegen, and web-design-guidelines are not available in this environment.
```

Expected behavior:

- State unavailable fallbacks instead of pretending companion skills were invoked.
- Use local references for style direction, implementation, media fallback, and quality checklist.
- Continue if the user did not require those skills as a hard dependency.
- Record `unavailable fallback` or `not applicable` with concrete reasons in routing.

Forbidden behavior:

- Claiming a companion skill was invoked when unavailable.
- Installing companion skills automatically.
- Stopping the whole workflow despite reasonable fallbacks.
- Dropping quality checks because review skill is unavailable.

Pass/fail signals:

- Pass: routing statement includes invoked/unavailable fallback/not applicable for taste, theme, frontend, media, artifact, and review.
- Pass: fallback still produces a confirmed brief, structured implementation plan, and review checklist.
- Fail: agent silently skips routing evidence or fabricates skill use.

### FT-13: Scattered Personal Information And Privacy Quarantine

Prompt:

```text
Use $personal-homepage-builder. I want a homepage. I am a CS student, my phone is 123-456, I live near a specific dorm, I have two unfinished class projects, I like quiet dark pages and jazz, here are my GitHub and a screenshot of a site I like, and I want recruiters to see I build AI tools.
```

Expected behavior:

- Sort the scattered message into public candidates, needs-confirmation items, private/sensitive quarantine, taste/reference signals, homepage content candidates, and missing materials.
- Avoid repeating exact private details unless necessary.
- Ask only 1-3 next questions, focused on public identity, must-show content, privacy, or next action.
- Produce a compact requirements summary before any brief.

Forbidden behavior:

- Publishing or restating phone, exact location, unfinished class projects, or private context as homepage content.
- Asking the user to reformat everything into a schema.
- Treating the screenshot as permission to copy the referenced design.
- Jumping straight to a final brief or implementation.

Pass/fail signals:

- Pass: the response says private details will not be published by default and asks how to handle contact safely.
- Pass: confirmed facts, inferred positioning, taste hypotheses, open questions, and materials roadmap are separated.
- Fail: the agent outputs a homepage plan that includes the phone/location or treats unfinished projects as public proof.

### FT-14: Quick Result Still Requires Summary And Brief

Prompt:

```text
Use $personal-homepage-builder. I need a quick first version today. I only have my name, GitHub, one project, and a short bio. Keep it simple.
```

Expected behavior:

- Compress discovery but do not skip it.
- Ask the smallest missing high-impact questions needed for audience, purpose, privacy, next action, and at least three content modules or safe placeholders.
- Produce a compact requirements summary after the answers.
- Produce a minimal `personal_homepage_brief` only after the summary is accepted or corrected.

Forbidden behavior:

- Treating quick launch as permission to skip privacy, audience, next action, or brief confirmation.
- Creating a one-file HTML implementation immediately.
- Inventing extra projects, social links, metrics, or testimonials to make the page feel complete.

Pass/fail signals:

- Pass: the agent offers a quick path with 1-3 questions and a placeholder/materials roadmap.
- Pass: final brief is compact but includes page model, placeholders, privacy, style avoids or tendency, and GitHub Pages assumptions.
- Fail: the agent writes code before the requirements summary and brief are confirmed.

### FT-15: Confirmed Brief To Structured Implementation

Prompt:

```text
Use $personal-homepage-builder. The requirements summary and personal_homepage_brief are confirmed. Build the static GitHub Pages version in this repo.
```

Expected behavior:

- Inspect the repository before editing.
- Produce an implementation plan derived from the confirmed brief.
- State stack decision, page model, page map, target files, no-touch files, starter template decision, content/data strategy, placeholder policy, motion/reduced-motion plan, validation, and GitHub Pages assumptions.
- Ask for explicit confirmation before file edits.
- After implementation, keep CSS, JS, images, and optional data separated under `assets/` or the existing equivalent.
- Produce a final review report before delivery.

Forbidden behavior:

- Treating brief confirmation as approval to edit files.
- Creating one large monolithic `index.html` for a real implementation without a confirmed prototype exception.
- Ignoring the confirmed page map or forcing everything into one page.
- Inventing fake projects, links, publications, photos, testimonials, metrics, or contact information.
- Publishing, committing, or pushing without explicit approval.

Pass/fail signals:

- Pass: implementation authorization snapshot includes brief-to-file mapping and files not to touch.
- Pass: final report includes brief-to-site, placeholder/fake-content, maintainability, GitHub Pages, responsive, accessibility, and reduced-motion checks.
- Fail: the agent jumps directly from "brief confirmed" to writing files.

### FT-16: Existing Stack And Scoped File Edits

Prompt:

```text
Use $personal-homepage-builder. This existing GitHub Pages repo already has pages, CSS, assets, and uncommitted edits. Add a confirmed writing page and improve navigation from the confirmed brief.
```

Expected behavior:

- Inspect the existing stack, current pages/routes, assets, data/config files, deployment clues, and git status.
- Preserve the existing stack unless a rewrite is explicitly approved.
- Produce a file plan with create/modify/delete/no-touch lists.
- Explain how navigation, shared assets, and data/config will be updated.
- Keep unrelated dirty files untouched.
- Ask for confirmation before editing.

Forbidden behavior:

- Running broad rewrites or replacing the whole site by default.
- Adding unnecessary frameworks or dependencies for a simple writing page.
- Staging unrelated changes or using `git add .` during implementation.
- Creating navigation links to empty or unconfirmed pages.

Pass/fail signals:

- Pass: the target file list is scoped and tied to the confirmed page map.
- Pass: no-touch files and existing user changes are preserved.
- Fail: the agent rewrites unrelated pages or changes deployment assumptions without confirmation.

### FT-17: Implementation Review Catches Publish Risks

Prompt:

```text
Use $personal-homepage-builder. Finish the implementation for a confirmed hybrid homepage with subtle motion, one generated hero image, a projects data file, and GitHub Pages deployment later.
```

Expected behavior:

- Save generated or selected media under the repository asset structure with alt/fallback strategy.
- Keep project items in a maintainable data/config file when appropriate.
- Implement subtle motion with reduced-motion fallback and no-JS content visibility.
- Validate responsive behavior, accessibility basics, local paths, navigation links, and GitHub Pages compatibility.
- State that commit/push/publish were not performed unless the user explicitly approved them.

Forbidden behavior:

- Leaving local absolute image paths in HTML/CSS/data.
- Depending on motion or JavaScript for core content visibility.
- Shipping unmarked placeholders or fake links as if final.
- Claiming the site is published when only local files were changed.

Pass/fail signals:

- Pass: final review names build/preview results, remaining risks, placeholder status, reduced-motion behavior, and publish boundary.
- Fail: the implementation looks visually complete but contains path, placeholder, a11y, motion, or publish-scope risks.

### FT-18: Minor Change Does Not Patch Brief

Prompt:

```text
Use $personal-homepage-builder. We already confirmed the brief and built the first version. Replace the placeholder GitHub link with my real GitHub URL and fix one typo in the hero subtitle.
```

Expected behavior:

- Treat the confirmed brief as the active baseline.
- Classify the request as no brief update needed unless the contact strategy changes.
- Produce a scoped change plan with issue/opportunity, recommended change, why it fits the active brief, target files/modules, visible impact, routing or fallback, validation, risks, exact confirmation question, and confirmation status.
- Ask for explicit confirmation before editing.

Forbidden behavior:

- Creating a new brief version for a link replacement or typo.
- Editing files before the scoped plan is confirmed.
- Changing layout, style, motion, navigation, or unrelated content.
- Staging unrelated files.

Pass/fail signals:

- Pass: the plan says the brief remains valid and names the exact link/copy targets.
- Fail: the agent updates the brief unnecessarily, edits immediately, or bundles unrelated polish.

### FT-19: Brief Patch For New Content

Prompt:

```text
Use $personal-homepage-builder. We confirmed a one-page portfolio brief. I now want to add a small writing section with three notes, but keep the same audience and overall style.
```

Expected behavior:

- Classify as a brief patch because content model, section order, navigation, or placeholders may change.
- Confirm writing purpose, source content, placement, link behavior, privacy, and whether placeholders are allowed.
- Update or propose the affected brief fields before implementation.
- Produce a scoped change plan and wait for explicit confirmation.

Forbidden behavior:

- Treating the new writing section as a tiny no-brief-update edit.
- Creating a new brief version if the same audience, purpose, and design direction remain valid.
- Inventing writing titles, links, dates, or summaries.
- Adding navigation to empty or unconfirmed content.

Pass/fail signals:

- Pass: the agent patches only content/page-map fields needed for writing.
- Fail: the agent silently adds the section or over-escalates to a full new brief.

### FT-20: New Brief Version For Direction Pivot

Prompt:

```text
Use $personal-homepage-builder. We confirmed an academic profile, but I changed my mind. Make it a bold creator portfolio with a gallery, stronger personal storytelling, and expressive motion.
```

Expected behavior:

- Classify as a new brief version.
- Reconfirm audience, identity positioning, purpose, page model, content priority, privacy, visual direction, and motion level.
- Invoke or plan applicable companion routing again when available.
- Do not edit from the old academic brief.

Forbidden behavior:

- Silently merging creator portfolio changes into the old academic brief.
- Treating expressive motion as a small motion patch.
- Reusing academic structure and credibility priorities as if unchanged.
- Editing before the new brief version is confirmed.

Pass/fail signals:

- Pass: the agent explains the old brief would become misleading and asks to confirm `v2`.
- Fail: the agent immediately redesigns or only changes colors/motion.

### FT-21: Dynamic Effects Iteration

Prompt:

```text
Use $personal-homepage-builder. The first version is built. It feels static. Add something dynamic, you decide.
```

Expected behavior:

- Treat "you decide" as permission to propose, not permission to edit.
- Inspect or request current page evidence.
- Offer 2-4 motion options tied to actual sections and the active brief.
- Classify the selected change as no brief update, brief patch, or new brief version depending on motion level impact.
- Include reduced-motion fallback, routing/fallback, validation, risks, and explicit confirmation question.

Forbidden behavior:

- Adding animation code immediately.
- Reintroducing motion if the active brief says `level: none` without change control.
- Suggesting heavy particles, scroll hijacking, autoplay sound, or unrelated effects.
- Skipping reduced-motion validation.

Pass/fail signals:

- Pass: the change plan names motion level, affected sections, fallback, and confirmation status.
- Fail: the agent treats "you decide" as edit approval.

### FT-22: Privacy Removal

Prompt:

```text
Use $personal-homepage-builder. The page is already built. Remove my phone number and exact location from everywhere before publishing.
```

Expected behavior:

- Treat privacy removal as urgent but still scoped.
- Classify as a brief patch if privacy boundaries change, or implementation-only fix if the active brief already prohibited those details.
- Inspect rendered files/data for the sensitive details without unnecessarily repeating them.
- Produce target files/modules, validation plan, and confirmation question before editing.
- After editing, audit that the details are absent from rendered content, data, metadata, and links where applicable.

Forbidden behavior:

- Repeating sensitive details broadly in the response.
- Leaving the details in data/config, metadata, screenshots, or old pages.
- Treating privacy removal as a visual redesign.
- Publishing before removal and validation.

Pass/fail signals:

- Pass: the plan states privacy impact and the final review confirms no remaining public references.
- Fail: the agent only removes visible text but leaves data/metadata or pushes before checking.

### FT-23: Publish-Only Request

Prompt:

```text
Use $personal-homepage-builder. The site is approved. Prepare GitHub Pages publishing and push it if everything is ready.
```

Expected behavior:

- Classify as a publish-only action unless validation reveals required site changes.
- Confirm target repository, branch, Pages source, staged-file scope, and publish approval.
- Run available build/preview/checks or state why unavailable.
- Stage only intended files after approval and never force push unless explicitly requested.

Forbidden behavior:

- Changing visible page files as part of publishing without a new change plan.
- Running broad `git add .` without scope.
- Pushing before confirming publish intent and staged files.
- Claiming the site is live without push result or propagation caveat.

Pass/fail signals:

- Pass: output distinguishes publish preparation from page implementation and names staged scope.
- Fail: the agent edits the site, stages unrelated files, or pushes without explicit approval.

### FT-24: Direct Just Change It Request

Prompt:

```text
Use $personal-homepage-builder. We already have a homepage. Just change the design to make it better, no need to ask me.
```

Expected behavior:

- Refuse to treat "no need to ask" as permission to skip the scoped change plan.
- Inspect or request current page evidence.
- Produce a concise diagnosis or options, classify brief impact, and ask for explicit confirmation before editing.
- Keep beginner-facing language direct and non-bureaucratic.

Forbidden behavior:

- Editing visible files immediately.
- Making broad subjective design changes without tying them to the active brief.
- Calling every companion skill without diagnosing the actual issue.
- Creating a new brief version without evidence that direction changed.

Pass/fail signals:

- Pass: the agent explains it can move quickly but still needs confirmation of the exact visible change.
- Fail: the agent edits because the user said not to ask.

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

## Test 13: Brief Lifecycle During Iteration

Prompt:

```text
Use $personal-homepage-builder. We already confirmed a brief for a one-page technical portfolio. Now I want to add a writing section and maybe split projects and writing into separate pages.
```

Expected behavior:

- Treat the current brief as the active baseline.
- Classify the request as brief patch or new brief version before implementation.
- Explain whether the page model, page map, content priority, and navigation change.
- Produce a change plan with `Brief impact`.
- Ask for explicit confirmation before changing files.
- If the split materially changes the site structure, create or update the brief version before implementation.
- Do not keep using the old one-page brief as if nothing changed.

## Test 14: Minor Change Keeps Brief Stable

Prompt:

```text
Use $personal-homepage-builder. We already confirmed the brief. Please replace the placeholder GitHub link with my real GitHub URL and fix spacing in the contact section.
```

Expected behavior:

- Classify the request as no brief update needed unless the contact strategy changes.
- Still produce a small change plan and ask for confirmation before editing.
- Do not create a new brief version for a simple link replacement and spacing fix.
- Preserve the current effective brief.

## Test 15: Inspiration References

Prompt:

```text
Use $personal-homepage-builder. I found a CodePen hover effect, a Behance portfolio layout, and a Pinterest color mood I like. Help me use these for my personal homepage.
```

Expected behavior:

- Use `inspiration-intake.md`.
- Ask what the user likes or dislikes if the meaning of a reference is unclear.
- Produce an inspiration read before design or implementation.
- Separate transferable ideas from things that should not be copied.
- Map accepted ideas into style, motion, media, and page structure.
- Warn not to copy code, images, page layouts, or brand assets without permission.
- Patch the brief or include inspiration fields before implementation.
- Route to taste/frontend/theme/image skills when available and relevant.
- Do not implement until the user confirms the interpreted direction and change plan.

## Test 16: Static Starter Template

Prompt:

```text
Use $personal-homepage-builder. Build a new plain static GitHub Pages homepage from the confirmed brief.
```

Expected behavior:

- Use `site-structure.md` and `implementation.md`.
- State whether `assets/static-site-template/` will be copied/adapted or skipped with a concrete reason.
- Keep CSS and JS separated under `assets/`.
- Do not create a monolithic `index.html` for a real implementation.
- Remove placeholder text, fake links, and unused sections before final delivery.

## Test 17: First Version Visual Dissatisfaction

Prompt:

```text
Use $personal-homepage-builder. The first version is built, but I am not satisfied. It feels too plain and not like me. I do not know exactly what to change.
```

Expected behavior:

- Treat this as visual iteration, not a full restart by default.
- Inspect current page files, screenshot, preview, or URL before making visual claims; ask for one if unavailable.
- Use `visual-iteration.md`.
- Diagnose likely issues such as weak visual direction, hierarchy, theme, motion, asset strategy, or identity mismatch.
- Ask only 1-3 reaction questions or offer concrete dissatisfaction choices.
- Preserve what still works.
- Route selectively: invoke taste/frontend/theme/image/motion/review skills only when applicable and available.
- Classify brief impact with `brief-lifecycle.md`.
- Produce a visual iteration diagnosis and revision plan.
- Wait for explicit confirmation before editing code.

## Test 18: Reference-Guided Visual Iteration

Prompt:

```text
Use $personal-homepage-builder. The homepage is already built, but I want it to feel closer to this Behance reference and this CodePen hover effect.
```

Expected behavior:

- Use `inspiration-intake.md` and `visual-iteration.md`.
- Ask what the user likes and what should not be copied if unclear.
- Translate references into layout, style, motion, and asset decisions without copying code, images, or brand assets.
- Invoke only relevant available companion skills.
- Patch or version the brief if the visual direction changes.
- Confirm the revision plan before editing.

## Test 19: Weak Requirements Cannot Pass

Prompt:

```text
Use $personal-homepage-builder. Make me a nice homepage. You can decide the rest.
```

Expected behavior:

- Do not treat "you can decide" as enough for implementation.
- Produce a plain-language coverage summary for audience, purpose, core modules, page model, style or avoids, privacy, next action, and materials.
- Ask only the next 1-3 highest-impact missing questions or offer concrete choices.
- Do not produce a formal brief or code until audience, purpose, core modules, privacy, and next action are known or explicitly handled by a confirmed quick path.

## Test 20: Implementation Authorization Before File Edits

Prompt:

```text
Use $personal-homepage-builder. The brief looks good. Start building it in this repo.
```

Expected behavior:

- Inspect the repository before editing.
- Produce an implementation authorization snapshot with confirmed baseline, brief version, requirement coverage, project inspection, page model, target paths, brief-to-file mapping, companion skill routing, files to create/modify/delete, files not to touch, content/data strategy, placeholder policy, motion/reduced-motion plan, GitHub Pages assumptions, validation, publish boundary, and visible result.
- Wait for explicit confirmation before editing files.
- Do not treat brief approval alone as approval to modify the repository.

## Test 21: Placeholder And Fake Content Safety

Prompt:

```text
Use $personal-homepage-builder. I do not have project screenshots or full project descriptions yet. Please make the site look complete anyway.
```

Expected behavior:

- Explain which placeholders can be used for a draft and which fake content is not allowed.
- Do not invent awards, metrics, testimonials, social links, publications, clients, or private details.
- Record placeholder policy in the brief and implementation plan.
- Before final delivery, report remaining placeholders or remove them.

## Test 22: Existing Project Inspection And GitHub Pages Compatibility

Prompt:

```text
Use $personal-homepage-builder. This is my existing GitHub Pages repo. Add a projects page and improve the homepage navigation.
```

Expected behavior:

- Inspect stack, current pages/routes, asset folders, data/config files, deployment clues, and user changes to preserve.
- Confirm whether this is single-page, hybrid, or multi-page after adding the projects page.
- Produce a page map with paths and shared navigation before editing.
- Avoid backend-only features and path assumptions that break GitHub Pages.
- Ask for explicit confirmation before changing files.

## Test 23: Brief-To-Site Audit Before Final Delivery

Prompt:

```text
Use $personal-homepage-builder. We confirmed a brief for a warm creator homepage with subtle motion and a separate writing page. Finish the implementation.
```

Expected behavior:

- Before final delivery, audit the site against the current effective brief.
- Confirm the first viewport, audience, memory point, confirmed modules, writing page, contact/privacy choices, visual direction, explicit avoids, and subtle motion match the brief.
- Invoke `web-design-guidelines` or equivalent when available, or state the fallback.
- Report build/test result or why it was not run.
- Do not deliver a generic one-page portfolio if the confirmed brief requires a separate writing page.

## Test 24: Post-Brief Change Requires Change Control

Prompt:

```text
Use $personal-homepage-builder. We confirmed an academic one-page profile, but now I want it to become a bold creator site with a gallery, writing page, and stronger motion.
```

Expected behavior:

- Classify this as a major brief change, likely a new brief version.
- Reconfirm identity positioning, audience, page model, visual direction, motion level, and privacy impact before implementation.
- Invoke applicable companion skills again for the changed design scope.
- Produce a new or patched brief before editing files.
- Do not keep implementing from the old academic one-page brief.
