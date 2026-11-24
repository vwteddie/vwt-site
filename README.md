# VWT Black Friday Landing Page

Static, mobile-first landing page (14306 Wicks Blvd, San Leandro, CA 94577 · 510-935-6111) for Vehicle Wrap Training LLC. No build step: upload the files to any host (Shopify page, Netlify, GitHub Pages, your current host).

| File | What it is |
|---|---|
| `index.html` | The Black Friday landing page |
| `thank-you.html` | Post-purchase page: confirmation, next steps, what to bring, calendar, map, bring-a-buddy |
| `privacy.html` | Privacy policy (needed for Meta ads). It's a template, so have it reviewed |
| `terms.html` | Terms and refund policy. **Your refund policy still has to be written in** |
| `public/images/class/` | Web-ready class photos (`-640.webp` for phones, `-1280.webp` for desktop). These are what the page loads |
| `public/images/brand/` | VWT logo (header, footer, all pages), browser tab icon, phone home-screen icon and the link-preview image `og-image.jpg` |
| `public/images/originals/` | Your full-size uploads (GPS location removed). The page doesn't load these |

## Fill these in before running ads

Everything lives in the `window.VWT` CONFIG block near the top of `index.html`:

1. **`pixelId`**: your Meta Pixel ID (numbers only). The pixel stays off until it's set.
2. **`links.tint` / `links.ppf` / `links.bundle` / `links.deposit` ($200 PPF deposit) / `links.bundleDeposit` ($500 bundle deposit)**: your new Shopify product URLs. Tint has no deposit link: it is paid in full. Until they're set, buttons scroll to the pricing section.
3. **`courses.ppf.regular` and `courses.bundle.regular`**: only use a price you've actually charged. Leave `null` and no strikethrough is shown.
4. **`classes`**: real dates and real seats left, e.g. `{ course: "tint", start: "2026-12-05", end: "2026-12-06", seatsLeft: 2 }`. Use only `"tint"` or `"ppf"`: Bundle students pick one of each at checkout, so the bundle has no dates of its own. These fill the **class calendar** and the "Next class · X of 4 seats left" line on each price card. Add `url:` to send that date to a specific Cowlendar product page; otherwise it uses the course link from `links`. Open the page with `?demo=1` to preview the calendar with sample dates (they never show without that).
5. **`heroVideo`**: a short, muted MP4 loop (aim for under 3 MB, 720p). It loads after the page appears, so it won't slow the first view.
6. **`gallery`**, **`graduates`**, **`eddiePhoto`** and **`eddieWork`**: your class photos are already in. To add more, make a `-640.webp` and `-1280.webp` copy in `public/images/class/` and add one line to the list. Eddie's photo is still needed.
7. **Reviews**: in `index.html`, search for `REVIEWS` and paste each review's text **word for word** from Google or your site. Cards with empty text show a dashed placeholder.
8. **FAQ**: the lunch answer and refund policy (search for `[YES/NO` and `[POLICY`).
9. **`terms.html`**: write your refund and reschedule policy.

## Tracking

| Event | Fires when |
|---|---|
| PageView | Page loads |
| ViewContent | Pricing cards scroll into view (once) |
| InitiateCheckout | Any buy, deposit or financing click |
| Lead | Any text, call or email click |
| Purchase | **On Shopify's own thank-you page.** Install the Shopify "Facebook & Instagram" app with the same Pixel ID. `thank-you.html` doesn't fire Purchase, so sales aren't counted twice. |

UTM parameters and `fbclid` from the ad URL are copied onto every checkout link automatically.

To send buyers to `thank-you.html`, add a link on Shopify's order status page, for example:
`thank-you.html?course=tint&start=2026-12-06&end=2026-12-07&label=Dec%206%E2%80%937`

## Countdown behavior

The countdown runs to **Nov 30, 2026, 11:59:59 PM PT** and doesn't reset. After it ends, the page switches to regular prices automatically: the countdown and strikethroughs are removed, and "Black Friday" wording changes to regular enrollment wording. Remember to **also** change the Shopify product prices after the deal ends.

## Class calendar + Cowlendar

Cowlendar runs inside Shopify, and I couldn't find a documented way to embed its widget on an outside site. So this page has its own calendar, and every "Book" button opens the Shopify product page where Cowlendar's date picker and checkout live.

1. In Shopify, set up each course product with Cowlendar (app embed turned on in your theme).
2. Paste those product URLs into `links.tint`, `links.ppf` and `links.bundle`, or into a class's `url:`.
3. Each time a seat sells, update `seatsLeft` (Cowlendar doesn't update this page automatically).

## After the page is hosted

Facebook and text-message link previews need full web addresses. Once you know the live URL, change the `og:image` line near the top of `index.html` to the full address, e.g. `https://vehiclewraptraining.com/public/images/brand/og-image.jpg`. The business info block (schema) under it assumes the site lives at vehiclewraptraining.com. Update those URLs if it's hosted somewhere else.
