# Beginner Validation Scenario

Use this document to forward-test whether `personal-homepage-builder` can guide a beginner from almost no prepared information to a confirmed homepage brief and implementation plan.

This is a zero-prep interaction test. The user should not provide a resume, full profile, style preference, links, or project details until the agent asks for them.

## Test Goal

Validate the full loop:

```text
minimal first user request
-> agent asks only the next useful questions
-> user answers only what was asked
-> agent summarizes confirmed and inferred needs
-> agent translates personal signals into style and structure
-> agent produces a homepage brief
-> user confirms or corrects it
-> agent routes companion skills and plans implementation
```

The agent passes only if it helps the user clarify needs before implementation and does not jump directly into code.

## How To Run This Test

Give the tested agent only Turn 1 at first. Do not paste the hidden user notes or later answers upfront.

The tester should play the user and reveal information gradually. If the agent asks a good question, answer it using the next matching user response. If the agent asks too many questions, answer only the most important ones. If the agent asks for style too early, give a vague answer and see whether it can recover.

## User Behavior Rules

The user should behave like a real beginner:

- Start with only a desire to make a personal homepage.
- Do not know design terms.
- Do not know what structure the homepage should use.
- Do not know which motion effects are appropriate.
- Provide information only after the agent asks.
- Give short, imperfect answers.
- Say "I am not sure" when unsure.
- Correct the agent when a summary feels too resume-like, too corporate, too flashy, or too generic.

## Information The Agent Should Eventually Discover

The agent should not demand every field at once, but a complete run should eventually cover these items.

| Area | What the agent should discover | Why it matters |
| --- | --- | --- |
| Identity | Public name, one-line self-description, roles, communities | Defines who the homepage represents |
| Audience | Recruiters, collaborators, clients, readers, peers, friends | Determines tone, content order, and proof level |
| Memory point | What visitors should remember after 10-30 seconds | Prevents a generic resume layout |
| Content | Projects, papers, services, writing, photos, videos, social links | Defines sections and homepage structure |
| Proof | Links, screenshots, demos, publications, metrics, testimonials | Supports credibility without exaggeration |
| Privacy | Details to avoid, outdated facts, sensitive materials | Prevents accidental public exposure |
| Taste clues | Sites, apps, colors, objects, music, films, moods, dislikes | Helps translate personal language into design direction |
| Media | Avatar, portraits, covers, screenshots, video, music references | Determines whether to use media-enhanced layout |
| Motion | none, subtle, moderate, expressive, or not sure | Controls dynamic elements and accessibility handling |
| Language | English, Chinese, bilingual, or another setup | Controls copy and metadata |
| Constraints | Timeline, hosting, stack, GitHub username, repo status | Controls implementation and publishing plan |

## Hidden User Seed

Use this only to answer agent questions during the test. Do not give it to the agent upfront.

```yaml
hidden_user_seed:
  display_name: "Lin Chen"
  identity: "computer science student who builds small AI tools and web experiments"
  audience: "future collaborators, internship recruiters, and technical peers"
  memory_point: "turns AI ideas into usable prototypes"
  must_show:
    - GitHub
    - two AI projects
    - short intro
    - LinkedIn
    - one blog post
  projects:
    - name: "PromptBoard"
      description: "a small prompt library for AI workflows"
      link_status: "placeholder for now"
    - name: "StudyLens"
      description: "a web tool that summarizes study notes"
      link_status: "placeholder for now"
  missing:
    - polished resume
    - professional photos
    - final project links
  privacy:
    - do not publish phone number
    - do not publish home location
    - do not show unfinished class projects
    - do not overstate project impact
  taste:
    - quiet
    - technical
    - slightly personal
    - clean dark interfaces
    - magazine-like typography
    - calm motion
  dislikes:
    - neon cyberpunk
    - generic portfolio cards
    - startup landing page vibes
    - emoji
  language: "English first"
  desired_correction: "less like a resume, more like a small builder profile; professional but not corporate"
```

## First-Person Interaction Script

### Turn 1: User Starts With Almost Nothing

User:

```text
Use $personal-homepage-builder. I want to build a personal github.io homepage, but I am a beginner and do not know what information, style, structure, or effects I need. Please guide me from scratch.
```

Expected agent behavior:

- Activate `personal-homepage-builder`.
- Set inferred default: `Deep Profile`, `Profile`, `subtle` motion.
- Explain that the process will happen in short discovery rounds before code.
- Mention that useful materials can be prepared later, such as links, projects, photos, social accounts, and style references.
- Do not ask "what style do you want?"
- Ask 1-3 easy, grounded questions.
- Do not ask for all materials at once.

