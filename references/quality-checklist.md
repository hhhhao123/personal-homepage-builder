# Quality Checklist

Use this checklist before final delivery of any implemented homepage/site or visible page iteration.

## Review Report Template

```text
Implementation review:
- Brief match:
- Change classification:
- Files changed:
- Files intentionally left untouched:
- Placeholder/fake-content audit:
- Maintainability:
- Responsive check:
- Accessibility check:
- Motion and reduced-motion check:
- Performance basics:
- GitHub Pages compatibility:
- Build/preview result:
- Known risks:
- Publish status:
```

The review must be tied to the current effective brief, not only to generic UI quality.

## Iteration Review Addendum

For post-brief or post-implementation changes, verify:

- the implemented change matches the confirmed change plan
- the classification was appropriate: no brief update needed, implementation-only fix, brief patch, new brief version, or publish-only action
- brief patches or new brief versions were recorded before implementation when required
- no unrelated files were changed
- responsive, accessibility, and reduced-motion checks were rerun when the change touches layout, UI, content, media, or motion
- publishing was not performed unless explicitly approved

## Identity Fit

- The first viewport clearly says who the person is.
- One memory point is visible without overpowering the professional goal.
- The page does not look like a generic template.
- The structure matches the user's primary audience.
- The built site matches the current effective brief, not an earlier draft or a generic portfolio pattern.
- The confirmed page model is respected: one-page, hybrid, or multi-page as approved.

## Content

- The most important content appears early.
- Claims are backed by concrete work, experience, or links.
- Extracted content is accurate, current, and confirmed before public use.
- Private or sensitive source material is not published accidentally.
- Fake names, fake projects, fake metrics, fake testimonials, fake awards, fake links, and unapproved private details are absent.
- Any remaining placeholders are explicitly approved and easy to find later.
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
- The first viewport and navigation remain usable on narrow mobile screens.
- Responsive checks cover at least a desktop-width view and a mobile-width view when tooling allows.
- Keyboard navigation reaches interactive elements in a sensible order.
- Text remains readable over images, video, gradients, or textured backgrounds.

## Technical

- Internal paths work with the hosting setup.
- GitHub Pages sites use compatible static/Jekyll structure and correct repository assumptions.
- Absolute local paths are not used for deployable assets, links, scripts, styles, or images.
- SEO/social preview metadata is present for publishable sites.
- Multilingual sites have a clear default language and consistent translated fields.
- Build command passes.
- Generated assets are saved in the project.
- Motion CSS/JS is stored in project asset files and does not require core content to load.
- Unrelated user changes are not reverted.
- Git commits stage only intended files.
- CSS, JS, images, and optional data are separated under the existing asset structure unless a prototype exception was confirmed.
- Data/config files are easy to edit for repeated projects, writing, publications, social links, media, or services.
- All navigation links point to existing pages, sections, or confirmed external URLs.
- No deployable file contains local absolute paths.
- The final response says whether commit, push, or publish was performed, and only does so when explicitly approved.
- For publish-only actions, staged files match the approved scope and no new visible page changes were introduced.

## Performance Basics

- Avoid loading large media before it is needed.
- Use responsive image sizing or stable media containers when practical.
- Keep JavaScript progressive: core content should be visible without JavaScript.
- Avoid heavy animation libraries for small static sites unless the brief specifically needs them.
- Use lazy loading for non-critical images or embeds when practical.
