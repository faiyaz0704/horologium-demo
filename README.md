# HOROLOGIUM — Static Demo Website

A fully connected, responsive static demo built from the Horologium luxury watch theme. No backend, no PHP, no WordPress required — this uploads directly to any static host (Cloudflare Pages, Netlify, GitHub Pages, etc.).

## Running locally

Open `index.html` or `horologium.html` in any browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000/horologium.html`.

## Pages

| Page | File | Purpose |
|---|---|---|
| Home | `horologium.html` | Complete 11-section homepage with Hero carousel, Category marquee, 12-tile Collection Grid, Z-pattern showcase, New Arrivals, Casio Brand Spotlight, Store CTA, Product Spotlight, Testimonials, Brand Statement, and Trust Strip |
| Shop | `shop.html` | Full product grid — 14 watches, live category filter + price/newest sort |
| Product | `product.html` | Product detail — gallery, zoom, variants, reviews, tabs, related items |
| About | `about.html` | Brand story, narrative blocks, values grid, closing statement |
| Contact | `contact.html` | Contact form with client-side validation, business hours, FAQ accordion |
| Terms | `terms.html` | Terms & policies with jump-to-section TOC and Warranty Policy |
| Track Order | `track-order.html` | Order-tracking lookup with 5-step visual progress stepper |

All internal links form a closed graph — every page reaches every other page through the header nav, footer, or in-page CTAs.

## Homepage Sections (11-Section Architecture)

1. **Hero Carousel** — Dual slide transitions with Ken Burns drift, counter, and timed indicators
2. **Category Slider** — Marquee animation with category pills and piece counts
3. **Collection Grid** — 12 brand tiles (Orient, Breitling, Seiko, Hublot, TAG Heuer, Tissot, Casio, Citizen, Fossil, Longines, Omega, Rolex) with hover zoom and filtered links
4. **Collection (Z-Pattern)** — Staggered editorial product pairs with gold hover accents
5. **New Arrivals** — 4-column product grid featuring 8 timepieces on an ivory backdrop
6. **Brand Spotlight** — Full-width Casio exploded diagram banner with curated brand products
7. **Store CTA** — Showroom location, address, Google Maps directions, and shop CTA
8. **Product Spotlight** — Editorial feature block for Audemars Royal Oak
9. **Testimonials** — Client reviews with 5-star SVGs and quotes
10. **Brand Statement** — Centered atelier philosophy quote
11. **Trust Strip** — 4 trust badges (Authenticated, Secure Payment, Free Delivery, 2-Year Warranty)

## Assets

`assets/images/` holds all photography and imagery:
- `collections/` — 12 brand collection tile images (Orient, Breitling, Seiko, Hublot, TAG Heuer, Tissot, Casio, Citizen, Fossil, Longines, Omega, Rolex)
- `brand-spotlight-casio.jpg` — Casio exploded-diagram banner (1920×600)
- `hero-slide-1.jpg`, `hero-slide-2.jpg`, `hero.png` — Homepage hero carousel
- `watch-royal-oak.jpg`, `watch-aurora.jpg`, `watch-chronographe.jpg`, `watch-tourbillon.jpg`, `watch-vetriano.jpg`, `watch-a.png`, `product1.png`–`product6.png` — Watch photography

## What's Functional

- Full navigation across all 7 pages (header + footer + in-page CTAs)
- Dismissible promo announcement bar with session memory
- Tourbillon mechanical loader animation
- Mobile hamburger menu on every page
- Shop grid live category filtering and sorting
- Product gallery thumbnail switching, zoom overlay, variant selection, tabs, quantity stepper
- Contact form client-side validation
- Scroll reveal animations with `IntersectionObserver` and reduced-motion fallback
- Fully responsive from ~1440px down to ~360px
