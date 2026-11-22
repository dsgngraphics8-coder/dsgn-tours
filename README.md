# 3 BHK Virtual Tour — DSGN Graphics

A client-facing presentation site for one residential project. Plain static files, no build step.

| File | What it is |
|---|---|
| `index.html` | Landing page — video, 2D plan, area statement, contact |
| `walkthrough.html` | Interactive 3D walkthrough (three.js) |
| `assets/model.glb` | The flat, exported from Blender (9.3 MB) |
| `assets/walkthrough.mp4` | 51-second guided video tour with music |
| `assets/plan-2d.svg` / `.png` | Dimensioned 2D floor plan |

## Deploying to Vercel

1. vercel.com → **Add New… → Project**
2. Import this repository.
3. Framework preset: **Other**. Leave build command and output directory empty.
4. **Deploy.**

Vercel gives a `*.vercel.app` link immediately. To use a custom domain
(e.g. `tour.dsgngraphics.com`), add it under **Project → Settings → Domains**.

## Reusing this for a new client

Copy the repo, then replace:

- `assets/model.glb` — new Blender export
- `assets/walkthrough.mp4` — new video
- `assets/plan-2d.svg` — new plan
- the `ROOMS` array near the top of the script in `walkthrough.html` (room names, x/y bounds, sizes)
- the text and area table in `index.html`

Each client gets its own repo and its own Vercel project, so each has its own link.

---
© DSGN Graphics · Amravati
