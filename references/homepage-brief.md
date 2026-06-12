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
    coverage:
      audience: known | missing | explicitly_deferred
      purpose: known | missing | explicitly_deferred
      core_modules: known | missing | explicitly_deferred
      page_model: known | missing | explicitly_deferred
      style_or_avoids: known | missing | explicitly_deferred
      privacy_boundary: known | missing | explicitly_deferred
      contact_or_next_action: known | missing | explicitly_deferred
      materials: known | missing | explicitly_deferred
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
  placeholder_policy:
    allowed_placeholders:
    must_remove_before_final:
    approved_to_remain:
    replacement_notes:
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
    source_brief_version:
    project_inspection:
      stack:
      existing_pages:
      asset_structure:
      data_or_config:
      deployment_clues:
      user_changes_to_preserve:
      files_not_to_touch:
    authorization_status:
      snapshot_ready: true | false
      user_confirmed_file_edits: true | false
      confirmed_at:
    implementation_plan:
      stack_decision:
      page_model_decision:
      file_plan:
        create:
        modify:
        delete:
        do_not_touch:
      brief_to_file_mapping:
      starter_template_decision:
      motion_implementation:
      validation_plan:
      publish_boundary:
    site_structure:
    pages:
    assets:
    content_data_strategy:
    github_pages_readiness:
    validation:
  final_review:
    brief_to_site_audit:
    placeholder_audit:
    github_pages_compatibility:
  change_control:
    baseline_summary:
    lifecycle_decision: initial_brief | no_brief_update_needed | implementation_only_fix | brief_patch | new_brief_version | publish_only_action
    latest_change_plan:
      issue_or_opportunity:
      recommended_change:
      why_it_fits_active_brief:
      target_files_or_modules:
      visible_impact:
      companion_routing:
      motion_or_reduced_motion_impact:
      validation_needed:
      risks_or_tradeoffs:
      confirmation_status:
    changed_fields:
    publish_status:
    change_history:
      - version:
        date:
        classification: no_brief_update_needed | implementation_only_fix | brief_patch | new_brief_version | publish_only_action
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
- Treat implementation-only fixes and publish-only actions as change history entries, not brief version changes.
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
- requirement coverage status
- placeholder policy
- inspiration interpretation if references, screenshots, or effect links were provided
- functional must-haves
- practical constraints
- companion skill routing
- project inspection and implementation authorization status before file edits
- GitHub Pages readiness
- validation plan
- brief version and whether this is a new baseline or a patch

## Beginner-Facing Brief Wrapper

When showing the brief to a beginner, do not dump only YAML unless they asked for technical detail. Present a short readable wrapper first, then keep the structured `personal_homepage_brief` available for implementation.

Use this shape:

```text
This is the homepage brief I would build from:
- The page represents:
- It is mainly for:
- Visitors should remember:
- It must show:
- It should not reveal:
- It should feel:
- Page shape:
- Missing materials and placeholders:
- Assumptions I am making:

Please correct anything that feels unlike you, too public, exaggerated, missing, or wrongly prioritized.
```

Then include the structured brief or save it internally, depending on the user's environment and request.

Rules:

- Confirmed facts must stay separate from assumptions.
- Inferred positioning must be easy for the user to reject.
- Private or quarantined material must not appear as public content.
- Placeholders must say what they replace and whether they are safe for draft use.
- A quick brief may be compact, but it must still include page model, privacy boundaries, material status, style direction, and motion decision.

## Confirmation Prompt

Before implementation, ask:

```text
Does this brief accurately describe how the homepage should represent you? Correct anything that feels off before I turn it into an implementation plan and then UI/code.
```

For beginner users, phrase the confirmation in plain language:

```text
This is the plan I would build from. Please check whether it feels like you and whether anything private, exaggerated, missing, or wrongly prioritized needs to change before I plan the file changes.
```
