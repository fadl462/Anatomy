# Transparent Anatomy Viewer (Prototype)

A single-file, self-contained interactive anatomy demo: click on an organ to
see its name, function, associated system, common disorders, and a quick
fact. Filter by body system, search by organ name, toggle male/female, and
adjust body transparency.

**Live in one file:** `index.html` — no build step, no dependencies. Just
open it in a browser or serve it as a static site.

## What's actually in this version

- A schematic (simplified-shape) transparent body outline, not a
  photorealistic or clinically precise 3D model.
- 20 organs/structures spanning all 10 requested systems (nervous, skeletal,
  muscular, circulatory, respiratory, digestive, endocrine, lymphatic,
  urinary, reproductive).
- Click, hover-tooltip, system-filter chips, search, transparency slider,
  and a male/female toggle that swaps a couple of body proportions and the
  reproductive-system entry.
- Glow / pulse styling using CSS `drop-shadow`, in an electric-blue
  hologram palette.

## What this is *not* (and what the original brief asked for)

The uploaded brief described a full commercial product: photoreal 3D
organ meshes, a MATLAB App Designer build, medically-vetted content for
every organ (blood supply, nerve supply, weight, clinical notes, audio
pronunciation), quiz/flashcard modes, X-ray/hologram render modes, and
export to PDF/vector/print. That's a multi-month build involving an actual
medical illustrator for accuracy — not something to generate wholesale in
one pass. This prototype is a reasonable *starting point* you can extend:

- **More organs / more detail per organ** — add entries to the `ORGANS`
  array in `index.html`; each one just needs a position, system, and text
  fields.
- **Real 3D** — swap the SVG figure for a Three.js scene and reuse the same
  `ORGANS` data to place labels/markers on a 3D mesh.
- **Quiz/flashcard mode** — the data model already has everything needed;
  it just needs a new UI mode that hides labels and asks the user to
  identify organs.
- **MATLAB App Designer** — a genuinely different tech stack from this web
  prototype; if you want that specifically, it's worth starting a separate
  `.mlapp` project rather than porting this HTML/JS.

## Deploying / uploading to GitHub

```bash
git init
git add index.html README.md
git commit -m "Interactive anatomy viewer prototype"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

To view it live for free, enable **GitHub Pages** on the repo
(Settings → Pages → deploy from `main` branch, root folder) — it'll be
served directly since it's a static HTML file with no build step.
