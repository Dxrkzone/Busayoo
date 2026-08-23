# Where every image and video goes

All media files sit at the project root — no `images/` or `videos/` subfolders — and are
referenced by plain `<img src="filename.jpg">` and `<video><source src="filename.mp4"></video>`
tags in `index.html`. To swap something out, replace the file (keep the same filename) — or
open `index.html`, search for the filename, and point it at a new file instead.

Every insertion point also has an HTML comment directly above it, e.g. `<!-- File: bio-intro.mp4 -->`,
so you can just search the file for the section name (Ctrl+F "Logo Design") to jump straight there.

## Hero
| File | Used for |
|---|---|
| `hero-photo.png` | Bust photo at the top of the page |

## Bio
| File | Used for |
|---|---|
| `bio-intro.mp4` | Short intro clip under the bio heading (autoplays, muted, looped) |

## Work section order

The Work section now leads with video, then logo work, then brand identity, then social:

1. **Video Content** — reels
2. **Logo Design** — logo marks + logo animation clips
3. **Brand Identity** — brand guideline boards
4. **Social Media Content** — social videos

## Video Content
| File | Used for |
|---|---|
| `reel-1.mp4` – `reel-14.mp4` | Short-form video: reels, promos, behind-the-scenes |

## Logo Design
| File | Used for |
|---|---|
| `logo-macro-tape-dark.jpg`, `logo-macro-tape-light.jpg` | The Macro Tape logo marks |
| `logo-just-peppers-light.jpg`, `logo-just-peppers-dark.jpg` | Just Peppers logo marks |
| `logo-osteria-dei-nonni-light.jpg`, `logo-osteria-dei-nonni-dark.jpg` | Osteria dei Nonni logo marks |
| `logo-video-1.mp4` – `logo-video-4.mp4` | Logo animation/presentation clips |

## Brand Identity
| File | Used for |
|---|---|
| `brand-guide-grab-and-go.jpg` | Grab & Go brand guideline board |
| `brand-guide-hair-by-bola.jpg` | Hair by Bola brand guideline board |
| `brand-guide-soundturf.jpg` | Soundturf brand guideline board |
| `brand-guide-ebar-palette.jpg` | E-Bar brand guideline board — color palette |
| `brand-guide-ebar-personality.jpg` | E-Bar brand guideline board — brand personality |

## Social Media Content
| File | Used for |
|---|---|
| `social-video-1.mp4` – `social-video-12.mp4` | Video content |

---

## To add more, or rearrange

Every tile in the Work section sits inside a `<div class="media-tile">`. To add a new one,
copy an existing tile and change the filename:

```html
<div class="media-tile reveal-scale">
  <img src="your-new-file.jpg" alt="Description" loading="lazy">
</div>
```

For video, use:

```html
<div class="media-tile reveal-scale">
  <video controls muted playsinline preload="none">
    <source src="your-new-file.mp4" type="video/mp4">
  </video>
</div>
```

The grid (`.media-masonry`) auto-arranges tiles by column, so order in the HTML is left-to-right,
top-to-bottom — reordering the `<div class="media-tile">` blocks reorders the gallery. To reorder
whole categories (e.g. move Brand Identity above Logo Design), move the entire
`<div class="work-category">...</div>` block.

## Notes

- The Web Design category has been removed.
- Videos are set to `controls muted playsinline preload="none"` (click to play) rather than
  autoplay, since autoplaying 30+ videos at once would slow the page down badly. `preload="none"`
  means the browser doesn't touch a video file until you press play — this avoids upfront
  byte-range requests that some static hosts mishandle. The bio intro clip at the top is the
  only one that autoplays, since it's just the one.
- Every video in this set has been verified frame-by-frame with ffmpeg and confirmed
  `faststart` (moov atom at the front of the file) before being included.
