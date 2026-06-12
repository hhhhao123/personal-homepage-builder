# Profile Schema

Use the profile schema as the long-term editable data contract for a personal homepage. It supports first generation and future maintenance such as adding a new work, link, publication, image, video, or language.

## Purpose

- Keep content separate from presentation.
- Let ordinary users update the homepage without editing layout code.
- Give agents a stable place to add or revise content later.
- Track public/private and confirmation state for safety.

## Implementation Placement Rule

Use profile data when content is repeated, likely to change, or safer to manage outside layout code. Good candidates include projects, publications, writing, talks, services, social links, media, education, experience, and SEO metadata.

Render only items that are public-safe:

- `visibility: public` and `status: confirmed`
- or an explicitly approved draft placeholder recorded in the brief

Do not render `private`, `hidden`, `needs_confirmation`, or `outdated` items as public content unless the user confirms that specific use. Do not create fake profile data to make a page look full.

## Recommended Shape

Use YAML for Jekyll/GitHub Pages when possible, for example `_data/profile.yml`. JSON is acceptable for plain static sites.

```yaml
profile:
  name: ""
  display_name: ""
  headline:
    zh: ""
    en: ""
  bio:
    short:
      zh: ""
      en: ""
    long:
      zh: ""
      en: ""
  languages:
    default: "zh"
    available: ["zh", "en"]
  location: ""
  avatar: ""
  hero:
    image: ""
    video: ""
    poster: ""
    alt: ""
  roles: []
  tags: []
  contact:
    email: ""
    phone:
      value: ""
      visibility: private
    location:
      value: ""
      visibility: public
  social_links: []
  sections:
    enabled: ["about", "links", "projects", "contact"]
    order: ["hero", "about", "projects", "links", "contact"]
  projects: []
  education: []
  experience: []
  publications: []
  media: []
  seo:
    title: ""
    description: ""
    image: ""
  privacy:
    default_visibility: public
    needs_confirmation: []
```

## Social Link Item

```yaml
- platform: GitHub
  label: GitHub
  url: https://github.com/example
  handle: example
  group: professional
  priority: 1
  visibility: public
  status: confirmed
```

## Project / Work Item

Use for software projects, videos, design works, papers, articles, cases, campaigns, photography sets, or creator content.

```yaml
- id: "my-work"
  title:
    zh: ""
    en: ""
  type: "project | video | article | paper | design | photo | service | other"
  summary:
    zh: ""
    en: ""
  cover: "assets/images/my-work-cover.jpg"
  url: ""
  video_url: ""
  repo_url: ""
  paper_url: ""
  platform: ""
  year: 2026
  tags: []
  featured: true
  priority: 1
  visibility: public
  status: confirmed
```

## Privacy And Confirmation

- `visibility: public`: safe to show.
- `visibility: private`: do not publish.
- `visibility: hidden`: stored but not rendered.
- `status: confirmed`: user approved for public display.
- `status: needs_confirmation`: ask before publishing.
- `status: outdated`: do not feature unless user confirms.

Default rule: if privacy is unclear, mark `needs_confirmation`.

## Maintenance Workflow

When the user asks to add or update content:

1. Read the existing profile data.
2. Add or update the relevant item in the profile schema.
3. Keep IDs stable.
4. Ask confirmation for public visibility if needed.
5. Update the rendered page only if the current site does not already render from profile data.
6. Build/test the site.

For existing static pages with no data layer, add one only when it reduces future maintenance. A tiny one-time copy edit does not need a new data architecture.

## SEO And Sharing

Always derive these from the profile when possible:

- page title
- description
- Open Graph title/description/image
- X/Twitter card metadata
- favicon or avatar fallback

Keep descriptions factual and concise.
