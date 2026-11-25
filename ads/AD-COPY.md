# Black Friday Meta / Instagram ads

Every price and claim here comes from the landing page (`index.html`). The deal ends **Mon, Nov 30, 2026, 11:59 PM PT**. Turn the ads off by then.

## Images

| Ad | Feed (FB + IG feed, 1080×1350, 4:5) | Stories / Reels (1080×1920, 9:16) |
|---|---|---|
| 1. Bundle deal | `vwt-bf-1-bundle-deal-feed-4x5.png` | `vwt-bf-1-bundle-deal-story-9x16.png` |
| 2. Course menu | `vwt-bf-2-course-menu-feed-4x5.png` | `vwt-bf-2-course-menu-story-9x16.png` |
| 3. Graduates | `vwt-bf-3-graduates-feed-4x5.png` | `vwt-bf-3-graduates-story-9x16.png` |

In Ads Manager, upload the feed image, then under **Placements → Stories & Reels** swap in the 9:16 version of the same ad. On the story versions, all text is kept clear of the top 14% and bottom 20% of the image, where Instagram's buttons and caption sit.

To change text or prices: edit `src/ad.html`, open it in a browser with `?ad=1&fmt=feed` (or `ad=2|3`, `fmt=story`), and screenshot the 1080-wide frame.

## Copy

**Call to action button:** `Book Now` (or `Shop Now`)
**Website URL:** your landing page, with UTMs, e.g. `…/?utm_source=meta&utm_medium=paid&utm_campaign=bf2026&utm_content=bundle`. The page copies these onto every checkout link.

### Ad 1: Bundle deal
**Primary text**
> 🔥 Black Friday: 45% off the Film Pro Bundle.
>
> Learn window tint AND clear & color PPF hands-on from a 16-year pro, right here in San Leandro.
>
> ✅ Only 4 students per class, so you get real one-on-one time
> ✅ $1,297 (reg. $2,341). You save $1,044
> ✅ Reserve with $500 and pick any class date through 2027
>
> Ends Cyber Monday at midnight. Seats are limited 👇

**Headline:** Tint + PPF Bundle: 45% Off
**Description:** Ends Cyber Monday · San Leandro, CA

### Ad 2: Course menu
**Primary text**
> Black Friday course sale is live 🚗
>
> 🎯 2-Day Window Tint: $497 (reg. $895)
> 🎯 3-Day Clear & Color PPF: $997 (reg. $1,446)
> 🏆 Film Pro Bundle (both): $1,297 (reg. $2,341)
>
> Hands-on training with a max of 4 students per class. Lock in the price now and use it on any class date through 2027.
>
> Sale ends Cyber Monday, Nov 30.

**Headline:** Tint Course From $497
**Description:** Black Friday pricing ends Nov 30

### Ad 3: Graduates
**Primary text**
> These are our students, not stock photos 👊
>
> Every one of them learned window tint and PPF hands-on at Vehicle Wrap Training in San Leandro. Small classes (only 4 students), a 16-year pro instructor, and real cars every day.
>
> ⭐️⭐️⭐️⭐️⭐️ 41 Google reviews
>
> Black Friday: up to 45% off. Tint starts at $497, and the Tint + PPF bundle is $1,297 (reg. $2,341). Ends Cyber Monday.

**Headline:** Learn Tint & PPF in Small Classes
**Description:** Up to 45% off through Cyber Monday

## Last-day version (Nov 30)
Swap the first line of any primary text for:
> ⏰ LAST DAY: Black Friday pricing ends tonight at 11:59 PM PT.

## Before you launch
- The photos show real students. If anyone pictured hasn't agreed to be in an ad, get their OK first (being on the website isn't the same thing).
- "Reg." prices should be prices you've actually charged. The site's notes say the same.
- Meta ads are reviewed against the landing page, so keep these prices matched to `index.html` and Shopify.
