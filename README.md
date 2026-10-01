# Leaside Pilates — Landing Page

A single-page site for Leaside Pilates (Toronto). Plain HTML/CSS/JS, no build step.

## Files
- `index.html` — the landing page
- `assets/` — images and the hero video
- `robots.txt`, `sitemap.xml` — SEO files

## Publish with GitHub Pages
1. Create a new repository and upload everything in this folder (keep `index.html` at the repo root).
2. In the repo: **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick the `main` branch and the `/ (root)` folder, then **Save**.
4. Wait a minute; your site appears at `https://<username>.github.io/<repo>/`.

## Using your own domain (leasidepilates.com)
1. In **Settings → Pages → Custom domain**, enter `www.leasidepilates.com` and save (this adds a `CNAME` file).
2. At your domain registrar, add a CNAME record pointing `www` to `<username>.github.io`.
3. Once it verifies, tick **Enforce HTTPS**.

## Before launch — things to finish
- **Book buttons**: the "Book Now" / "Explore" links point to `#book`. Replace with your Momence booking URL.
- **Opening hours**: not yet in the page or schema — add them for local SEO.
- **Hours/coordinates in schema**: the JSON-LD has your name, address, phone, email and services; add `openingHoursSpecification` and (optionally) geo-coordinates if you want them.
- **Social image**: the Open Graph tags reference `https://www.leasidepilates.com/assets/hero.jpg` — correct once this is live on that domain.
- **Validate**: run the live URL through Google's Rich Results Test to confirm the LocalBusiness and FAQ schema.

## Note on the hero video
`assets/hero.mp4` (~7 MB) autoplays muted and loops, with `assets/hero-poster.jpg` shown while it loads and for anyone who prefers reduced motion. To use a still instead, delete the `<video>` element's `<source>` line, or replace the whole block with the `index.html` `<img>` fallback already inside it.

## Meta ads landing page (`intro.html`)
A dedicated, conversion-focused page for Meta (Facebook/Instagram) ad traffic.
- No site navigation — every CTA links straight to the Momence purchase page (https://momence.com/m/931146), opening in a new tab.
- Marked `noindex` so it won't show up in Google search (ad pages shouldn't compete with the main site).
- A sticky bottom CTA bar appears on mobile.

### Meta Pixel — ACTION REQUIRED
The Meta Pixel (ID 26238821305805814) is installed on BOTH `index.html` and `intro.html`.
1. No placeholder left to replace — it is live in the files.
2. The Pixel fires `PageView` automatically on load.
3. The first click on any CTA fires a `Lead` event (value 99.00 CAD, content_name "2 Weeks Unlimited Reformer $99"), then sends the visitor to Momence.
4. Verify with the Meta Pixel Helper browser extension, or in Events Manager → Test Events, once the page is live on a real URL (the Pixel won't register from a local file).

Point your Meta ad's destination URL at `.../intro.html`.
