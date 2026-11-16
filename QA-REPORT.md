# QA report

## Verified

- Restored `data/games.js` from the deployed catalog and confirmed its SHA-256 matches the downloaded source. All catalog image paths exist locally.
- Preserved source product prices, platform variants, and image paths; public product rendering and generated pages are restricted to PS4/PS5.
- Removed the obsolete GTA V page that incorrectly presented a PC-only source product as PS5. QA now detects generated pages for unpublished products.
- Ran `npm run build`: generated 25 PS4/PS5 game pages and responsive image variants.
- Ran `npm run qa` after the latest changes: passed for all 25 public game pages, source prices and image paths, GTA VI Ultimate artwork configuration, and trade-in checks.
- Checked 360, 390, 768, 1024, 1280, and 1440 px in EN, FR, ES, and AR (24 viewport/language combinations): no horizontal overflow; Arabic uses RTL.
- Tested PS4 filtering and FC 27 PS4 at 299 DH, cart quantity/subtotal, WhatsApp prefill, GTA VI countdown states, empty reviews, and all five payment methods.
- Tested the trade-in form's required-field validation and WhatsApp inquiry in EN, FR, ES, and AR, including optional wanted-game details; all four messages targeted +212 636 059 783.
- Tested GTA VI Ultimate Edition on its dedicated page and homepage card: 649 DH, PS5, correct WhatsApp message, and the local 1280x720 artwork without the obsolete square cover reference.
- No browser console or page errors were observed during the checked interactions.

## Owner follow-up

- Deploy and verify Netlify rewrites, canonical URLs, and generated pages on the live site.
- Run Lighthouse and test on physical mobile devices, including Instagram's in-app browser.
- Provide a transparent logo and higher-resolution replacements for the source images listed in `IMAGE-REPORT.md`. The previous 225x225 GTA VI Ultimate cover is no longer used.
- Confirm compatibility and availability for products marked `review` in `data/games.js`.
- The build dependency audit reports a high-severity advisory for `sharp` versions below 0.35.5. `sharp` is build-only; review an upgrade before publishing the next dependency change.

The live Netlify site was not changed. Its current homepage is an older version that does not match this local project. This is a local QA report, not a live-deployment, Lighthouse, physical-device, or Instagram in-app browser sign-off.
