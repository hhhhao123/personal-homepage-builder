# Homepage Brief

Use this schema for `personal_homepage_brief`. Keep it compact for quick work and expand it for deep design work.

## Required Schema

```yaml
personal_homepage_brief:
  brief_meta:
    version: v1
    status: draft | confirmed | patched | superseded
    created_at:
    confirmed_at:
    last_updated_at:
    supersedes:
    current_effective: true | false
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
  inspiration:
    provided_references:
      - source:
        url_or_description:
        reference_type: dynamic_effect | page_layout | mood_board | hero_image | typography | portfolio_structure | media_treatment
        user_like:
        user_dislike:
        transferable_idea:
        should_not_copy:
        fit_for_homepage:
        risk:
    accepted_ideas:
    rejected_ideas:
    asset_license_notes:
    confirmation_status: unconfirmed | confirmed | rejected | partially_confirmed
  information_architecture:
    page_model: single_page | hybrid | multi_page
    rationale:
    page_map:
      - path:
        title:
        purpose:
        priority:
        sections:
        source_content:
        missing_content:
    navigation:
      primary_links:
      footer_links:
      mobile_behavior:
      active_state:
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
    lifecycle_decision: initial_brief | no_brief_update | brief_patch | new_brief_version
    latest_change_plan:
    changed_fields:
    change_history:
      - version:
        date:
        classification: no_brief_update | brief_patch | new_brief_version
        summary:
        confirmed_by_user: true | false
    requires_reconfirmation_if_changed:
```

## Lifecycle Rule

Use `brief-lifecycle.md` after a brief has been confirmed.

- Keep one current effective brief.
- Use a change plan for every visible adjustment.
- Patch the current brief when a confirmed change affects its fields but preserves the same direction.
- Create a new brief version when audience, purpose, identity positioning, page model, major content priority, privacy boundary, or design direction changes.
- Do not implement from a stale brief.

## Minimal Quick Brief

For speed-focused work, the brief may be short but still needs these fields:

- identity
- audience
- main purpose
- first impression
- remembered-for
- at least three required sections or content modules
- page model: single page, hybrid, or multi-page
- page map when supporting pages are needed
- public/private boundaries
- style direction
- motion strategy
- privacy avoids
- material status
- inspiration interpretation if references, screenshots, or effect links were provided
- functional must-haves
- practical constraints
- companion skill routing
- validation plan
- brief version and whether this is a new baseline or a patch

## Confirmation Prompt

Before implementation, ask:

```text
Does this brief accurately describe how the homepage should represent you? Correct anything that feels off before I turn it into UI and code.
```

For beginner users, phrase the confirmation in plain language:

```text
This is the plan I would build from. Please check whether it feels like you and whether anything private, exaggerated, missing, or wrongly prioritized needs to change before I start implementation.
```
