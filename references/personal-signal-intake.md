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

## Zero-Prep Onboarding Protocol

Use this when the user starts with only a sentence such as "I want to make a personal homepage, but I have no idea yet."

The first response should do three things:

1. Set expectations: explain that the agent will ask in short rounds before writing code.
2. Give a light materials roadmap: tell the user they do not need everything now, but links, projects, photos, social accounts, and style references may help later.
3. Ask only the first 1-3 questions about identity, audience, and memory point.

Do not ask for a complete resume, full biography, brand system, or all links in the first message.

For beginner users, prefer `references/beginner-conversation-patterns.md` over direct checklist questions. Use choices, contrasts, and rough sketches to help them react.

After each user answer:

1. Summarize what is now confirmed.
2. State what is still missing.
3. Tell the user what kind of material may be useful in the next round.
4. Ask the next 1-3 questions.

Before producing a homepage brief for a zero-prep user, cover these minimum checkpoints unless the user explicitly chooses a quick-path shortcut:

- identity: who the user is in ordinary language
- audience: who the homepage is for
- memory point: what visitors should remember
- content/materials: what to show and which links or placeholders exist
- privacy: what not to publish
- taste: preferred feeling, disliked styles, and any references
- media/assets: photos, screenshots, video, audio, or typography-first fallback
- constraints: language, hosting, timeline, and whether publishing is needed now
- motion: none, subtle, moderate, expressive, or not sure

Do not show these checkpoints as a form. Treat them as internal coverage. Ask the user in plain language.

Use this short materials roadmap when helpful:

```text
You do not need to prepare everything now. As we go, useful materials may include:
- basic identity: public name, one-line introduction, audience
- content: projects, writing, publications, services, or links
- proof: GitHub, demos, screenshots, papers, testimonials, metrics
- media: avatar, photos, covers, videos, or a decision to stay typography-first
- taste: sites, apps, moods, colors, objects, music, books, films, or dislikes
- boundaries: anything private, outdated, exaggerated, or not ready for public use
```

The goal is not to collect everything upfront. The goal is to make the user comfortable and help them discover what matters.

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

Use this response shape after collecting signals for a beginner:

```text
What I heard:
- You are:
- The homepage is mainly for:
- Visitors should remember:
- The page should show:
- It should not reveal:
- Taste clues:

My current homepage direction:
- Overall feel:
- First screen should focus on:
- Main sections:
- Movement:
- Materials still useful:

Please correct anything that feels off.
```

Update the internal delivery mode, quality tier, style direction, and motion level silently.

## Quick Start: 5 Questions

Use this when the user starts from zero or wants to save tokens.

```text
1. Who are you in one or two rough sentences?
2. Who should open this page first?
3. What are the three things you most want people to see or remember?
4. What should not be public?
5. Which feels closer: professional, portfolio-like, personal/story-driven, technical, warm, minimal, bold, or not sure?
```

After the user answers, summarize:

- identity
- audience
- content priorities
- taste clues
- privacy boundaries
- missing information
- next materials to prepare or decide

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
