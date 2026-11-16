# Storefront audit

## Architecture and source of truth

- The project is a static HTML/CSS/JavaScript storefront. `data/games.js` is the catalog; `data/store-config.js` holds store and event settings; `scripts/build.mjs` generates game pages, image variants, sitemap, robots, and Netlify routes.
- The deployed catalog was previously restored byte-for-byte and its prices, titles, platform records, and image paths verified. For the requested GTA VI Ultimate artwork upgrade, only that product's image path now points to the higher-resolution local original; catalog titles and prices remain unchanged.
- Public catalog and generated pages expose confirmed PS4/PS5 options only. Unsupported catalog records remain unmodified and unpublished.
- Orders and contact use WhatsApp. The cart and product details retain their existing local-store behavior; no payment processing or order-success claim was added.
- Reviews are driven by `reviews/reviews.json`; the current file contains no published review records.

## Pre-change audit findings

- No Trade-in/Exchange section or implementation existed in the current homepage, project source, `archive/`, `css - Copy/`, or the currently deployed homepage. There was no exchange form, process, or existing WhatsApp message to preserve.
- The homepage now has a configurable PS4/PS5 exchange inquiry. It requests the game/platform the customer has and optionally the game/platform they want, then asks the store to confirm possible options directly on WhatsApp. It displays no exchange price, valuation, eligibility promise, or guarantee.
- The active GTA VI Ultimate Edition source was 225x225. A local 1280x720 Ultimate Edition image with matching artwork was present; the product now uses that asset at its native aspect ratio. The older square source is retained but no longer referenced by active storefront data.
- The previously deployed homepage is a different/older version and still advertises PC, includes unsupported testimonial claims, and does not reflect this local redesign. No live changes were made.

## Current implementation

- Premium dark gaming storefront with compact navigation, cinematic hero and GTA VI event, PS4/PS5 selection, search, sorting, visible prices, cart, PlayStation Plus, PSN gift-card inquiries, offers, ordering, payment, FAQ, and reviews.
- Dedicated game pages are generated from the same product data. Netlify route rules target `/game/<slug>`.
- Store UI and the new exchange form support EN/FR/ES/AR; Arabic uses RTL.
- Contact, hours, payment methods, event date, exchange platform choices, and optional language-specific exchange details are configurable.
- `archive/` and `css - Copy/` were not modified.

## Remaining verification

- The latest `npm run build` and `npm run qa` passed for all 25 public product pages, source prices and image paths, and trade-in/GTA VI configuration checks.
- Browser checks covered 24 viewport/language combinations, required-field validation and all four trade-in WhatsApp translations, plus the GTA VI Ultimate edition price, artwork, and order message. See `QA-REPORT.md` for scope and details.
- Live Netlify validation, Lighthouse, physical-device testing, and Instagram in-app browser testing remain owner follow-ups. The live site was not changed or deployed.
- The logo is opaque rather than transparent; a transparent original would improve the header. Other low-resolution source covers are listed in `IMAGE-REPORT.md`.
