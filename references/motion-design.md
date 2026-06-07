# Motion Design

Use this file when deciding whether and how to add dynamic behavior to a personal homepage.

## Principle

Motion is optional but must be decided. Good motion makes a homepage feel intentional, responsive, and personal. Bad motion distracts from identity, slows the page, or makes the site feel like a generic demo.

Discuss motion as a design choice, not a default decoration.

If the user says they do not want motion, set `level: none` and do not reintroduce animated effects later unless they ask for them.

If the user wants the page to feel more dynamic but has not specified a style, recommend a level from the content:

- academic, formal, resume-heavy, or dense profile: `none` or `subtle`
- developer, builder, indie maker, or product-focused profile: `subtle` or `moderate`
- creator, designer, media-forward, or highly expressive personal brand: `moderate`, and `expressive` only with clear user support

## Motion Levels

Use one of these levels in the homepage brief:

```yaml
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
```

## Level Guidance

### none

Use when:

- the user wants maximum simplicity
- the audience expects seriousness or restraint
- accessibility/performance is the top priority
- the content is already visually dense

Still provide focus states and instant UI feedback.

### subtle

Default recommendation for most personal homepages.

Use:

- hero text and identity chips fade in once
- sections reveal with small `opacity + translateY`
- cards lift slightly on hover/focus
- links animate underline or arrow movement
- navigation highlights the active section

### moderate

Use when the user's identity benefits from a more expressive page, such as creator, designer, builder, indie maker, or media-forward profile.

Use:

- staggered project cards
- timeline node reveals
- gentle parallax on nonessential decorative layers
- tab/filter transitions
- media card hover previews without autoplay sound

### expressive

Use only when the user's taste and audience support it.

Use:

- stronger scene transitions
- interactive visual motifs
- custom cursor or canvas effects only if they serve identity
- richer media choreography

Avoid expressive motion for academic, formal, hiring-focused, or dense informational pages unless explicitly requested.

## Common Patterns

Entrance:

- title fade and rise
- avatar or hero image soft reveal
- social links stagger in

Scroll:

- section reveal
- project cards stagger
- timeline line or nodes reveal
- active navigation state

Hover/focus:

- card lift
- image crop or scale within bounds
- button border/color transition
- link underline slide
- arrow movement

State:

- filter changes
- tab transitions
- expanded project details
- copied contact feedback
- media play state

Content-specific:

- academic: restrained timeline and publication card reveal
- developer: subtle terminal/cursor or grid motion
- creator: media card hover and gallery transitions
- music/video: waveform or progress-like motif without autoplay sound
- minimalist: small opacity/position changes only

## Safety Rules

- Always respect `prefers-reduced-motion`.
- Respect `level: none`; do not add reveal animations, parallax, cursor effects, or decorative motion when the brief disables motion.
- Avoid autoplay sound.
- Avoid heavy particle backgrounds by default.
- Avoid motion that blocks reading or delays access to core content.
- Avoid animating every element.
- Avoid scroll hijacking.
- Avoid large layout-shifting animations.
- Keep motion performant: prefer `opacity` and `transform`.
- Ensure hover-only effects have keyboard focus equivalents.

## Implementation Notes

For plain static sites:

- Put motion CSS in `assets/css/animations.css` or the appropriate page stylesheet.
- Put scroll reveal or interaction code in `assets/js/interactions.js`.
- Use IntersectionObserver for scroll reveal when JavaScript is used.
- Keep content visible if JavaScript fails.
- Add a reduced-motion CSS block:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
```
