# Homepage Brief

Use this schema for `personal_homepage_brief`. Keep it compact for quick work and expand it for deep design work.

## Required Schema

```yaml
personal_homepage_brief:
  requirements_status:
    minimum_viable_requirements: incomplete | ready | confirmed
    confirmed_at:
    missing_or_deferred:
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
  functional_requirements:
    must_have:
    nice_to_have:
    explicitly_out_of_scope:
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
    content_model:
      project_or_work_item:
      writing_or_publication_item:
      link_item:
      media_item:
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
    language:
    external_resources:
    placeholders_allowed:
    assumptions:
    emoji_policy: no emoji unless explicitly requested
    must_keep:
    must_avoid:
  non_functional_requirements:
    responsive:
    accessibility:
    seo:
    performance:
    maintainability:
    reduced_motion:
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
  change_control:
    baseline_summary:
    requires_reconfirmation_if_changed:
```

## Minimal Quick Brief

For speed-focused work, the brief may be short but still needs these fields:

- identity
- audience
- main purpose
- first impression
- remembered-for
- at least three required sections or content modules
- public/private boundaries
- style direction
- motion strategy
- privacy avoids
- material status
- functional must-haves
- practical constraints
- companion skill routing
- validation plan

## Confirmation Prompt

Before implementation, ask:

```text
Does this brief accurately describe how the homepage should represent you? Correct anything that feels off before I turn it into UI and code.
```

For beginner users, phrase the confirmation in plain language:

```text
This is the plan I would build from. Please check whether it feels like you and whether anything private, exaggerated, missing, or wrongly prioritized needs to change before I start implementation.
```
