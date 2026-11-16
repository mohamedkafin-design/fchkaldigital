# Storefront design and implementation

## Visual direction

- Premium dark gaming-store interface: charcoal surfaces, white typography, subtle violet lighting, restrained borders, and soft neon accents.
- Barlow Condensed italic headlines, Inter interface text, and Cairo Arabic text.
- The logo preserves its source artwork and proportions; screen blending helps it sit on the dark header without a hard black tile.
- Layout uses clear focus states, reduced-motion support, safe-area spacing, readable contrast, and RTL direction.

## Shopping experience

- Compact sticky header with brand, navigation, language, search, WhatsApp, and cart controls.
- Cinematic local-art hero with direct shopping and WhatsApp actions; GTA VI release event remains a separate countdown feature.
- PS5/PS4 selector, search, sorting, and equal-height cards with visible covers, platform and edition labels, price, primary WhatsApp action, cart action, and details link.
- PlayStation Plus, GTA VI cross-sell, PSN gift-card inquiry, offers, ordering details, payments, FAQ, and customer reviews remain available.
- A dedicated trade-in/exchange section collects the game and PS4/PS5 platform the customer has, plus an optional requested game/platform. It opens a prefilled WhatsApp inquiry without publishing invented prices or terms.
- The customer review gallery is data-driven and shows only entries in `reviews/reviews.json`.
- Dedicated `/game/<slug>` pages and Netlify routes are generated from the same catalog.

## Catalog and platform rules

- `data/games.js` retains the exact catalog from the deployed source, including original prices, image paths, statuses, and platform variants.
- Public rendering sanitizes platform choices to PS4/PS5 only. It never converts an unsupported product into a PlayStation product.
- GTA VI standard and Ultimate Edition use source prices of 500 DH and 649 DH, PS5 only. Standard uses its original cover; Ultimate now uses the matching local 1280x720 asset `images/UltimateEdition_07_en_us_R04_Deliv.jpg`, displayed without cropping.
- Unknown prices remain `null` and use a WhatsApp inquiry. Products requiring platform or availability confirmation use inquiry actions.

## Operations

- Contact, hours, payment methods, GTA VI release date, and event switch are in `data/store-config.js`.
- Trade-in visibility, accepted platforms, and optional language-specific terms are also configured in `data/store-config.js`; leave terms unset until confirmed by the owner.
- Reviews and customer images live in `reviews/reviews.json` and `reviews/`.
- `npm run build` generates game pages, route/crawl files, and responsive WebP output without enlarging source images; `npm run qa` checks generated pages and public platform claims.
- Keep `archive/` and `css - Copy/` unchanged.
