# Anatta · Shopify design landing page

Static, self-contained build of the design landing page (Full Page v4).
No build step, so it deploys as-is.

## Sections
1. Hero: headline with the Shopify Platinum Partner badge and the promo reel (grows to full screen on scroll)
2. Case studies: AG1, Vuori, Dollar Shave Club, True Botanicals, Rothy's (animated UI bentos, click maps)
3. Industries: Health & Wellness selected by default
4. Unicorn stories: AG1, Vuori, Rothy's, SmartyPants partnership timelines
5. How we can help
6. How we design: process steps and the "we operate here" diagram (builds on scroll)
7. What clients say
8. Investment

## Structure
```
index.html                 the whole page (markup, styles, interaction logic, embedded brand fonts)
vendor/petite-vue.iife.js  tiny rendering library (petite-vue 0.4.1, MIT), bundled locally
assets/                    promo video (720p, 7.3 MB), poster, case images, logos
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
1. Push this folder's contents to your GitHub repo (index.html at the repo root). To update the existing repo, replace all files, and delete the old `assets/4cab8c….mp4` and `assets/8b16f8….jpg` if they are still there.
2. In Vercel: **Add New → Project → Import** the repo (or, if it is already connected, the push redeploys automatically).
3. Framework preset: **Other**. Build command: *(leave empty)*. Output directory: **./** (root).
4. Deploy.

Or with the Vercel CLI, from this folder: `npx vercel` (then `npx vercel --prod`).

## Accessibility
Built to WCAG 2.1 AA: text contrast checked on every background, 44px+ touch targets, keyboard-reachable controls with visible focus, labelled regions and images, pause controls for looping motion, and `prefers-reduced-motion` respected throughout.

## Before going public
- Fonts: Publico Banner and Calibre are embedded from desktop OTFs. Confirm Anatta's licences cover web embedding (Commercial Type, Klim).
- Content from the confidential proposal deck needs marketing sign-off: Vuori and Rothy's growth figures, the Unicorn stories timelines and lists, and the growth multiples (AG1 50×, Rothy's 220×, SmartyPants 6×+).
- Click counts in the case-study click maps are illustrative placeholders.
- "Schedule a time" buttons still need their destination link.
- Layout is designed for desktop (1280px and up); the mobile pass is in progress.
