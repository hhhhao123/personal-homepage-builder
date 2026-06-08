# Personal Signal Intake

Use this file when the user has little, scattered, or unpolished material. This is not resume-writing guidance. Its purpose is to collect enough personal signals to design a homepage without long, expensive back-and-forth.

## Principle

Ask for design-relevant signals, not a perfect biography.

Good signals include:

- who the person is in plain language
- who should visit the homepage
- what the visitor should remember
- what work, story, taste, or links should be visible
- what should stay private
- what visual or emotional directions feel right or wrong

Allow incomplete answers. "I do not know yet" is useful input.

## Preference Discovery Ladder

When the user is a beginner, move from easy personal language to implementation decisions:

1. Identity: who they are in plain language.
2. Audience: who should visit and what that visitor needs.
3. Memory point: what should be remembered after 10-30 seconds.
4. Content priority: what must be visible first, what can be secondary.
5. Privacy boundary: what should not become public.
6. Taste clues: moods, places, objects, media, brands, sites, colors, dislikes.
7. Design translation: homepage archetype, style direction, content modules, theme, motion level, and implementation structure.

Do not ask the user to choose a technical design system. Convert their words into a brief and label what is confirmed versus inferred.

Use this response shape after collecting signals:

```text
What I heard:
- You are:
- The homepage is mainly for:
- Visitors should remember:
- The page should show:
- It should not reveal:
- Taste clues:

My design translation:
- Delivery mode:
- Quality tier:
- Style direction:
- Motion level:
- Homepage structure:

Please correct anything that feels off.
```

## Quick Start: 5 Questions

Use this when the user starts from zero or wants to save tokens.

```text
1. Who are you in one or two sentences? This can be rough.
2. Who is this homepage mainly for?
3. What are the 3 things you most want to show?
4. What should not be public?
5. Are there any sites, colors, moods, objects, music, films, games, books, or visual styles you like or dislike?
```

After the user answers, summarize:

- identity
- audience
- content priorities
- taste clues
- privacy boundaries
- missing information

## Standard Intake: 15 Signals

Use this when the user wants a stronger personalized homepage but does not have a polished profile package.

```text
1. Name or public display name:
2. One-line identity:
3. Roles or communities you belong to:
4. Primary audience:
5. Secondary audience:
6. First impression you want:
7. What you want to be remembered for:
8. 3-6 works, projects, publications, services, or stories to show:
9. Links to include:
10. Contact method:
11. Photos, avatar, video, music, or visual assets available:
12. Visual references you like:
13. Visual references you dislike:
14. Content that must stay private:
15. Timeline and publishing target:
```

Do not require every field. Extract what exists and ask only the next highest-impact missing question.

## Deep Signal Pack

Use only when the user wants deep personalization.

Collect:

- origin story
- career or creative arc
- signature projects
- repeated themes in their work
- values and boundaries
- cultural references
- preferred pace and density
- public persona vs private self
- writing voice
- image and media preferences
- social platform priorities

## Pre-Agent Prompt

Offer this when the user wants to prepare outside the agent session to save cost:

```text
Help me prepare a Personal Signal Pack for designing my personal homepage. Do not write a resume. Ask me for or infer: who I am, who the homepage is for, what I want visitors to remember, what work or links to show, what should stay private, what visual styles I like or dislike, and what tone the site should have. Return a concise structured summary I can paste into a homepage-building agent.
```

## Output Shape

Convert answers into:

```yaml
personal_signal_pack:
  identity:
  audience:
  remembered_for:
  content_priorities:
  links:
  media_assets:
  taste_clues:
  dislikes:
  privacy_boundaries:
  open_questions:
```
