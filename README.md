# HOROLOGIUM — Static Demo Website

A fully connected, responsive static demo built from the seven Horologium prototype
pages. No backend, no PHP, no WordPress required — this uploads directly to any
static host (Cloudflare Pages, Netlify, GitHub Pages, etc.).

## Running locally

Open `horologium.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/horologium.html`.

## Pages

| Page | File | Purpose |
|---|---|---|
| Home | `horologium.html` | Hero carousel, collection preview, brand spotlight |
| Shop | `shop.html` | Full product grid — 14 watches, live filter + sort |
| Product | `product.html` | Product detail — gallery, variants, reviews, related items |
| About | `about.html` | Brand story |
| Contact | `contact.html` | Contact form with client-side validation |
| Terms | `terms.html` | Terms & policies, with jump-to-section TOC |
| Track Order | `track-order.html` | Simulated order-tracking lookup |

All internal links form a closed graph — every page reaches every other page
through the header nav, footer, or in-page CTAs.

## Assets

`assets/images/` holds the real photos you supplied, renamed to describe what
they show:

- `watch-royal-oak.jpg`, `watch-aurora.jpg`, `watch-chronographe.jpg`,
  `watch-tourbillon.jpg`, `watch-vetriano.jpg` — the five distinct watch photos
- `watch-royal-oak-dial.jpg`, `watch-royal-oak-crown.jpg`, `movement-macro.jpg` —
  detail crops used in the product gallery (see limitations below)
- `hero-slide-1.jpg`, `hero-slide-2.jpg` — homepage hero carousel

## Known limitations (be upfront about these with a client)

1. **Product gallery is a composite, not a real 4-angle shoot.** You supplied
   one photo per watch, not multiple angles of the same watch. The product
   page's "Audemars Royal Oak" gallery uses the real hero photo plus two
   cropped details from it and the macro shot as a "movement" view — it reads
   as coherent, but it's not four genuine photos of one physical watch.
2. **One product template, many product names.** The site has 20 named watches
   across the homepage and shop grid but only one product detail page. Every
   product card and every "related product" link routes to the same
   `product.html`. Fine for a design demo; a production build needs either a
   templated product page per SKU or a real catalog data source.
3. **Five real photos, twenty product cards.** Photos are reused/cycled across
   cards with different names — expected for a demo, but a client should know
   the catalog isn't fully shot yet.
4. **"Warranty Policy" has no page.** Footer links to it are left as `#`
   since no warranty content was provided in the prototype set.
5. **Cart, wishlist, and tracking are simulated.** Add-to-cart increments a
   counter with no persistence or checkout; order tracking returns one fixed
   sample result regardless of input; nothing is sent anywhere. All of this is
   labelled and scoped in the code comments as demo-only.
6. **Fonts and analytics load from Google Fonts (remote).** No other external
   dependencies are used.

## What's genuinely functional (not simulated)

- Full navigation across all 7 pages, header + footer + in-page CTAs
- Mobile hamburger menu on every page, including `product.html` (had no
  mobile menu at all in the original prototype — added one)
- Shop grid filtering and sorting (category filters, price sort)
- Product gallery image/thumbnail switching, click-to-zoom, variant selection,
  quantity stepper, tabs, wishlist toggle
- Contact form client-side validation (required fields, email format)
- Responsive layout from ~1440px down to ~360px on every page
