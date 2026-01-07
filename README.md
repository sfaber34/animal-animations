# animalAnimations

This repo is a **static site** (single `index.html`). There is **no build step** required.

## Deploy to Vercel

- **Recommended**: import the Git repo into Vercel and choose **Framework Preset: Other**.
- **Build Command**: leave empty (no build)
- **Output Directory**: leave empty / default (project root)

That’s it — Vercel will serve `index.html` at `/`.

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

Then open `http://localhost:5173`.