Good agent response shape:

```text
I will treat this as Deep Profile + Profile quality for now: enough discovery to make it personal without turning it into a large custom site.

To start, answer these roughly:
1. Who are you in one or two sentences?
2. Who should this homepage mainly help?
3. What should visitors remember about you after 10 seconds?
```

### Turn 2: User Answers Only The First Questions

User:

```text
I am Lin Chen, a computer science student. I build small AI tools and web experiments. I think the homepage should help future collaborators, internship recruiters, and technical peers understand what I can build. I want them to remember that I turn AI ideas into usable prototypes.
```

Expected agent behavior:

- Store identity, audience, memory point.
- Ask for content and privacy next, not visual style yet.
- Keep questions limited.

Good next questions:

```text
That gives me the core positioning. Next I need content and boundaries:
1. What are the 3 things that must appear on the homepage?
2. Which links or platforms should be included?
3. What should not be public?
```

### Turn 3: User Provides Only Content And Boundaries

User:

```text
Must show my GitHub, two AI projects, and a short intro. I also have a LinkedIn profile and one blog post. I do not want my phone number, home location, or unfinished class projects shown. I also do not want the page to exaggerate what my projects did.
```

Expected agent behavior:

- Extract materials and privacy constraints.
- Notice missing project names and links.
- Ask for project details or taste, depending on what is most useful next.

Good next questions:

```text
Good. I will keep the page honest and avoid private details. Next:
1. What are the two project names, and how would you describe each in one sentence?
2. Do you already have links for GitHub, LinkedIn, the blog post, or should I mark them as placeholders?
3. Do you have any photos or should the first version be typography-first?
```

### Turn 4: User Gives Project Details

User:

```text
Project 1 is PromptBoard, a small prompt library for AI workflows. Project 2 is StudyLens, a web tool that summarizes study notes. I can provide the GitHub links later, so use placeholders for now. I do not have good photos yet, so typography-first is better.
```

Expected agent behavior:

- Store placeholders clearly.
- Do not invent links.
- Ask taste questions in plain language.

Good next questions:

```text
Now I have enough content for a first structure. For taste, answer in ordinary words:
1. Should the page feel more quiet and credible, sharp and technical, warm and personal, or expressive and creative?
2. Are there any websites, apps, colors, objects, music, books, films, or places you like or dislike?
3. Should motion be none, subtle, moderate, expressive, or are you not sure?
```

### Turn 5: User Gives Vague Taste Clues

User:

```text
I want it to feel quiet, technical, and a little personal. I like clean dark interfaces, magazine-like typography, and calm motion. I do not want neon cyberpunk, generic portfolio cards, startup landing page vibes, or emoji. I am not sure about motion, but subtle sounds right.
```

Expected agent behavior:

- Translate taste clues into a style direction.
- Produce an identity reflection before full implementation.
- Label confirmed facts and inferred design direction separately.

Good reflection shape:

```text
Current understanding:
- Delivery mode: Deep Profile
- Quality tier: Profile
- Motion level: subtle
- Confirmed identity: computer science student building AI tools and web experiments
- Audience: collaborators, internship recruiters, technical peers
- Memory point: turns AI ideas into usable prototypes
- Must show: GitHub, PromptBoard, StudyLens, LinkedIn, one blog post, short intro
- Must avoid: phone, home location, unfinished class projects, overstated claims, emoji
- Taste clues: quiet technical, clean dark interface, editorial typography, calm motion

Inferred design direction:
- Quiet Technical Editorial
- Structured hero, selected projects, writing link, compact social/contact section
- Subtle entrance and hover/focus motion only

Open question:
Should the homepage be English only, Chinese only, or bilingual?
```

### Turn 6: User Answers The Remaining Question

User:

```text
English first. Maybe bilingual later, but not for the first version.
```

Expected agent behavior:

- Produce a compact `personal_homepage_brief`.
- Include placeholders clearly.
- Do not implement until user confirms or corrects the brief.

Expected brief contents:

