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
