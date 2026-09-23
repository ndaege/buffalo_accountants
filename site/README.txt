Buffalo.Accountants website — deployment notes
================================================

Contents:
  index.html        Home page
  services.html     Services page
  contact.html      Contact page

  site.css          Shared styles for every page: embedded Raleway
                    fonts, base styles, header/nav, buttons,
                    call-to-action band, footer
  index.css         Home page styles
  services.css      Services page styles
  contact.css       Contact page styles

  index.js          Page scripts (generated runtime; do not edit)
  services.js
  contact.js

  logo.svg          Site logo (header)
  logo-dark.svg     Logo variant for dark backgrounds
  img/              Photos and platform logos

  sitemap.xml       XML sitemap for search engines
  robots.txt        Crawler directives
  _redirects        Clean-URL rewrites (Netlify / Cloudflare Pages)

Styles:
- No inline styles. Every page loads site.css first, then its own
  page stylesheet (e.g. index.css). Keep that order: page sheets
  override shared rules where they overlap.
- Put anything used on more than one page in site.css; put
  single-page styles in that page's sheet.
- Fonts are embedded in site.css, so there are no external font
  files to upload.

Deployment:
- No build step, no server-side code — upload to any static host
  (cPanel public_html, Netlify, Cloudflare Pages, S3, etc.).
- Upload everything above to the site root, keeping the img/ folder,
  so stylesheet, script and image paths resolve.
- Nav links point to clean URLs (/, /services, /contact). The
  _redirects file maps these to the .html files on Netlify and
  Cloudflare Pages. On other hosts, set up equivalent rewrites
  (e.g. .htaccess on cPanel) and serve index.html at "/", or the
  Services and Contact links will 404.
- Canonical URLs and sitemap assume the site is served at
  https://buffalo.accountants/ — if hosted elsewhere, update the
  <link rel="canonical">, og:url tags, and sitemap.xml accordingly.

Contact: info@buffalo.accountants · +1-888-801-6424
