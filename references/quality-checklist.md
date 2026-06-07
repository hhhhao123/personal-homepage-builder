# Quality Checklist

## Identity Fit

- The first viewport clearly says who the person is.
- One memory point is visible without overpowering the professional goal.
- The page does not look like a generic template.
- The structure matches the user's primary audience.

## Content

- The most important content appears early.
- Claims are backed by concrete work, experience, or links.
- Extracted content is accurate, current, and confirmed before public use.
- Private or sensitive source material is not published accidentally.
- Maintainable sites store repeatable content in profile data instead of only hard-coded HTML.
- Project/work cards include enough context: title, type, summary, cover or fallback, link, year, and priority.
- Contact path is obvious.
- Secondary content does not compete with primary content.

## Media

- Media rights and public-use status are confirmed.
- Background video is muted, optional, and has a poster fallback.
- Audible audio requires user interaction and visible controls.
- Video embeds or links have accessible labels and fallback covers.
- Large media files do not make the GitHub Pages site feel slow.
- Reduced-motion users are not forced through animated/video-heavy experiences.

## Visual Design

- Typography has clear hierarchy and readable body text.
- Palette is cohesive and not dominated by a single overused hue.
- Cards and sections are not nested unnecessarily.
- Decorative elements support the identity rather than filling space.
- Text does not overlap images or controls.

## Accessibility And UX

- Semantic headings and landmarks are present.
- Links and controls have visible focus states.
- Touch targets are comfortable on mobile.
- Motion respects reduced-motion preferences.
- If the brief sets `motion_strategy.level` to `none`, decorative motion is absent.
- Enabled motion matches the confirmed motion strategy and does not distract from reading.
- Hover effects have keyboard focus equivalents where relevant.
- Images have appropriate alt text or empty alt when decorative.
- Layout has no horizontal overflow.

## Technical

- Internal paths work with the hosting setup.
- GitHub Pages sites use compatible static/Jekyll structure and correct repository assumptions.
- SEO/social preview metadata is present for publishable sites.
- Multilingual sites have a clear default language and consistent translated fields.
- Build command passes.
- Generated assets are saved in the project.
- Motion CSS/JS is stored in project asset files and does not require core content to load.
- Unrelated user changes are not reverted.
- Git commits stage only intended files.
