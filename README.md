# Window Installation Toronto

Rank-and-rent lead-gen site for window installation in Toronto. Single-page app: one `index.html` with client-side routing, plus `sitemap.xml`, `robots.txt`, and `_redirects`.

Site display name: Window Installation Toronto. No invented brand or company name.

## Pages (6 URLs, as specified)

- `/` — Home
- `/window-installation-toronto/` — Main service page
- `/fogged-windows-between-panes/` — Guide
- `/drafty-windows-winter/` — Guide
- `/how-long-does-window-installation-take/` — Guide
- `/vinyl-vs-wood-vs-fiberglass-windows/` — Guide

That is 1 home page, 1 service page, and 4 guide pages — the 6 slugs specified for this site. All 6 are listed in `sitemap.xml`.

## Phone number — SITE_CONFIG

The phone number lives in ONE place only: the `SITE_CONFIG` JavaScript object at the top of `index.html` (the script block just before the main app script). It holds the display number and the tap-to-call link.

Every phone display on the site — header, hero, footer, service page, and guides — reads from `SITE_CONFIG`. Do not hard-code the number anywhere else in the HTML, copy, or comments. To change the number for a renter, edit `SITE_CONFIG` only and redeploy.

The callback request form was removed Nov 20, 2026 — the site's contact path is the call button.

## Content rules

- Price factors only. The firm price is confirmed after inspection only.
- No invented reviews, testimonials, company names, or phone numbers.
- Homeowner-first, plain second-person language.

## Photos

Three free Pexels stock photos. They are embedded directly in `index.html` as data URIs so they show in the file preview and on every page route — no separate image files are needed for the site to work. The `images/` folder holds the originals as the source of truth if a photo ever needs swapping (re-embed after replacing). Illustrative only — not the renter's own work.

- `installer-fitting-window.jpg` — worker fitting a new window frame (home hero). Source: https://images.pexels.com/photos/5691544/pexels-photo-5691544.jpeg
- `new-window-at-dusk.jpg` — new white window in an older house at dusk (service page). Source: https://images.pexels.com/photos/12654941/pexels-photo-12654941.jpeg
- `bright-living-room-windows.jpg` — bright living room with large windows ("What we see in Toronto homes"). Source: https://images.pexels.com/photos/6527029/pexels-photo-6527029.jpeg

## Deploy — GitHub + Cloudflare Pages

1. Create a GitHub repo and push these files to it (all files at the repo root).
2. In Cloudflare, create a Pages project and connect that GitHub repo.
3. Build settings: no build command, output directory is the repo root (the site is static HTML).
4. Add the custom domain `clearpanetoronto.ca` in the Pages project, and point the domain's DNS to Cloudflare as shown in the Pages setup.
5. Confirm the site loads, the 6 content URLs resolve, and `sitemap.xml` and `robots.txt` load.
6. Submit the sitemap in Google Search Console once the domain is live.
