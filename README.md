# Charles Leaven — Profile & Reference

Static profile site intended for `https://info.charlesleaven.com/`.

## Architecture

- Plain semantic HTML + CSS
- No JavaScript runtime
- No database or backend
- Designed for Cloudflare Pages
- `ProfilePage` / `Person` JSON-LD
- Crawlable metadata, robots.txt and image-aware sitemap

## Local preview

```bash
python -m http.server 4173
```

Then open `http://localhost:4173`.

## Cloudflare Pages

Connect the GitHub repository to Cloudflare Pages.

For a zero-build static deployment:

- Production branch: `main`
- Build command: `exit 0`
- Build output directory: `.`

Then add `info.charlesleaven.com` under **Custom domains**.

## Important before production SEO test

The lead N4E image currently loads from the existing `charlesleaven.com` image URL so this working copy can render without duplicating an unavailable local asset.

Before requesting Google indexing, copy the original image into this repository at:

`images/charles-leaven-duduzane-zuma-ryan-singlehurst-n4e-durban.png`

Then replace the existing image URL in:

- `index.html` (`og:image`, JSON-LD and `<img src>`)
- `sitemap.xml`

with:

`https://info.charlesleaven.com/images/charles-leaven-duduzane-zuma-ryan-singlehurst-n4e-durban.png`

That local copy is important if the subdomain is being used as a clean test of how Google treats the image from an independent URL/context.
