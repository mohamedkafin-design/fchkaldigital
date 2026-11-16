# Approved storefront direction

Build FCHKAL DIGITAL as a premium, conventional gaming e-commerce store inspired by the supplied gaming-store references. Do not use an Instagram-profile layout, social post cards, or story-circle navigation.

## Required design

- Dark charcoal gaming interface with subtle violet highlights, white type, restrained neon lighting, and modern gaming typography.
- Compact header, cinematic local-art hero, PS4/PS5 selector, product-first grid, and clear responsive shopping controls.
- Product cards show existing artwork, confirmed platform and edition, exact source price in DH, and a full-width WhatsApp purchase action. Search, sorting, cart, and details remain accessible.
- Keep useful PlayStation Plus, PSN gift-card inquiry, offers, ordering, payment, FAQ, and review sections.
- Include a configurable trade-in/exchange inquiry that collects the user's current game and platform plus an optional requested game/platform. Use WhatsApp to confirm terms; never invent values, eligibility, or guarantees.
- Use the existing local `images/UltimateEdition_07_en_us_R04_Deliv.jpg` for GTA VI Ultimate Edition and preserve its 16:9 art without cropping.

## Data integrity

- `data/games.js` is the canonical deployed catalog. Keep every original title, price, image path, and platform variation.
- Never convert PC/other-platform records into PlayStation products. Only verified PS4/PS5 choices may appear publicly; unsupported source entries remain unpublished until corrected.
- Do not invent prices, descriptions, stock, reviews, names, ratings, or release details. Missing prices should prompt a WhatsApp inquiry.
- Use only local project artwork. Never hotlink or scrape random images.

## Store settings and language

- WhatsApp +212 636 059 783; Instagram @fchkal_digital; hours 11:00–00:00.
- Payments: CIH, Wafacash, PayPal, Cash Plus, Tijarawafa.
- Support English, French, Spanish, and Arabic with correct RTL behavior.
- Keep the independent-reseller disclaimer in all four languages.

## Quality

- Preserve the cart, correct prefilled WhatsApp messages, safe-area spacing, accessible focus, reduced-motion behavior, and mobile-first layout.
- Test 360, 390, 768, 1024, 1280, and 1440 px in all four languages. Verify each public product's price, platform, source cover, and order link.
- Update `AUDIT.md`, `DESIGN-PLAN.md`, `IMAGE-REPORT.md`, `OWNER-GUIDE.md`, `OWNER-TODO.md`, and `QA-REPORT.md` as the implementation changes.
