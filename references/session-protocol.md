# Session Protocol

Use this file whenever `personal-homepage-builder` is active in a conversation.

## Session State

Maintain this state internally and update it after meaningful user input:

```yaml
homepage_session:
  active: true
  current_phase:
  delivery_mode:
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
    privacy_risks:
  identity:
    confirmed_facts:
    inferred_positioning:
    tentative_signals:
    open_questions:
  audience:
    primary:
    secondary:
  taste:
    references:
    likes:
    dislikes:
    hypotheses:
    companion_skill_used:
  brief:
    status: not_started | draft | confirmed | needs_revision
    last_confirmed_at:
  implementation:
    allowed: false
    companion_skills:
    fallback_notes:
  validation:
    build_checked:
    design_review_checked:
    responsive_checked:
    publish_approved:
```

Do not print the full state every turn. Print only the parts that help the user make a decision.

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
- If implementation already began, re-check the brief, stack, and git scope before editing.

## User Wants To Skip Ahead

If the user asks to jump directly to design or code:

- Keep momentum, but do not skip gates silently.
- Produce the smallest viable identity reflection and brief.
- Ask only the missing high-impact questions.
- State which gates are being compressed and which cannot be skipped.

## User Wants To Save Tokens

If the user wants to reduce back-and-forth:

- Offer the Quick Start questions from `personal-signal-intake.md`.
- Ask them to paste a prepared Personal Signal Pack.
- Extract only the missing high-impact items.
- Avoid repeating questions already answered in the signal pack.

## Exit

The workflow ends when the user explicitly exits it, changes task domain, or confirms final delivery. If the user later resumes personal homepage work, reactivate this protocol.
