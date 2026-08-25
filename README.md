# BlackButWhyte

The public page for **BlackButWhyte**, a natural history wall art shop on Etsy. It carries
the shop blurb and the privacy policy for the shop and its private Pinterest integration.

Plain HTML with inline CSS. No build step, no framework, no dependencies, no third party
requests. The folder you see is exactly what gets served.

---

## The link to give Pinterest

Pinterest's developer app asks for a privacy policy URL. Once the site is deployed, that is:

```
https://blackbutwhyte.netlify.app/#privacy
```

The policy is a section of the single page, so the `#privacy` anchor lands directly on it.

---

## Deploying it (Netlify, free)

1. Go to [app.netlify.com](https://app.netlify.com), then **Add new site**, then
   **Import an existing project**, then **GitHub**, then pick this repository.
2. Build command: leave it **empty**. Publish directory: `.` — the `netlify.toml` in this
   repo already says this, so it should fill itself in.
3. Deploy. You get a random name like `curious-fox-a1b2c3.netlify.app`.
4. Go to **Site configuration**, then **Site details**, then **Change site name**, and type
   `blackbutwhyte`. Your link becomes `https://blackbutwhyte.netlify.app`.

Every `git push` to `main` redeploys automatically. HTTPS is issued for you.

If the name `blackbutwhyte` is already taken on Netlify, pick the next closest one and
update the three URLs in `index.html` (`canonical` and `og:url`), plus `robots.txt` and
`sitemap.xml`, to match.

### Alternative: Cloudflare Pages

Same idea. Connect the repo at [dash.cloudflare.com](https://dash.cloudflare.com), then
Workers and Pages, then Create, then Pages, then Connect to Git. Framework preset: **None**.
Build command: empty. Output directory: `/`. The `_headers` file is Cloudflare's format, so
the security headers apply straight away.

---

## Later, if you want your own domain

`blackbutwhyte.com` costs about 10 to 15 dollars a year, and Cloudflare Registrar sells at
cost. Both hosts above attach a custom domain for free with automatic HTTPS. After pointing
the DNS, update the URLs in `index.html`, `robots.txt` and `sitemap.xml` so search engines
and Pinterest follow the new address.

---

## Editing the content

Everything is in `index.html`. The prose is plain HTML, the styling is the `<style>` block
at the top, and the colours are the six variables in `:root` (with dark mode overrides just
below). Change the text, commit, push, and it is live in under a minute.

When you change the privacy policy, update the "Last updated" date on the line under the
Privacy Policy heading. The policy itself says you will, and Pinterest checks.

---

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` straight from disk works too.

---

## Files

```
index.html      the whole page, shop blurb and privacy policy
404.html        not found page
netlify.toml    Netlify config: publish root and security headers
_headers        the same headers in Cloudflare Pages format
robots.txt      lets crawlers in, points at the sitemap
sitemap.xml     the one URL
.nojekyll       stops GitHub Pages running Jekyll, if you ever deploy there instead
```
