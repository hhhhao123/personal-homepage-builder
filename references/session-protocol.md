# Session Protocol

Use this file whenever `personal-homepage-builder` is active in a conversation.

## Session State

Maintain this state internally and update it after meaningful user input:

```yaml
homepage_session:
  active: true
  current_phase:
  user_experience_mode: beginner | technical | existing_site
  delivery_mode:
  quality_tier:
  motion_level:
  user_goal:
  project_context:
    has_existing_site:
    stack:
    deployment_target:
    git_scope:
  materials:
    provided:
    personal_signal_pack:
    extracted:
    missing:
    placeholders:
    to_prepare_next:
    privacy_risks:
  inspiration:
    provided_references:
    inspiration_read:
    accepted_ideas:
    rejected_ideas:
    should_not_copy:
    asset_license_notes:
    confirmation_status: none | unconfirmed | confirmed | partially_confirmed | rejected
  identity:
    confirmed_facts:
    inferred_positioning:
    tentative_signals:
    open_questions:
  audience:
    primary:
    secondary:
  requirements:
    mvr_status: missing | partial | ready | confirmed
    primary_audience_confirmed:
    main_purpose_confirmed:
    core_modules:
    information_architecture:
      page_model: unknown | single_page | hybrid | multi_page
      page_map:
      navigation:
    style_or_avoids_confirmed:
    privacy_confirmed:
    next_action_confirmed:
    material_status_confirmed:
    baseline_status: none | draft | confirmed | changed
    last_confirmed_summary:
    change_log:
  iteration:
    pending_change_plan:
    visual_diagnosis:
    dissatisfaction_type:
    preserved_strengths:
    rejected_directions:
    selected_revision_level:
    selective_skill_routes:
    confirmation_required:
    confirmed_change_plan:
    last_confirmed_at:
  probe_artifacts:
    direction_cards:
    text_wireframes:
    page_maps:
    content_gap_maps:
    inspiration_reads:
  taste:
    references:
    likes:
    dislikes:
    hypotheses:
    companion_skill_used:
  brief:
    status: not_started | draft | confirmed | needs_revision
    current_version:
    current_effective:
    lifecycle_status: initial | unchanged | patched | superseded
    last_change_classification:
    changed_fields:
    change_history:
    last_confirmed_at:
  implementation:
    allowed: false
    authorization_snapshot_ready:
    project_inspected:
    target_files:
    content_data_strategy:
    placeholder_policy:
    github_pages_readiness:
    user_confirmed_file_edits:
    companion_skills:
    fallback_notes:
  validation:
    build_checked:
    brief_to_site_audit_checked:
    placeholder_audit_checked:
    design_review_checked:
    responsive_checked:
    publish_approved:
```

Do not print the full state every turn. Print only the parts that help the user make a decision.

For beginner users, keep `delivery_mode`, `quality_tier`, `motion_level`, schema names, and gate names internal unless the user asks for technical detail. Describe them as plain-language choices instead.

## Phase Transitions

Before moving to a new phase, state a compact transition note:

```text
Current phase: <phase>
Confirmed: <short facts>
Inferred: <short hypotheses>
Needs confirmation: <open questions>
Next gate: <required output or user confirmation>
```

## Restart And Resume

If the conversation resumes after a pause:

- Reconstruct `homepage_session` from available context.
- State the current phase and any uncertainty.
- Do not assume a previous brief is confirmed unless the user clearly accepted it.
- If implementation already began, re-check the brief, stack, git scope, project inspection, and implementation authorization snapshot before editing.

## User Wants To Skip Ahead

If the user asks to jump directly to design or code:

- Keep momentum, but do not skip gates silently.
- Produce the smallest viable identity reflection and brief.
- Ask only the missing high-impact questions.
- State which gates are being compressed and which cannot be skipped.
- If the user is asking for file edits, produce the implementation authorization snapshot from `enforcement-checklist.md` after the brief is confirmed and wait for explicit edit confirmation.

## User Needs Something Concrete

If the user cannot answer abstract questions, do not keep asking the same way.

- Offer 2-4 concrete choices.
- Produce a non-code probe sketch from `beginner-conversation-patterns.md`.
- If content may need more than one page, offer a simple page map.
- Ask what feels wrong, missing, too formal, too personal, too plain, or too flashy.
- Convert the reaction into internal requirements.

Probe sketches do not permit implementation. They help the requirements baseline become clearer.

## User Adds A New Requirement Mid-Project

If the user already has a built or in-progress homepage and asks for a new feature, design adjustment, dynamic element, section, media treatment, or exploratory suggestion:

- Treat it as an iteration request.
- Use `iteration-requests.md`.
- Inspect the current page or available implementation before recommending UI changes.
- Preserve the confirmed brief unless the new request changes identity, audience, or public content.
- Offer 2-4 context-aware options when the user has no clear solution.
- Produce a compact change plan before editing.
- Use `brief-lifecycle.md` to classify whether the current brief stays unchanged, needs a patch, or needs a new version.
- Wait for explicit confirmation of the change plan before editing files. Do not skip this for low-risk or "you decide" requests.
- If a requirements baseline or brief was confirmed, use the Change Control Gate in `output-contracts.md` and reconfirm the affected part before editing.

## User Dislikes The First Version

If the user says the initial homepage feels wrong, too plain, too generic, not like them, visually weak, or unsatisfying:

- Treat the reaction as useful design feedback, not as a full restart by default.
- Use `visual-iteration.md`.
- Inspect the current page, screenshot, files, or URL before making visual claims.
- Ask for references only if they would help; do not force the user to find references.
- Diagnose the likely issue in plain language.
- Preserve what still works.
- Invoke only the necessary available companion skills for the diagnosed problem.
- Produce a revision plan and wait for explicit confirmation before editing files.
- Use `brief-lifecycle.md` if the change affects the confirmed plan or visual direction.

## User Wants To Save Tokens

If the user wants to reduce back-and-forth:

- Offer the Quick Start questions from `personal-signal-intake.md`.
- Ask them to paste a prepared Personal Signal Pack.
- Extract only the missing high-impact items.
- Avoid repeating questions already answered in the signal pack.

## Exit

The workflow ends when the user explicitly exits it, changes task domain, or confirms final delivery. If the user later resumes personal homepage work, reactivate this protocol.
