# Beginner Conversation Patterns

Use this file when the user is not a designer, developer, product manager, or experienced personal-site owner. The goal is to translate vague personal intuition into internal requirements without making the user feel like they are filling a technical form.

## Core Principle

Keep internal gates strict and user-facing conversation light.

Internally maintain minimum viable requirements, brief fields, taste hypotheses, motion level, and implementation constraints. Externally ask concrete, human questions and provide choices the user can react to.

Do not expose terms such as `delivery_mode`, `quality_tier`, `motion_strategy`, `personal_homepage_brief`, `MVR`, `schema`, or `output gate` unless the user asks for technical detail.

## First Reply For Vague Starts

Use this when the user says something like "I want a good-looking personal homepage" or "I have no idea yet."

```text
We can start without a full plan. I will first help you figure out what this homepage should make people understand about you, then we can turn that into a page plan, and only after you confirm it will we write code.

You do not need to prepare everything now. Later, useful materials may include links, projects, photos, screenshots, writing, social accounts, or examples of sites you like.

First, choose whichever is closest:
1. I want it to feel like a professional online name card.
2. I want it to feel like a portfolio of my work.
3. I want it to feel like a more personal self-introduction.

And in one rough sentence: who are you, or what do you want people to know about you first?
```

Ask no more than three questions in the first reply.

## Choice-Driven Prompts

Use choices to trigger reaction. The user may answer with a number, a mix, or "none of these."

### Purpose

```text
Which purpose is closest?
1. Make recruiters or collaborators trust me quickly.
2. Show my projects, writing, research, or creations.
3. Let people understand my personality and story.
4. Give people a simple place to find my links and contact me.
```

### Audience

```text
Who is most likely to open this page first?
1. Recruiters, interviewers, or clients.
2. Collaborators, peers, or open-source users.
3. Readers, fans, students, or community members.
4. Friends or people who already know me.
```

### Content Priority

```text
If the first screen can only make three things obvious, which three should they be?
1. Who I am.
2. What I have built or created.
3. What I am good at.
4. What I am currently exploring.
5. How to contact or follow me.
6. My story, taste, or personal side.
```

### Page Shape

```text
How should the content be organized?
1. One scrollable page: best if the page should feel simple and focused.
2. A homepage plus a few detail pages: best if projects, writing, or research need more room.
3. A small personal site with separate pages: best if you have many works, articles, publications, services, or media.
4. I am not sure; suggest the smallest structure that fits my content.
```

### Taste Direction

```text
Which direction feels closer?
1. Clean, calm, professional.
2. Technical, precise, slightly futuristic.
3. Warm, personal, story-driven.
4. Bold, visual, portfolio-like.
5. Minimal, quiet, typography-first.
```

Use this only after the agent has at least some identity, audience, content, or memory-point signal. Do not make taste the first design question.

If the user cannot describe visual style, ask about concrete reactions instead:

```text
Which version would feel less wrong for you?
1. A calm page that makes people trust you quickly.
2. A sharper page that makes your work feel technical and precise.
3. A warmer page that shows more story and personality.
4. A more visual page that puts projects, images, or media first.

Also, choose anything to avoid: too corporate, too flashy, too cute, too dark, too much like a resume, too generic.
```

### Motion

```text
How much movement should the page have?
1. Almost none, just clean and stable.
2. Subtle feedback, such as gentle hover and scroll reveal.
3. Noticeable but still controlled motion.
4. More expressive motion that becomes part of the personality.
5. I am not sure; decide based on the page content.
```

### Dislikes

```text
Which should we avoid?
1. Too corporate.
2. Too flashy.
3. Too cute or playful.
4. Too dark and heavy.
5. Too much like a resume.
6. Too much like a generic portfolio template.
```

## Probe Artifacts

Use a probe artifact when the user has provided some signals but still cannot describe preferences. A probe artifact is not implementation and must not contain final code.

Allowed probe artifacts:

- **Direction cards**: 2-3 possible page directions with plain-language names.
- **Text wireframe**: a rough section order using simple labels.
- **Page map**: a rough list of pages and what each page should contain.
- **Plain vs richer contrast**: show what the page would become with only current information versus what could improve it.
- **Content gap map**: show which missing material would make the page more personal.

### Direction Card Template

```text
Based on what you said, I see three possible directions:

1. Professional Signal
   Best for: trust, clarity, recruiters/collaborators.
   Page focus: intro, selected work, proof, contact.
   Risk: may feel too close to a resume if we do not add personal details.

2. Builder Portfolio
   Best for: projects, demos, open-source, product thinking.
   Page focus: hero, project cards, writing/notes, GitHub links.
   Risk: needs enough project material or good placeholders.

3. Personal Editorial
   Best for: story, taste, writing, life/work blend.
   Page focus: short narrative, selected work, photos or taste references.
   Risk: can feel vague if there is no clear visitor action.

Which one feels closest, or should we combine two of them?
```

