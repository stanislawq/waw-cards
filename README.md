# Conference cards

Two tiny single-page "business cards" for a conference — one screen, no scroll,
just a photo, a short intro, and QR codes for quick navigation.

```
├── index.html          ← chooser: links to both cards
├── person-1/           ← portfolio + full CV (3 QR codes)
│   ├── index.html
│   └── assets/  photo.jpg · qr-open-cv.jpg · qr-download-cv.jpg · qr-portfolio.jpg
├── person-2/           ← CV only (2 QR codes)
│   ├── index.html
│   └── assets/  photo.jpg · qr-open-cv.jpg · qr-download-cv.jpg
└── source-qr/          ← original QR images (backup, not used by the sites)
```

Tap a QR on the page to blow it up full-screen for easy scanning.

## Before the conference — customize (2 min)

In each `person-*/index.html` search for `EDIT`:

1. **Photo** — drop a square photo at `person-1/assets/photo.jpg` (and `person-2/assets/photo.jpg`).
   Until you do, a clean placeholder with initials shows automatically.
2. **Name / role** — edit the `<h1 class="name">` and `<p class="role">`.
3. **Two lines about yourself** — edit `<p class="bio">`.
4. **Person 2's QR codes** — the two files in `person-2/assets/` are placeholders
   copied from person 1. Replace them with person 2's own **Open CV** / **Download CV** codes.

The QR images already contain the links baked in — nothing to configure there.

## Deploy with git → GitHub Pages (free)

```bash
# from this folder
git add -A && git commit -m "Update conference cards"

# first time only — create an empty repo on github.com, then:
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Source: `main` branch, `/root` → Save.**
A minute later your cards are live at:

- `https://<you>.github.io/<repo>/person-1/`
- `https://<you>.github.io/<repo>/person-2/`
- `https://<you>.github.io/<repo>/` (chooser)

Any later change: `git add -A && git commit -m "..." && git push` — the site updates itself.

> Works fully offline once loaded (system fonts, no external requests) — handy if the
> conference Wi-Fi is flaky. Show your card on your phone; others scan the code from your screen.
