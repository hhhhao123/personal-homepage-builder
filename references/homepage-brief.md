# Homepage Brief

Use this schema for `personal_homepage_brief`. Keep it compact for quick work and expand it for deep design work.

## Required Schema

```yaml
personal_homepage_brief:
  identity:
    primary_role:
    secondary_traits:
    personal_elements:
    confirmed_facts:
    inferred_positioning:
    tentative_signals:
  audience:
    primary:
    secondary:
    visitor_tasks:
  goal:
    first_impression:
    remembered_for:
    conversion_or_next_action:
  privacy:
    public_allowed:
    needs_avoidance:
    needs_confirmation:
  content:
    source_materials:
    personal_signal_pack:
    placeholders:
    materials_to_prepare:
    priority_order:
    required_sections:
    optional_sections:
    social_links:
    media_assets:
  taste:
    references:
    likes:
    dislikes:
    design_read:
    anti_template_constraints:
  style:
    direction_name:
    tone_keywords:
    color_notes:
    typography_notes:
    image_strategy:
  motion_strategy:
    level: none | subtle | moderate | expressive
    rationale:
    entrance:
    scroll_reveal:
    hover_feedback:
    state_feedback:
    content_specific_motion:
    reduced_motion:
    avoid:
  constraints:
    stack:
    hosting: GitHub Pages by default
    timeline:
    emoji_policy: no emoji unless explicitly requested
    must_keep:
    must_avoid:
  companion_skill_routing:
    taste:
    theme:
    frontend:
    media:
    review:
  implementation:
    delivery_mode: Quick Launch | Deep Profile | Media Enhanced | Publish
    quality_tier: Basic | Profile | Creator | Academic | Premium
    site_structure:
    pages:
    assets:
    validation:
```

## Minimal Quick Brief

For speed-focused work, the brief may be short but still needs these fields:

- identity
- audience
- first impression
- remembered-for
- required sections
- style direction
- motion strategy
- privacy avoids
- companion skill routing
- validation plan

## Confirmation Prompt

Before implementation, ask:

```text
Does this brief accurately describe how the homepage should represent you? Correct anything that feels off before I turn it into UI and code.
```
