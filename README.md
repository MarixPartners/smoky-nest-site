# The Smoky Nest

Website and local guide for **The Smoky Nest**, a short-term rental cottage in
Pigeon Forge, TN. Live at [thesmokynest.com](https://thesmokynest.com/).

A static multi-page site with no build step, no framework, and no dependencies.
Each page carries its own inline CSS and JavaScript.

## Pages
- `index.html` — property showcase, live availability, booking, contact, and the local guide
- `things-to-do-pigeon-forge.html` — attractions guide
- `restaurants-pigeon-forge.html` — dining guide
- `thanks.html` — contact form confirmation page (noindex)
- `check-in-card.html` — printable card for guests (not linked from the site)

## Other files
- `images/` — property photography, plus documented third-party guide images.
  See `images/guide/IMAGE-SOURCES.md` for the source and rights basis of every
  guide image; do not add a guide image without adding its provenance record.
- `sitemap.xml`, `robots.txt` — search engine directives
- `netlify.toml`, `deploy-headers/` — deploy configuration (see below)
- `CNAME`, `favicon.ico`, `apple-touch-icon.png`, `googlec425fee7cfaa22df.html`

## Third-party embeds
- Availability and booking requests are handled by embedded OwnerRez widgets,
  loaded from `app.ownerrez.com/widget.js`.
- The contact form uses Netlify Forms. No JavaScript is involved; submissions
  appear in the Netlify dashboard under Forms.

## Deployment
Hosted on Netlify, deployed from this repository. Pushes to `main` publish to
production automatically.

Branch deploys are enabled for `smoky-nest-v2`. `netlify.toml` gives non-production
contexts a build command that copies `deploy-headers/_noindexHeaders` to `_headers`,
so branch deploys and deploy previews return `X-Robots-Tag: noindex, nofollow`.
Production defines no such context and is unaffected.

## Updating
Edit the relevant HTML file and push. Update `sitemap.xml` `lastmod` when page
content changes.
