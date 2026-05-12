# Image &amp; Video Drop-In Guide

This is the master reference for what images go where on the Glimpse Vision site. Drop a file with the filename below into the matching folder and it will appear on the site automatically (or, where noted, swap one HTML line). Aim for high-resolution editorial photography &mdash; real people, real frames, real interiors.

Folders already created:

```
site/
├── images/
│   ├── hero/         ← homepage hero stills + poster frame for video
│   ├── frames/       ← isolated/product shots of frames
│   ├── brands/       ← brand-page hero shots (one per designer)
│   ├── interior/     ← Gold Coast & Hinsdale store interiors
│   ├── team/         ← team headshots
│   └── lifestyle/    ← editorial / on-face / lookbook
└── video/            ← hero background video
```

---

## 1. Hero Video (the big win)

**The single most impactful image on the site.** A 6&ndash;15 second loop of frames being tried on, the storefront, hands cleaning a frame, light catching titanium &mdash; anything cinematic and slow.

| File | Spec | Where it goes |
|---|---|---|
| `video/hero.mp4` | 1920&times;1080+ MP4 (H.264), &lt; 8MB if possible, 6&ndash;15 sec loop, **muted** | Homepage hero background |
| `video/hero.webm` | Same content, WebM format (better compression) | Hero fallback for modern browsers |
| `images/hero/hero-poster.jpg` | 1920&times;1080 JPG, frame from the video | Shows while the video loads, and on slow connections |

**To activate:** in `site/index.html`, find the `<!-- When you provide hero footage -->` comment and uncomment the block right below it. Delete the line above (`<div class="hero-media no-video">`).

If you skip video, the animated gradient background already in place looks good on its own.

---

## 2. Hero Still Images (alternative if no video)

If you'd rather have a still hero, drop one of these into `images/hero/`:

| File | Spec |
|---|---|
| `images/hero/hero-still.jpg` | 2400&times;1600 JPG, dark editorial shot |
| `images/hero/hero-still-mobile.jpg` | 1200&times;1600 (portrait) for mobile |

To use a still instead of video, swap the hero-media div for:
```html
<div class="hero-media">
  <img src="images/hero/hero-still.jpg" alt="" />
</div>
```

---

## 3. Brand Pages (14 images, one per designer)

Each brand page has a "split image" panel that should be a hero shot of that brand's frames or campaign imagery.

Drop these into `images/brands/`. Aspect ratio: 4:5 portrait (e.g. 1200&times;1500).

- `images/brands/lindberg.jpg`
- `images/brands/tom-davies.jpg`
- `images/brands/dita.jpg`
- `images/brands/barton-perreira.jpg`
- `images/brands/anne-valentin.jpg`
- `images/brands/thierry-lasry.jpg`
- `images/brands/la-eyeworks.jpg`
- `images/brands/oliver-goldsmith.jpg`
- `images/brands/lafont.jpg`
- `images/brands/theo.jpg`
- `images/brands/sospiri.jpg`
- `images/brands/orgreen.jpg`
- `images/brands/fhone.jpg`

Once dropped in, tell me and I'll swap the gradient placeholders on each brand page for these images automatically.

---

## 4. Locations (interior shots)

Each location page has a hero plus a square interior shot. Drop into `images/interior/`:

| File | Spec |
|---|---|
| `images/interior/gold-coast-hero.jpg` | 1920&times;1080, the storefront or main display |
| `images/interior/gold-coast-detail.jpg` | 1200&times;1200 square, a beauty shot inside |
| `images/interior/hinsdale-hero.jpg` | 1920&times;1080, the storefront |
| `images/interior/hinsdale-detail.jpg` | 1200&times;1200 square, a beauty shot inside |

---

## 5. Team / Experts (8 headshots)

Drop into `images/team/`. Aspect ratio: 4:5 portrait or 1:1 square (1000&times;1250 or 1200&times;1200).

- `images/team/dr-carrie.jpg` &mdash; Dr. Carrie Roitstein
- `images/team/dr-janette.jpg` &mdash; Dr. Janette Perez
- `images/team/dr-john.jpg` &mdash; Dr. John Gialousakis
- `images/team/lesley.jpg` &mdash; Lesley Bramson
- `images/team/dory.jpg` &mdash; Dory Kenna
- `images/team/patty.jpg` &mdash; Patty Nogay
- `images/team/boyce.jpg` &mdash; Boyce Moffitt
- `images/team/dayana.jpg` &mdash; Dayana Strauf

---

## 6. Frame product shots (any quantity)

Drop frame product photography into `images/frames/`. Use any naming you want (e.g. `lindberg-spirit-rimless-1.jpg`, `dita-mach-six.jpg`). I'll wire these into a "Recently in store" or lookbook section once you have a batch.

Aspect ratio: 4:3 or 1:1, ideally on a consistent neutral background.

---

## 7. Lifestyle / on-face / lookbook (any quantity)

The most fashion-forward / aspirational shots. Drop into `images/lifestyle/`. Use any naming. I'll build a dedicated lookbook page (or a homepage lookbook strip) once you have 6+ shots.

Aspect ratio mix is fine &mdash; I'll lay them out editorially. Color, expression, motion, mood.

---

## When you have the folder ready

Tell me the folder name (or just say "images are in"), and I'll:

1. Wire the hero video/still into the homepage
2. Replace all 14 brand-page placeholders with real brand imagery
3. Replace location-page placeholders with interior shots
4. Replace team-page placeholders with headshots
5. Build the lookbook page from the lifestyle folder
6. Add a "Frames in store now" homepage section from the frames folder
7. Set proper `srcset` and `loading="lazy"` for performance
8. Run image optimization (WebP variants) so nothing slows the site down

---

## Image-quality tips for whatever you source

- **Color and contrast matter most.** A dim, low-contrast frame photo will sink the design.
- **Real people &gt; stock.** A single in-store shot of a real client beats ten gleaming stock photos.
- **Keep movement in mind.** For the hero video, slow movement reads luxurious. Fast cuts read like an ad.
- **No watermarks.** If you're pulling from brand websites, get the brand-supplied press images (most brands have a press kit with permission for stockists).
- **Consistent treatment.** If everything feels like it came from the same photographer or moodboard, the site reads premium. If the photos are from 8 different sources with 8 different white balances, it reads chaotic.
