# Store owner guide

## Edit catalog products and prices

1. Edit the existing entry in `data/games.js`; this file mirrors the deployed catalog and is the source of truth for titles, prices, source images, platform choices, and variants.
2. Keep the existing price values and image paths unless you intentionally update the source data. Use `null` only when the price is genuinely unknown.
3. Use only confirmed PS4/PS5 variants for products you want to display. The storefront filters out unsupported platform labels rather than converting them.
4. To update a source cover, replace the file at its existing path with a better original. The image build does not enlarge small source files.
5. GTA VI pricing and edition-specific covers are in `data/store-config.js`; its current source values are 500 DH for Standard and 649 DH for Ultimate Edition. Ultimate Edition uses the local 1280x720 asset `images/UltimateEdition_07_en_us_R04_Deliv.jpg`.

## Store and GTA VI settings

Edit `data/store-config.js`:

- `WHATSAPP_NUMBER`, `INSTAGRAM_URL`, `SHOP_HOURS`, and `PAYMENT_METHODS` control store contact details.
- `EVENT_MODE` enables or disables the GTA VI countdown/event treatment.
- `GTA6_RELEASE_ISO` sets the Morocco-time countdown date/time. Rockstar has not announced an exact unlock time; adjust this value if needed.
- `GTA6_HERO_IMAGE` points to the local cinematic hero art.
- `GTA6_PRODUCT` contains GTA VI's PS5 editions, prices, and source image paths.
- `TRADE_IN.enabled` controls the exchange inquiry section; `acceptedPlatforms` determines which PS4/PS5 choices appear.
- `TRADE_IN.termsByLanguage` is empty by default. Add owner-confirmed details per language only when exchange values, eligibility, or other terms are approved for publication. The page otherwise asks customers to confirm details on WhatsApp.

Configured store details: WhatsApp +212 636 059 783; Instagram @fchkal_digital; hours 11:00–00:00; payments CIH, Wafacash, PayPal, Cash Plus, and Tijarawafa.

## Trade-in / exchange inquiries

The current project and deployed homepage did not contain an earlier exchange flow to preserve. The homepage now provides a WhatsApp inquiry form: customers enter the game and platform they have, with optional details about the game/platform they want. It does not estimate values or promise eligibility. Confirm the exchange process and any applicable terms directly with the customer; configure owner-approved notes in `data/store-config.js` if they should be shown on the site.

## Add a customer review

1. Add one customer-approved photo directly inside `reviews/`.
2. Add one JSON object to `reviews/reviews.json` with the image filename and only approved details.
3. Set `verified` to `true` only for a purchase confirmed through WhatsApp. Do not invent names, ratings, or dates.
4. Run `npm run build` to generate responsive photo variants and embed the records.

See `reviews/README.md` for the JSON shape and consent guidance.

## Build, check, and publish

From the project folder, install dependencies once, then run:

```bash
npm install
npm run build
npm run qa
```

Deploy the project root to Netlify. The build generates the game pages under `games/`, the `_redirects` rules for `/game/<slug>`, `robots.txt`, and `sitemap.xml`. Check generated routes and WhatsApp links after deployment.
