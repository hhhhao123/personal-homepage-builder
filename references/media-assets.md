# Media Assets

Media is an optional advanced customization layer. Use it when it makes the homepage more personal or helps show the user's work. Keep the default GitHub Pages site fast and usable without media.

## Supported Media Inputs

- Style reference screenshots or images
- Portraits and personal photos
- Work/project screenshots
- Uploaded images for gallery, hero, avatar, or background
- Uploaded video files for background, reel, or project preview
- Video links from YouTube, Bilibili, Vimeo, TikTok/Douyin, Xiaohongshu, Instagram, or other platforms
- Music/audio files or music links
- User-provided cover images, thumbnails, posters, or QR codes

## Reference Style Images

When the user uploads a site screenshot or style image:

- Identify what they like: layout, color, typography, atmosphere, image treatment, motion, density, or content structure.
- Do not clone a brand or copyrighted design exactly.
- Translate the reference into a new personal direction tied to the user's identity.
- If multiple references conflict, ask which quality matters most.

## Personal And Work Images

- Use provided photos when they are meaningful and public-safe.
- Ask whether images should be shown directly, abstracted, cropped, filtered, or used only as generation references.
- For uploaded images, preserve important faces/objects unless the user asks for stylization.
- Prefer stable sizes and responsive crops for hero images, cards, and galleries.

## Video Strategy

Use video in one of these ways:

- **Background video**: decorative, muted, looped, short, compressed, with a poster image fallback.
- **Featured work card**: poster image plus play/link action.
- **Embedded platform video**: iframe or platform embed, loaded lazily when possible.
- **External video link**: card linking to the platform when embedding is heavy or blocked.

For background video:

```html
<video autoplay muted loop playsinline poster="assets/images/hero-poster.jpg">
  <source src="assets/video/hero.mp4" type="video/mp4">
</video>
```

Rules:
- Background video must be muted.
- Always provide a poster image.
- Avoid large files in GitHub Pages repositories; prefer short compressed clips.
- Respect reduced-motion preferences; show poster or pause animation when reduced motion is requested.
- Do not put essential information only in video.

## Audio And Music Strategy

Autoplay with audible audio is not reliable across modern browsers and can be unpleasant for visitors. Use one of:

- visible play button
- small music player
- link to Spotify, Apple Music, NetEase Cloud Music, QQ Music, SoundCloud, YouTube, or Bilibili
- muted background video with optional "play sound" control after user interaction

Rules:
- Do not promise automatic audible playback on page load.
- Do not hide audio controls if audio is central to the experience.
- Avoid surprising users with sound.
- Store only audio the user owns or is licensed to publish.

## Video Covers And Thumbnails

Preferred order:

1. Use a user-uploaded cover image.
2. Use a locally generated cover/poster from an uploaded video when tooling is available.
3. Use a platform thumbnail only when it is easy and allowed for that platform.
4. Use a designed placeholder card if no cover is available.

Do not depend on scraping thumbnails from platforms when that requires authentication, violates platform terms, or is brittle.

## Media Rights And Privacy

- Ask whether uploaded media is owned by the user or licensed for public use.
- Do not publish private family photos, private social media screenshots, copyrighted music, or copyrighted video unless the user confirms public rights.
- If rights are unclear, use the media as private inspiration only.

## Implementation Rules

- Save public site media under the repository's asset structure, usually `assets/images/`, `assets/video/`, or an existing equivalent.
- Do not reference private local absolute paths in deployable files.
- Provide meaningful alt text for informative images and empty alt text for purely decorative images.
- Use stable aspect ratios or media containers so images and video do not cause large layout shifts.
- Use poster images for video and visible controls for audio.
- Keep media optional when the homepage goal can be met with typography and layout.
- If a generated raster asset is used, save it with a descriptive filename and record its role in the asset strategy.
- If a media placeholder remains, label what it replaces and whether it is safe to publish as a draft.

## Brief Fields

Add these fields when media is involved:

```yaml
media:
  references:
  public_assets:
  private_inspiration:
  hero_media:
  gallery:
  featured_videos:
  music:
  rights_confirmed:
  fallbacks:
```
