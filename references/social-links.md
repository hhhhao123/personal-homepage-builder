# Social Links

Treat social/contact links as a core part of the homepage, not an afterthought. They help the page show both work and life.

## Supported Link Types

### Contact

- Email
- Phone
- Location
- Calendar/booking link
- Resume/CV download
- Contact form link

### Professional

- GitHub
- LinkedIn
- Google Scholar
- ORCID
- ResearchGate
- Semantic Scholar
- Behance
- Dribbble
- Portfolio
- Company/personal business page

### International Social And Creator Platforms

- X/Twitter
- Instagram
- Facebook
- YouTube
- TikTok
- Twitch
- Threads
- Medium
- Substack
- Spotify/Apple Podcasts

### China-Focused Platforms

- Douyin
- Xiaohongshu
- Bilibili
- Weibo
- Zhihu
- WeChat Official Account
- Jike
- Douban
- WeChat QR code

## Suggested Schema

Use this structure in a data file or equivalent config when possible:

```yaml
social_links:
  - platform: GitHub
    label: GitHub
    url: https://github.com/example
    handle: example
    group: professional
    priority: 1
    visibility: public
    status: confirmed
  - platform: Xiaohongshu
    label: Xiaohongshu
    url: https://www.xiaohongshu.com/user/profile/example
    handle: example
    group: life
    priority: 4
    visibility: public
    status: confirmed
  - platform: WeChat Official Account
    label: WeChat Official Account
    url:
    image: assets/images/wechat-qr.png
    group: creator
    priority: 5
    visibility: public
    status: needs_confirmation
```

## Display Rules

- Prominent links: show the highest-priority contact/action links near the hero.
- Full link set: show grouped links near the contact/footer area.
- Keep labels understandable; do not rely only on icons.
- Use `rel="me"` where useful for identity verification links.
- For external links, use safe attributes when opening in a new tab.
- Do not show empty platforms.
- Do not make every platform equal. Prioritize based on the user's audience and goals.
- Hide or de-emphasize platforms marked private, hidden, or needs-confirmation.

## Interview Hints

Ask the user to provide only links they are comfortable making public. If they are unsure, offer groups:

- Work: GitHub, LinkedIn, Google Scholar, ORCID
- Creator: YouTube, Bilibili, Substack, Medium, WeChat Official Account
- Social/life: Instagram, Xiaohongshu, Douyin, Weibo, Facebook
- Direct contact: email, calendar, resume
