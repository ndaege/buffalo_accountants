Buffalo.Accountants website — deployment notes
================================================

Contents:
  index.html      Home page
  services.html   Services page
  contact.html    Contact page
  sitemap.xml     XML sitemap for search engines
  robots.txt      Crawler directives

Deployment:
- Each HTML file is fully self-contained (fonts, logo, styles inlined).
  No build step, no server-side code — upload to any static host
  (cPanel public_html, Netlify, Cloudflare Pages, S3, etc.).
- Upload all files to the site root so nav links (index.html,
  services.html, contact.html) resolve.
- Canonical URLs and sitemap assume the site is served at
  https://buffalo.accountants/ — if hosted elsewhere, update the
  <link rel="canonical">, og:url tags, and sitemap.xml accordingly.
- Optional: configure the server to serve index.html at "/" and
  consider rewriting /services and /contact to the .html files to
  match the canonical tags.

Contact: info@buffalo.accountants · +1-888-801-6424
