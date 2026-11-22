# DSGN Graphics — Virtual Tours

Client-facing virtual tours. Plain static files — no build step, no framework, no CDN.

```
index.html                 studio page, lists every project
3bhk-residence/
  index.html               project page — video, 2D plan, areas, contact
  walkthrough.html         interactive 3D walkthrough (three.js, vendored)
  assets/
    model.glb              the flat, exported from Blender (9.3 MB)
    walkthrough.mp4        51-second guided video tour with music
    plan-2d.svg / .png     dimensioned 2D floor plan
    cover.jpg  poster.jpg  still images
    three/                 three.js r160, served from the repo — no CDN to fail
```

One folder per project. This one lives at `/3bhk-residence`; the next client is
a new folder and a new URL on the same site.

## Deploying to Vercel

1. vercel.com → **Add New… → Project**
2. Import this repository.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. **Deploy.**

Vercel gives a `*.vercel.app` link immediately. To use a custom domain
(e.g. `tour.dsgngraphics.com`), add it under **Project → Settings → Domains**.

## Adding a new client project

Copy `3bhk-residence/` to a new folder named after the client, add a card to the
root `index.html`, then replace inside the new folder:

- `assets/model.glb` — new Blender export
- `assets/walkthrough.mp4` — new video
- `assets/plan-2d.svg` — new plan
- the `ROOMS` array near the top of the script in `walkthrough.html` (room names, x/y bounds, sizes)
- the text and area table in `index.html`

Push, and it is live at `/<client-folder>` within about a minute.

---
© DSGN Graphics · Amravati
