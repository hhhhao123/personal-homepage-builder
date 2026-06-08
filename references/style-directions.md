# Style Directions

Offer directions in human language, not only design terms. Each direction should include a feeling, layout implication, and avoid list.

## Direction Patterns

### Quiet Expert

- Feeling: credible, measured, calm.
- Layout: strong typography, spacious sections, restrained cards, clear hierarchy.
- Palette: warm neutrals, one dark anchor, one accent.
- Avoid: excessive animation, loud gradients, crowded dashboards.

### Night Studio

- Feeling: focused, cinematic, personal, late-night creative.
- Layout: dark hero, strong negative space, one atmospheric image, signal/waveform accents.
- Palette: near-black, warm amber/coral, muted teal.
- Avoid: neon cyberpunk, club poster, unreadable dark UI.

### Editorial Creator

- Feeling: magazine-like, opinionated, expressive.
- Layout: asymmetric text blocks, large headlines, featured content modules.
- Palette: high-contrast paper/ink plus one memorable accent.
- Avoid: bland blog template, too many equal cards.

### Technical Console

- Feeling: precise, builderly, systems-oriented.
- Layout: dense but organized modules, code/data accents, compact navigation.
- Palette: dark or neutral base with signal accents.
- Avoid: fake terminal gimmicks, unreadable monospaced body text.

### Warm Humanist

- Feeling: approachable, generous, personal.
- Layout: soft section transitions, story blocks, portrait/photo emphasis.
- Palette: warm paper, natural accents, restrained contrast.
- Avoid: beige monotony, overly cute visuals.

### Bold Personal Brand

- Feeling: public-facing, memorable, confident.
- Layout: strong first-screen identity, clear offer or mission, proof sections.
- Palette: sharper contrast and fewer colors.
- Avoid: vague slogans, sales-page bloat.

### Symbolic Personal Motif

- Feeling: personally meaningful, subtle, story-led.
- Layout: standard professional structure with one recurring motif from zodiac, MBTI, hometown, music, season, or personal memory.
- Palette: derived from the motif but constrained for readability.
- Avoid: literal horoscope pages, personality stereotypes, decorative overload.

## Translation Rules

- "高级" usually means fewer colors, better type hierarchy, better spacing, fewer effects, and more intentional image use.
- "科技感" can mean precision, confidence, or future-facing. Ask which one before adding neon or cyberpunk styling.
- "简洁" does not mean empty. It means fewer competing elements and clearer priorities.
- "有个人特色" means one strong memory point, not decorating every section.
- "温暖" often comes from copy tone, imagery, texture, and off-white backgrounds, not only orange colors.
- "酷" is ambiguous. Ask whether they mean dark/cinematic, experimental, premium, street, or technically sharp.
- MBTI, zodiac, and similar labels are symbolic or conversational clues. Confirm what the user wants reflected before turning them into color, motion, layout, or copy choices.
- A profession should influence content hierarchy first, visual style second.
- A hobby should usually become atmosphere, imagery, section naming, or one visual motif, not the whole site identity unless the user wants that.

## From Preference To Engineering

After taste discovery, translate the user's preferences into implementation decisions:

```yaml
style_translation:
  homepage_archetype:
  style_direction:
  content_priority:
  theme_notes:
  typography_notes:
  image_strategy:
  motion_level:
  section_structure:
  implementation_notes:
```

Keep this translation visible in the brief so frontend and theme skills have concrete input. Avoid leaving the result as vague words such as "cool", "clean", or "personal".

## Presenting Options

Use a format like:

```text
I see three plausible directions:
1. Night Studio: ...
2. Quiet Expert: ...
3. Symbolic Personal Motif: ...

Recommended: Night Studio, because it supports your research identity while making R&B a memorable atmosphere.
```
