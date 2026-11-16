# Image report

## Image pipeline

`npm run build` uses the existing `sharp` dependency to write `images/covers/<slug>.webp` and responsive WebP candidates at available widths up to 900 pixels. Only PS4/PS5 storefront products are optimized for public use. The script never enlarges a source. Cards and generated game pages use `srcset` with the original image as a fallback. Review photos are optimized only after an approved JSON entry is added.

## Missing owner-provided assets

- The cinematic hero `images/gta6/hero.jpg` is available at 1280x720. It is used as a wide hero; no separate mobile crop is required by the current layout.
- `images/brand/fchkal-store-logo.png` is available but is an opaque square, not the transparent logo requested. CSS screen blending reduces its hard black edges; a transparent original would improve the header.
- No review images are published because `reviews/reviews.json` is empty.
- GTA VI Ultimate Edition now uses the existing matching `images/UltimateEdition_07_en_us_R04_Deliv.jpg` source (1280x720). The product card and detail view preserve its landscape ratio; it is not enlarged or cropped.
- The previous 225x225 `images/Grand Theft Auto VI Ultimate Edition (GTA 6 UE).jpg` source remains on disk for recovery but is no longer referenced by active product data or generated pages.

## Catalog sources below 900x1200

These are source dimensions, not upscaled output. Replace them with larger originals when available:

| File | Dimensions |
|---|---:|
| `images/ARC Raiders.jpg` | 736x981 |
| `images/Assassin’s Creed Black Flag Resynced.jpg` | 736x981 |
| `images/Black Myth Wukong.jpg` | 736x1104 |
| `images/Call of Duty Modern Warfare II.jpg` | 736x918 |
| `images/Crimson Desert.jpg` | 736x1104 |
| `images/EA Sports FC 26.jpg` | 736x920 |
| `images/EA SPORTS FC™ 27 ULTIMATE.jpg` | 736x981 |
| `images/EA SPORTS FC™ 27.jpg` | 736x1308 |
| `images/Elden Ring.jpg` | 736x1104 |
| `images/Far Cry® 6 Deluxe Edition.jpg` | 736x981 |
| `images/Forza Horizon 5.jpg` | 600x900 |
| `images/Ghost of Tsushima.jpg` | 600x900 |
| `images/God of War Ragnarok.jpg` | 735x1067 |
| `images/Grand Theft Auto V (GTA 5).jpg` | 736x902 |
| `images/Grand Theft Auto VI (GTA 6).jpg` | 736x849 |
| `images/It takes two + a way out.png` | 745x750 |
| `images/Mafia The Old Country.jpg` | 600x900 |
| `images/Marvel’s Wolverine.jpeg` | 764x934 |
| `images/Marvel's Spider-Man 2.jpg` | 736x981 |
| `images/Minecraft.jpg` | 300x450 |
| `images/NBA 2K27 Deluxe Edition.jpg` | 736x981 |
| `images/NBA 2K27.jpg` | 736x919 |
| `images/PlayStation Plus Essential 12 mois.jpg` | 736x736 |
| `images/PlayStation Plus Essential 3 mois.jpg` | 181x279 |
| `images/PlayStation Plus Extra 12 mois.png` | 751x749 |
| `images/PlayStation Plus Extra 3 mois.jpg` | 554x554 |
| `images/PRAGMATA.jpg` | 736x1104 |
| `images/Red Dead Redemption 2.jpg` | 685x1024 |
| `images/Resident Evil 4.jpg` | 1080x1080 |
| `images/Resident Evil Requiem.jpg` | 736x920 |
| `images/The Last of Us Part II.jpg` | 736x1104 |
| `images/UFC™ 6.jpg` | 362x453 |
| `images/UNCHARTED 4 A Thief’s End & UNCHARTED The Lost Legacy Digital Bundle.jpg` | 736x1104 |
| `images/WWE 2K25.jpg` | 736x920 |
| `images/WWE 2K26 Édition standard.jpg` | 425x535 |

The GTA VI hero source is landscape at 1280x720, appropriate for the cinematic hero. Product covers remain at their original source paths and ratios.
