# FCHKAL DIGITAL

Static, mobile-first PlayStation storefront for PS4 and PS5 games, PlayStation Plus, PSN gift cards, and exchange inquiries. Orders and exchange requests are handled through WhatsApp.

## Local preview and build

Requirements: Node.js and npm.

```bash
npm install
npm run build
npm run qa
```

Serve the project root with a local static server, such as VS Code Live Server, then open the local URL in a browser. The build generates responsive WebP files, game pages in `games/`, Netlify redirects for `/game/<slug>`, `robots.txt`, and `sitemap.xml`.

## Deploy on Netlify

The root `netlify.toml` configures Netlify to run `npm run build` from the project root and publish the project root (`.`). Netlify installs the `sharp` dependency from `package.json`; no environment variables are required. Keep the Base directory blank (the repository root) and deploy the directory containing this file, `index.html`, and `package.json`.

The project is a static HTML site, not a client-routed SPA. The build writes the existing `/game/<slug>` rewrites to `_redirects`, so no catch-all SPA fallback is needed.

## Data sources

- `data/games.js` — canonical deployed product titles, prices, source cover paths, and platform variants.
- `data/store-config.js` — contact information, hours, payment methods, GTA VI event settings, exchange platforms, and optional owner-confirmed terms.
- `reviews/reviews.json` and `reviews/` — approved review details and photos.
- `js/app.js` and `css/styles.css` — storefront behavior, translations, and design system.
- `scripts/build.mjs` and `scripts/images.mjs` — generated pages, crawl files, and responsive image variants.

Public product views are limited to confirmed PS4/PS5 options; unsupported catalog records remain unchanged and unpublished. See `OWNER-GUIDE.md` for editing instructions and `OWNER-TODO.md` for launch checks.
