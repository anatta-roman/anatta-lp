# Anatta · Shopify design landing page

Static, self-contained build of the design landing page (Full Page v3).
No build step, so it deploys as-is.

## Structure
```
index.html                 the whole page (markup, styles, interaction logic)
vendor/petite-vue.iife.js  tiny rendering library (petite-vue 0.4.1, MIT), bundled locally
assets/                    promo video, poster, case images, logos
vercel.json                clean URLs + long-cache headers for /assets
```

## Run locally
Any static server works, for example:
```
npx serve .
# or
python3 -m http.server 8000
```
Then open http://localhost:8000. Opening index.html straight from disk (file://) may block the video, so use a server.

## Deploy to Vercel via GitHub
1. Create a new GitHub repo and push this folder's contents to it (index.html at the repo root).
2. In Vercel: **Add New → Project → Import** the repo.
3. Framework preset: **Other**. Build command: *(leave empty)*. Output directory: **./** (root).
4. Deploy.

Or with the Vercel CLI, from this folder: `npx vercel` (then `npx vercel --prod`).

## Notes
- Fonts load from Google Fonts (Newsreader, Hanken Grotesk, IBM Plex Mono) as stand-ins for Publico and Calibre.
- The promo video is 14.7 MB (720p), well inside GitHub's and Vercel's limits.
- Layout is designed for desktop (1280px and up); a mobile pass is still to do.
- Click counts in the case-study click maps are illustrative placeholders.
- Vuori and Rothy's growth figures come from the confidential proposal deck: confirm before publishing.
