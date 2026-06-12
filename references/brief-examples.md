# Brief Examples

Use these examples to calibrate the quality of homepage briefs. Do not copy names, claims, links, or content into a user's project.

## Good Brief: Zero-Prep Builder Portfolio

Use when the user starts with little material but wants a credible personal homepage.

```yaml
personal_homepage_brief:
  brief_meta:
    version: v1
    status: draft
    current_effective: true
  requirements_status:
    minimum_viable_requirements: ready
    missing_or_deferred:
      - final avatar
      - complete project screenshots
  identity:
    primary_role: "AI tool builder"
    confirmed_facts:
      - "Has GitHub and two early projects"
      - "Wants a personal github.io homepage"
    inferred_positioning: "Practical builder who turns ideas into small usable tools"
  audience:
    primary: "collaborators, recruiters, and technical peers"
  goal:
    first_impression: "clear, capable, curious"
    remembered_for: "building useful AI experiments and documenting the process"
    conversion_or_next_action: "visit GitHub or contact for collaboration"
  content:
    source_materials:
      - GitHub profile
      - short self-introduction
      - two project links
    materials_to_prepare:
      - one project screenshot per project
      - preferred public contact link
    required_sections:
      - intro
      - selected projects
      - current focus
      - links and contact
    priority_order:
      - identity
      - strongest project
      - GitHub/contact
  information_architecture:
    page_model: single_page
    rationale: "Content is compact enough for one focused homepage."
    page_map:
      - path: "index.html"
        title: "Home"
        purpose: "Give a quick overview and route visitors to projects and contact"
        priority: high
        sections: ["hero", "selected projects", "current focus", "links"]
  taste:
    references: []
    likes: ["clean technical pages", "not too flashy"]
    dislikes: ["generic portfolio grid", "overly corporate tone"]
    design_read: "quiet technical portfolio with a personal builder signal"
    anti_template_constraints:
      - "Avoid a resume-like timeline as the main structure"
      - "Include a small personal/current-focus section"
  style:
    direction_name: "quiet technical editorial"
    tone_keywords: ["precise", "calm", "approachable"]
    image_strategy: "typography-first with optional project screenshots"
  motion_strategy:
    level: subtle
    rationale: "Motion should add polish without distracting from credibility."
    hover_feedback: "project cards and links"
    scroll_reveal: "gentle section reveal"
    reduced_motion: "show all content without reveal animation"
  constraints:
    hosting: "GitHub Pages"
    placeholders_allowed: true
    emoji_policy: "no emoji unless explicitly requested"
  companion_skill_routing:
    taste: "design-taste-frontend invoked or unavailable fallback stated"
    theme: "theme-factory invoked if theme system is needed"
    frontend: "frontend-design invoked before UI implementation"
    review: "web-design-guidelines invoked before delivery"
```

Why this is good:

- It turns vague identity into a clear first impression.
- It records missing materials without blocking progress.
- It chooses the smallest page model that fits.
- It gives design direction without pretending every detail is known.

## Good Brief: Multi-Page Personal Site

Use when the user has enough projects, writing, research, services, or media to need supporting pages.

```yaml
personal_homepage_brief:
  identity:
    primary_role: "researcher and independent builder"
    inferred_positioning: "Connects research, prototypes, and public writing"
  audience:
    primary: "research collaborators and readers"
    secondary: "recruiters and open-source users"
  goal:
    first_impression: "thoughtful, rigorous, still approachable"
    remembered_for: "making complex AI topics easier to understand and test"
    conversion_or_next_action: "read writing, inspect projects, or contact"
  content:
    required_sections:
      - intro
      - research themes
      - selected projects
      - writing
      - contact
    content_model:
      project_or_work_item:
        fields: ["title", "summary", "role", "links", "status", "tags"]
      writing_or_publication_item:
        fields: ["title", "date", "topic", "link", "short_summary"]
  information_architecture:
    page_model: hybrid
    rationale: "The homepage should stay focused while projects and writing need more room."
    page_map:
      - path: "index.html"
        title: "Home"
        purpose: "Strong first impression and best links"
        sections: ["hero", "research themes", "selected highlights", "contact"]
      - path: "projects.html"
        title: "Projects"
        purpose: "Show project details and proof"
        sections: ["project index", "project cards", "tags"]
      - path: "writing.html"
        title: "Writing"
        purpose: "Collect essays, notes, and publications"
        sections: ["writing list", "topics", "external links"]
  style:
    direction_name: "research editorial"
    tone_keywords: ["focused", "credible", "human"]
  motion_strategy:
    level: subtle
    content_specific_motion:
      - "subtle hover on project and writing cards"
      - "small active state in navigation"
```

Why this is good:

- It does not force all content into one long page.
- It defines repeated content fields before implementation.
- It keeps the homepage as a strong summary page.

## Good Brief: Reference-Informed Visual Direction

Use when the user supplies CodePen, Behance, Pinterest, Awwwards, or SiteInspire references.

```yaml
personal_homepage_brief:
  taste:
    references:
      - source: "CodePen"
        user_like: "subtle hover glow and card lift"
        transferable_idea: "project cards can have restrained hover depth"
        avoid: "do not copy the exact particle background"
      - source: "Behance"
        user_like: "editorial first screen and strong typography"
        transferable_idea: "hero can use large type, short identity, and asymmetrical spacing"
        avoid: "do not make it look like a design agency case study"
    design_read: "editorial technical homepage with restrained interaction"
    anti_template_constraints:
      - "No generic portfolio grid"
      - "No decorative animation that competes with reading"
  style:
    direction_name: "editorial technical"
    typography_notes: "larger first-screen type, compact body text, strong hierarchy"
    color_notes: "neutral base with one restrained accent"
    image_strategy: "use project screenshots or original generated texture, not copied reference images"
  motion_strategy:
    level: subtle
    hover_feedback: "card lift, link underline, focus ring"
    scroll_reveal: "short reveal for major sections only"
    avoid: ["heavy parallax", "cursor trail", "autoplay sound"]
```

Why this is good:

- It separates what the user likes from what should not be copied.
- It maps references into style, layout, motion, and asset decisions.
- It turns inspiration into a confirmable plan.

## Bad Brief: Too Vague

Avoid:

```yaml
personal_homepage_brief:
  identity:
    primary_role: "developer"
  audience:
    primary: "everyone"
  goal:
    first_impression: "cool"
  content:
    required_sections: ["about", "projects", "contact"]
  style:
    direction_name: "modern"
  motion_strategy:
    level: moderate
```

Why this fails:

- "Everyone" is not a useful audience.
- "Cool" and "modern" do not explain what the visitor should remember.
- There is no privacy boundary, material status, page model, content priority, or implementation constraint.
- Motion is chosen without rationale.

## Bad Brief: Form-Like And User-Hostile

Avoid showing this kind of prompt to beginners:

```text
Please provide all functional requirements, non-functional requirements, content model fields, information architecture, motion strategy, quality tier, and delivery mode.
```

Why this fails:

- It exposes internal engineering categories to ordinary users.
- It increases friction before the user has enough confidence to answer.
- The agent should collect these details through plain-language conversation and translate them silently.

## Bad Brief: Copying A Reference

Avoid:

```yaml
style:
  direction_name: "same as this Awwwards site"
implementation:
  instruction: "copy the layout, animation, and hero image"
```

Why this fails:

- It may copy another site's protected expression, code, images, or brand.
- It ignores whether the reference fits the user's identity and content.
- It does not produce a maintainable personal homepage direction.

