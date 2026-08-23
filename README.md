# Busayo Okojie — Portfolio

Single-page portfolio site. No build step, no dependencies — it's plain HTML/CSS/JS.

## Structure

```
index.html      the whole site
*.png *.jpg     all photos, logos, brand guideline boards
*.mp4           all clips (reels, logo animations, social content)
MEDIA-GUIDE.md  which file goes where, and how to swap or reorder them
```

All media files sit next to `index.html` at the root — no `images/` or `videos/` subfolders.

## Running locally

Just open `index.html` in a browser. No server or build tools needed.

## Deploying

**Vercel:** import this repo (or drag-and-drop this folder) at vercel.com/new — it auto-detects
a static site, no config needed.

**GitHub Pages:** Settings → Pages → Deploy from branch → `main` → `/ (root)`. The site will be
live at `https://<username>.github.io/<repo-name>/`.

## Editing content

See `MEDIA-GUIDE.md` for exactly which file feeds which part of the page, and how to add,
replace, or reorder images and videos.
