# Inspiration Intake

Use this file when the user provides design references, dynamic effect links, screenshots, mood boards, image references, or asks the agent to help find a better visual direction.

## Purpose

Turn subjective references into actionable homepage requirements without copying another site's code, layout, images, brand, or identity.

References should help answer:

- what feeling the user likes
- what should be avoided
- which layout, motion, media, or typography ideas fit the confirmed homepage goal
- which ideas would distract from the user's identity, content, or audience

## Recommended Beginner Flow

If the user has no references, do not force them to browse. Offer this lightweight option:

```text
You can start without references. If you want the page to feel more visually specific, the most useful preparation is 3-5 links or screenshots. For each one, write one sentence: what you like, what you dislike, and what should not be copied.
```

Prefer user-led reference gathering when possible because personal taste matters and it saves tokens.

Use agent-assisted reference research only when:

- the user asks the agent to inspect specific links
- a confirmed brief exists but the user has no visual references
- the user wants options for dynamic effects, hero imagery, or layout mood
- the agent has browsing or retrieval tools available

If browsing is unavailable, ask the user for links or screenshots and continue from those.

## Reference Sources

| Source | Best use | What to extract |
| --- | --- | --- |
| [CodePen](https://codepen.io/) | Specific dynamic effects and interaction experiments. | Interaction pattern, trigger, intensity, complexity, reduced-motion fallback, whether it fits the content. |
| [React Bits](https://www.reactbits.dev/) | React-ready animated components, text effects, backgrounds, and UI motion patterns. | Component idea, motion role, implementation fit, dependency risk, accessibility concerns. |
| [SiteInspire](https://www.siteinspire.com/) | Real website layout, editorial rhythm, restrained visual systems, and mature interaction use. | Page structure, visual density, navigation, image use, motion restraint. |
| [Pinterest](https://www.pinterest.com/) | Mood boards, colors, typography feeling, image atmosphere, and hero-image direction. | Mood words, palette clues, image style, texture, avoid copying exact images. |
| [Behance](https://www.behance.net/) | Portfolio, personal brand, visual identity, and art-directed presentation. | Brand direction, section rhythm, typography, project presentation, visual confidence. |
| [Awwwards Portfolio Websites](https://www.awwwards.com/websites/portfolio/) | Highly polished portfolio examples and motion-heavy first-screen ideas. | First-screen impact, motion rhythm, layout ambition, risk of overbuilding. |

## Analysis Workflow

When references are provided:

1. Identify the reference type: dynamic effect, page layout, mood board, hero image, portfolio structure, typography, color, or media treatment.
2. Ask the user what they like if it is not obvious. Do not assume a reference means "copy this."
3. Extract transferable ideas:
   - layout logic
   - visual mood
   - typography and spacing feel
   - image or media strategy
   - motion trigger and intensity
   - interaction pattern
4. Extract explicit avoids:
   - too flashy
   - too corporate
   - too dark
   - too cute
   - too template-like
   - too difficult to maintain
5. Map the reference to the homepage brief fields.
6. Produce an Inspiration Read and ask for confirmation before design or implementation.

## Inspiration Read Template

```text
Inspiration read:
- Reference 1:
  - What you seem to like:
  - What should not be copied:
  - Transferable idea:
  - Fit for your homepage:
  - Risk:
- Reference 2:
  - What you seem to like:
  - What should not be copied:
  - Transferable idea:
  - Fit for your homepage:
  - Risk:

How I would translate this into the homepage:
- Style:
- Layout:
- Motion:
- Media/images:
- What to avoid:

Please confirm whether this interpretation is right before I update the brief or design plan.
```

For beginner users, keep this plain and short. Do not expose internal schema names unless the user asks.

## Brief Mapping

Map references into these brief fields:

| Reference signal | Brief fields |
| --- | --- |
| "I like this first screen" | `style.image_strategy`, `information_architecture.page_map`, `goal.first_impression` |
| "I like this hover / scroll effect" | `motion_strategy.hover_feedback`, `motion_strategy.scroll_reveal`, `motion_strategy.level` |
| "I like this color mood" | `style.color_notes`, `taste.likes`, `taste.references` |
| "I like this typography feeling" | `style.typography_notes`, `taste.design_read` |
| "This feels too corporate / too flashy" | `taste.dislikes`, `style.must_avoid`, `motion_strategy.avoid` |
| "I want something like this portfolio" | `archetype`, `content.priority_order`, `information_architecture.page_model` |
| "I want this kind of background image" | `style.image_strategy`, `content.media_assets`, `constraints.external_resources` |

## Dynamic Effects

For CodePen, React Bits, or other effect references:

- Treat the reference as an interaction idea, not a code dependency.
- Check whether the effect supports the user's content and audience.
- Prefer subtle hover, reveal, card, cursor, or background motion over heavy parallax, scroll hijacking, or distracting particles.
- Require `prefers-reduced-motion` fallback.
- Do not copy code unless the license clearly allows it and the user approves using that code.
- Rebuild the effect in the chosen project style when practical.

## Image And Asset References

For Pinterest, Behance, Awwwards, SiteInspire, screenshots, or image references:

- Do not reuse images unless the user owns them or the license allows it.
- Prefer user-provided photos, licensed images, generated original visuals, or typography-first design.
- If the reference is a hero-image mood, translate it into art direction: subject, palette, lighting, texture, composition, and emotional tone.
- If generating a new asset, route to `imagegen` when available.

## Confirmation Rule

Reference interpretation is not implementation approval.

Before changing code, confirm:

- which reference ideas are accepted
- which ideas are rejected
- whether the brief needs a patch or new version
- target files and visible impact

