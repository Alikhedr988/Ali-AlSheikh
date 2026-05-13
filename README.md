# Ali Khedr — Portfolio

Cinematic portfolio for **Ali Khedr** — independent Syrian journalist, photographer, videographer and musician based in Beirut.

🌐 Live: _(to be added after deploy)_

---

## Stack

- **Plain HTML / CSS / JS** — no build step required
- **GSAP + ScrollTrigger** for scroll-driven motion (loaded from CDN)
- **Lenis** for smooth scroll (loaded from CDN)
- **Fraunces** variable serif from Google Fonts
- **YouTube embeds** for all video work (videos stay on YouTube)

Designed to be **lightweight, fast, and easy to deploy anywhere**.

---

## Folder structure

```
ali-khedr-portfolio/
│
├── index.html              ← homepage (cinematic single-page scroll for now)
│
├── assets/
│   ├── images/             ← all portfolio photography, organized by section
│   │   ├── bio/
│   │   ├── indivisible/
│   │   ├── beirut-uprising/
│   │   ├── osf-bekaa/
│   │   ├── dop-stills/
│   │   ├── art-culture/
│   │   ├── seenaryo/
│   │   ├── music/
│   │   ├── jazz-kabeez/
│   │   ├── journalism/
│   │   └── additional/     ← extras pulled from page metadata
│   ├── designs/
│   │   └── jazz-kabeez-posters/    ← 5 musician poster designs
│   ├── video-thumbnails/   ← high-res YouTube poster frames
│   └── site-meta/
│       └── favicon.ico
│
├── css/                    ← (reserved — currently all styles are inline in index.html)
├── js/                     ← (reserved — currently all JS is inline in index.html)
│
├── manifest.json           ← every image: caption, original URL, intended section
├── links.md                ← all YouTube IDs, publications, socials, contact
├── README.md               ← this file
└── .gitignore
```

---

## Local development

No build step. Just open `index.html` in a browser, or run a local server:

```bash
# Python (most systems have this)
python3 -m http.server 8000

# Or Node (if you have it)
npx serve .
```

Then visit http://localhost:8000

---

## Deploy

### Recommended: Vercel

1. Push this repo to GitHub.
2. Go to [vercel.com](https://vercel.com), sign in with GitHub.
3. Click **Add New → Project**, select this repo, accept defaults.
4. Done. Vercel gives you a `*.vercel.app` URL immediately.
5. To attach a custom domain (e.g. `alikhedr.com`): Settings → Domains → Add.

### Alternative: Netlify

Same flow as Vercel — connect repo, deploy, attach domain.

### Alternative: GitHub Pages

1. Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
2. Site published at `https://<username>.github.io/ali-khedr-portfolio/`.

⚠️ If using GitHub Pages, all image/asset paths in `index.html` are **relative**, so it works out of the box. No changes needed.

---

## Build status

Section-by-section progress on the cinematic rebuild:

- [x] **Homepage** — hero, interlude, 3-story scroll, contact CTA
- [ ] **Film page** — categorized YouTube embed gallery (Showreel, Aerial, Arts & Culture, Documentary, Humanitarian, Music)
- [ ] **Photography page** — full visual essay gallery with the rest of the photo work
- [ ] **Journalism page** — published-work timeline (Amnesty, Al Jazeera, Saferworld, News Deeply)
- [x] **Jazz Kabeez page** — sky background, floating clouds & shapes (mouse parallax), poster gallery, 7 videos, album CTA
- [ ] **About page** — full bio, portrait, contact, socials
- [ ] **Mobile-specific motion pass**
- [ ] **Hi-res photo replacements** from local archive

---

## Notes for future work

**Hi-res photos.** Images currently in `assets/images/` were extracted from the Weebly CDN at display resolution (largest single file: 232 KB). For a true cinematic feel on 4K/retina displays, replacing these with hi-res originals from your archive is the single biggest upgrade available. Keep filenames identical so paths stay correct.

**One known broken image.** `dsc05084-2` (brass polishing at Al-Fares refugee camp) is 404 on the source Weebly site. If you have a local copy, drop it into `assets/images/seenaryo/dsc05084-2-brass-polishing.jpg`.

**Videos.** All 17 YouTube IDs are documented in `links.md`. They embed by ID, no need to host video files. The `assets/video-thumbnails/` folder contains the high-res poster frames pulled from YouTube for use as click-to-play previews.

**Image optimization later.** When the repo grows or traffic picks up, consider moving images to Cloudinary (free tier handles this scale easily) for automatic WebP/AVIF conversion and responsive sizing. Until then, GitHub-served assets are fine.

---

## Contact

- **Email**: alishkhedr@gmail.com
- **Phone**: +961 76 955 915
- **Instagram**: [@ali_shaikh_](https://instagram.com/ali_shaikh_)
- **Facebook**: [askorn](https://www.facebook.com/askorn)
- **LinkedIn**: [ali-alsheikh-khedr](https://www.linkedin.com/in/ali-alsheikh-khedr-a1b8a680/)

---

Built with care. The work is the point.