### Text Wireframe Template

```text
A rough structure could be:

1. First screen: name, one-line identity, main link/contact.
2. About: short self-introduction written for the target visitor.
3. Selected work: 3-6 projects, writings, papers, services, or creations.
4. Proof or context: GitHub, screenshots, metrics, testimonials, publications, or timeline.
5. Personal signal: one small section that shows taste, values, interests, or current focus.
6. Contact and links: clear next action.

This is only a sketch. Tell me what feels wrong or missing.
```

### Page Map Template

```text
The site could stay as one page, but if we split it slightly, I would suggest:

1. Home
   Purpose: quick first impression and strongest links.
   Includes: intro, selected highlights, contact.

2. Projects
   Purpose: give each project enough space.
   Includes: project cards, links, screenshots, short notes.

3. Writing / Notes
   Purpose: collect articles, posts, papers, or learning notes.
   Includes: title, date, topic, link, short summary.

This is only a page map. We should confirm whether these pages are actually needed before implementation.
```

### Plain Vs Richer Contrast

```text
With only the information we have now, the page would be a clean but basic profile:
- name and one-line intro
- a few links
- generic project/contact sections

To make it feel more like you, the highest-impact next material would be:
- one or two projects or stories you are proud of
- a photo, avatar, screenshot, or decision to stay typography-first
- one visual reference you like and one style you dislike

Which of these can you provide next?
```

## Silent Mapping Rules

Convert user answers into internal fields without showing the field names.

| User says | Internally update |
| --- | --- |
| "I want recruiters to understand me quickly" | audience.primary, goal.conversion_or_next_action, content priority |
| "I want it to feel like my work, not a resume" | anti_template_constraints, style direction, content mix |
| "I like calm pages, not too much animation" | taste.likes, taste.dislikes, motion_strategy.level=subtle |
| "I only have GitHub and two projects" | source_materials, placeholders, materials_to_prepare |
| "Do not show my phone or school details" | privacy.needs_avoidance |
| "I want Chinese and English" | functional requirements, content model, implementation constraints |
| "My projects and writing need their own space" | information_architecture.page_model=hybrid or multi_page |
| "Keep it simple; one page is enough" | information_architecture.page_model=single_page |

## Scattered Answer Handling

When the user gives a messy paragraph with mixed biography, links, taste, and private details, do not ask them to reorganize it. Sort it for them and ask only for the next missing decision.

Use this response shape:

```text
I can work with this. I sorted it into:
- Public facts I think are safe:
- Things that sound useful but need confirmation:
- Private or sensitive details I will not publish unless you explicitly approve:
- Possible homepage sections:
- Taste clues:
- Missing materials or placeholders:

The next useful question is:
1.
```

Do not include sensitive details verbatim if repeating them would expose unnecessary private information. Summarize them as "private contact detail", "specific location", "unpublished project", or "sensitive personal context" when possible.

## User-Friendly Term Replacements

| Internal term | User-facing language |
| --- | --- |
| audience | who should open this page |
| conversion | what visitors should do next |
| content model | what each section needs to show |
| information architecture | how many pages the site needs and what each page contains |
| motion strategy | how much movement the page should have |
| non-functional requirements | practical quality expectations |
| constraints | things we need to work around |
| requirements baseline | the version of the plan we are about to build from |

## Good Interaction Examples

### Good: Choice Instead Of Form

```text
Which feels closer: a reliable online name card, a work portfolio, or a personal story page?
```

### Good: Reaction Probe

```text
Here are two possible directions. The first is safer and more professional; the second is more personal and visual. Which one feels less wrong?
```

### Good: Gentle Material Guidance

```text
You do not need photos now. If you have no image assets, I can design a typography-first page and leave image slots optional.
```

## Bad Interaction Examples

Avoid:

```text
Please provide your target audience, functional requirements, non-functional requirements, content model, motion strategy, and deployment constraints.
```

Avoid:

```text
I will now generate the HTML, CSS, and JavaScript.
```

Avoid:

```text
You selected delivery_mode=Deep Profile and quality_tier=Profile.
```

Avoid:

```text
I cannot continue until you provide a complete PRD.
```

## When The User Asks For Code Early

Keep momentum but do not skip understanding. Say briefly:

```text
I can build it after we confirm the direction. To avoid creating a generic page, I need the smallest version of the plan first: who should see it, what they should remember, at least three things to show, and anything private to avoid.
```

Then ask only the missing items.