```yaml
personal_homepage_brief:
  implementation:
    delivery_mode: Deep Profile
    quality_tier: Profile
  identity:
    primary_role: "computer science student and AI tool builder"
    confirmed_facts:
      - "Builds small AI tools and web experiments"
      - "Wants to show GitHub, PromptBoard, StudyLens, LinkedIn, one blog post, and a short intro"
    inferred_positioning: "Turns AI ideas into usable prototypes"
  audience:
    primary: "future collaborators and internship recruiters"
    secondary: "technical peers"
  goal:
    first_impression: "quiet, technical, credible, slightly personal"
    remembered_for: "building practical AI prototypes"
  privacy:
    needs_avoidance:
      - "phone number"
      - "home location"
      - "unfinished class projects"
      - "overstated claims"
  content:
    required_sections:
      - "intro"
      - "selected AI projects"
      - "writing"
      - "links/contact"
    social_links:
      - "GitHub placeholder"
      - "LinkedIn placeholder"
  style:
    direction_name: "Quiet Technical Editorial"
    tone_keywords:
      - "quiet"
      - "technical"
      - "editorial"
      - "credible"
    typography_notes: "strong readable hierarchy with editorial influence"
    image_strategy: "typography-first until good photos are available"
  motion_strategy:
    level: "subtle"
    entrance: "small hero text fade/rise"
    scroll_reveal: "gentle section reveal only if it improves pacing"
    hover_feedback: "project cards and links get clear hover/focus states"
    reduced_motion: "disable reveal animations and keep instant feedback"
    avoid:
      - "neon cyberpunk effects"
      - "heavy particles"
      - "scroll hijacking"
  companion_skill_routing:
    taste: "design-taste-frontend or fallback"
    theme: "theme-factory or fallback"
    frontend: "frontend-design or fallback"
    media: "not needed unless visual assets are generated"
    review: "web-design-guidelines or fallback"
```

### Turn 7: User Corrects The Brief

User:

```text
This is mostly right. Make it less like a resume and more like a small builder profile. I still want it professional, but not corporate.
```

Expected agent behavior:

- Update the brief.
- Explain the change in content hierarchy and style.
- Ask for approval to implement or present the implementation plan.

Good response shape:

```text
I will adjust the brief from resume-like to builder profile:
- Hero emphasizes practical AI prototypes, not education first.
- Projects come before resume-style details.
- Writing appears as a thinking/progress signal.
- Contact remains compact and professional.

Next gate: implementation plan. I will not edit code until this direction is accepted.
```

### Turn 8: User Approves Implementation

User:

```text
Accepted. Please build the first version as a static GitHub Pages homepage.
```

Expected agent behavior:

- Declare design routing.
- Use companion skills when available.
- Produce an implementation plan.
- Use structured files, not a single large HTML file.

Good implementation plan:

```text
Design routing:
- Taste: design-taste-frontend or fallback
- Theme: theme-factory or fallback
- Frontend/UI: frontend-design or fallback
- Media: not needed for v1
- Motion: subtle
- Review: web-design-guidelines or fallback

Implementation plan:
- Create index.html
- Create assets/css/base.css, assets/css/components.css, assets/css/animations.css, assets/css/home.css
- Create assets/js/main.js and assets/js/interactions.js if motion needs JavaScript
- Add placeholder project links clearly
- Validate responsive layout, text fit, keyboard focus, reduced motion, and local static preview
```

## Pass Criteria

The agent passes this scenario if it:

- Uses `personal-homepage-builder` as the controlling workflow.
- Defaults to `Deep Profile`, `Profile`, and `subtle` motion for the unsure beginner.
- Asks grounded personal and content questions before visual style questions.
- Reveals the process step by step instead of demanding all information upfront.
- Gives a materials roadmap and tells the user what to prepare next.
- Avoids asking the user to manually choose quality tiers.
- Extracts privacy constraints before implementation.
- Translates vague taste into a named style direction and concrete implementation notes.
- Produces a structured `personal_homepage_brief`.
- Waits for user confirmation before coding.
- Routes companion skills before UI implementation.
- Uses structured static site files for GitHub Pages.
- Avoids emoji by default.

## Failure Modes

The agent fails this scenario if it:

- Immediately writes HTML without a brief.
- Starts by asking only "what style do you want?"
- Asks the beginner to provide a complete brand/design brief upfront.
- Ends discovery after three or four short turns without covering materials, privacy, taste, constraints, and placeholders.
- Ignores privacy boundaries.
- Treats placeholders as real links.
- Adds flashy motion despite the subtle preference.
- Creates one large monolithic HTML file for a real site.
- Claims companion skills were used when they were not available or invoked.
- Pushes or publishes without explicit approval.

## Compact Test Prompt

Use this prompt when launching a fresh validation run:

```text
Use $personal-homepage-builder. I want to build a personal github.io homepage from scratch. I am a beginner and I do not know what information, style, structure, or effects I need. Please guide me step by step, ask me only what you need next, and do not write code until we have a confirmed homepage brief.
```
