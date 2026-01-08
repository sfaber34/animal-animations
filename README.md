# animalAnimations

This repo is a **static site** (single `index.html`). There is **no build step** required.

## Deploy to Vercel

- **Recommended**: import the Git repo into Vercel and choose **Framework Preset: Other**.
- **Build Command**: leave empty (no build)
- **Output Directory**: leave empty / default (project root)

That’s it — Vercel will serve `index.html` at `/`.

### Routes

This repo includes `vercel.json` with a couple friendly routes:

- `/giraffe-jump` → `giraffe_jump_duration_control.html`
- `/giraffe` → `giraffe.svg`

### Optional: SPA-style routing (only if you add client-side routes later)

If you later add links like `/about` handled entirely in the browser, add a `vercel.json` rewrite so refreshes don’t 404:

```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```

## Run locally

From this folder:

```bash
python3 -m http.server 5173
```

Then open:

- `http://localhost:5173/` (home)
- `http://localhost:5173/giraffe_jump_duration_control.html` (duration slider page)
- `http://localhost:5173/giraffe-jump` (same page, friendly route on Vercel)

Why you need a local server: browsers block access to an embedded SVG’s DOM when opening the page via `file://`, so the
duration slider can’t call `contentDocument` / `getAnimations()` unless the files are served over `http(s)`.


