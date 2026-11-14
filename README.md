# Ansh – Portfolio

Static site: no build step, no server code. Files:

- `index.html` – the whole site (HTML, CSS, JS inline)
- `assets/three.min.js` – three.js r128, self-hosted (no CDN dependency)
- `favicon.svg`, `og-image.png` – icon and link-preview image
- `404.html`, `robots.txt`, `sitemap.xml`
- `_headers`, `netlify.toml`, `vercel.json` – security headers and caching for Netlify / Vercel
- `.nojekyll` – needed for GitHub Pages

## Before you deploy

The URL `https://ansh-dev11.github.io/` is used in `index.html` (canonical, og:url, og:image, JSON-LD),
`robots.txt` and `sitemap.xml`. If your site lives on another domain or repo path, find-and-replace it everywhere.
If it is a project page such as `https://ansh-dev11.github.io/portfolio/`, include `/portfolio/` in the og:image URL.

## Deploy

**GitHub Pages** – push these files to the root of a repo named `Ansh-dev11.github.io`
(or any repo), then Settings → Pages → Deploy from branch → `main` / root.

**Netlify** – drag the folder onto app.netlify.com/drop, or connect the repo (publish directory `.`).

**Vercel** – `vercel` in this folder, or import the repo (framework: Other).

## Test locally

    python3 -m http.server 8080

Open http://localhost:8080. Do not open `index.html` by double-click if you want to test the 404 page or headers.

## Notes

- Project pages use hash routes (`#car-price`, `#movie-match`, `#maison-catch`, `#terrain-trek`), so they work on any static host and the browser back button returns one step.
- A Content-Security-Policy is set in a `<meta>` tag and in the header files. If you add analytics or new external scripts, extend `script-src` and `connect-src`.
- Google Fonts are loaded from fonts.googleapis.com; the page falls back to system fonts if they fail.
