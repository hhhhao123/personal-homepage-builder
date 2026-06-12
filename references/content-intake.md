# Content Intake

Support two input modes:

- **Conversation-first**: user does not have prepared materials; build the brief through interview.
- **Materials-first**: user uploads or pastes documents/text; extract homepage content first, then ask targeted follow-up questions. Do not skip clarification.

## Acceptable Source Materials

- Resume or CV
- Academic bio
- Personal introduction
- Portfolio/project list
- Publication list
- Services/offers
- Social media profile text
- Article drafts
- Speaking/event bio
- Personal notes, memories, hobbies, values
- Link collections
- Images, portraits, life photos, work screenshots, visual references, or existing site screenshots
- Video links, uploaded video files, music/audio links, or uploaded audio files

## Extraction Schema

Extract into this structure:

```yaml
content_intake:
  source_materials:
    - type:
      filename_or_origin:
      public_use_status: confirmed | unconfirmed | private
  facts:
    identity:
    education:
    work:
    projects:
    publications:
    services:
    achievements:
    social_links:
    media_assets:
    reference_styles:
    contact:
  story_material:
    turning_points:
    motivations:
    values:
    hobbies:
    personal_symbols:
  tone_clues:
    writing_style:
    repeated_words:
    emotional_texture:
  homepage_candidates:
    hero_statement:
    section_ideas:
    featured_items:
    proof_points:
  gaps:
    missing_links:
    missing_dates:
    unclear_claims:
    media_rights:
    privacy_questions:
```

## Public Content Safety

- Do not publish phone numbers, private addresses, IDs, private social accounts, unpublished sensitive work, or personal details unless the user explicitly confirms they are public.
- Mark uncertain extracted facts as `needs_confirmation`.
- If source materials conflict, ask the user which is current.
- If content sounds inflated, keep wording factual and grounded.

## Scattered Material Triage

When the user provides scattered text, links, resume/CV fragments, screenshots, or inspiration references, first triage the input before asking follow-up questions.

Use this internal split:

```yaml
triage:
  confirmed_public_candidates:
  needs_confirmation:
  private_or_sensitive_quarantine:
  taste_or_reference_signals:
  homepage_content_candidates:
  missing_or_placeholder_ready:
  contradictions_or_outdated_items:
```

Rules:

- Do not ask the user to reformat the material.
- Do not treat a link, screenshot, or resume line as permission to publish it.
- Do not repeat sensitive details verbatim unless needed for confirmation.
- Ask only 1-3 follow-up questions after triage.
- If references are included, separate content facts from visual inspiration.

Use this user-facing summary:

```text
I sorted the material into:
- likely public homepage material:
- useful but needs confirmation:
- private or sensitive, so I will not publish it by default:
- possible style/reference clues:
- missing items or placeholders:

Before I turn this into a homepage plan, I only need to confirm:
1.
2.
3.
```

## Privacy Quarantine

If the user over-shares private information, quarantine it instead of treating it as normal content.

Quarantine examples:

- phone number, home address, ID number, private email
- precise location if not clearly intended for public use
- legal name when the user may prefer a display name
- unpublished work, confidential employer/client context, class projects, medical/family/personal context
- private photos, private social screenshots, unlicensed images or music

For quarantined material:

- mark as `private_or_sensitive_quarantine`
- never put it in the brief as public content
- ask whether to omit it, generalize it, or use it only as private context
- if repeated in a summary, describe the category rather than the exact detail when possible

Example:

```text
I noticed a few details that may be private, such as direct contact or exact location information. I will not publish those by default. Should the site use only a public email/social link, or should we omit direct contact for now?
```

## Turning Raw Text Into A Homepage

1. Extract facts and story material.
2. Identify the primary audience and goal.
3. Rank content by homepage usefulness.
4. Convert long text into concise modules.
5. Preserve the user's voice where it helps personality.
6. Ask a minimum confirmation round for identity, audience, emphasis, privacy, and first impression.
7. Map confirmed content into the profile schema when the site should be maintainable.
8. Ask extra follow-up questions only for gaps that affect the design or public accuracy.

## Follow-Up Prompt

Use after extraction:

```text
I extracted these homepage candidates:
- Strong public facts:
- Possible story/memory points:
- Links/contact:
- Content gaps:
- Privacy confirmations needed:

Before designing, I only need to clarify:
1. What public identity should lead the page?
2. Who is the primary audience?
3. Is anything private, outdated, or not meant for the public site?
```
