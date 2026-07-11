# News Wire

A live, hourly-refreshed news dashboard (world, business, tech, India current affairs, etc.), built as a single static page powered by the Currents API.

## 1. Publish it on GitHub Pages (free hosting)

1. Go to [github.com/new](https://github.com/new) and create a repository (e.g. `news-wire`). Keep it **Public**.
2. Upload these three files to the repo root: `index.html`, `robots.txt`, `sitemap.xml`.
   - Easiest way: on the repo page, click **Add file → Upload files**, drag the files in, and commit.
   - Or via git:
     ```bash
     git init
     git add index.html robots.txt sitemap.xml
     git commit -m "Initial site"
     git branch -M main
     git remote add origin https://github.com/YOUR-USERNAME/news-wire.git
     git push -u origin main
     ```
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source: Deploy from a branch**, branch **main**, folder **/(root)**. Save.
5. Wait ~1 minute. Your site goes live at:
   `https://YOUR-USERNAME.github.io/news-wire/`
6. (Optional) Add a custom domain under Settings → Pages → Custom domain, if you own one — a real domain (yourdomain.com) is better for SEO than a `.github.io` subdomain.

**Before or after publishing**, replace every occurrence of `REPLACE-WITH-YOUR-DOMAIN` in `index.html`, `robots.txt`, and `sitemap.xml` with your actual live URL (e.g. `your-username.github.io/news-wire` or your custom domain). Search-and-replace in a text editor is fastest.

## 2. Get it into Google — realistic timeline

There's no way to force Google to rank a brand-new site quickly — that part isn't something any code change can guarantee. But you can make sure it's indexed fast and give it the best possible shot:

1. **Google Search Console** (free): [search.google.com/search-console](https://search.google.com/search-console)
   - Add your property (the GitHub Pages URL or custom domain).
   - Submit `sitemap.xml` under "Sitemaps".
   - Use "URL Inspection" → "Request Indexing" on your homepage to nudge Google to crawl it right away.
2. **Bing Webmaster Tools** ([bing.com/webmasters](https://www.bing.com/webmasters)) — same idea, also feeds Bing/Yahoo/DuckDuckGo, and it's usually faster to index than Google.
3. **Backlinks matter more than anything else for a new site.** Share the link from places that already have authority: your social profiles, relevant subreddits/forums, a Product Hunt-style listing, your GitHub profile README, etc. A brand-new site with zero inbound links can sit unranked for weeks no matter how clean the code is.
4. **Core Web Vitals / speed** — the page is already lightweight (no framework, no heavy images), which Google's ranking algorithm rewards.

## 3. Two things worth knowing about this specific site

- **The Currents API key is visible in the page source.** Anyone who views-source can copy it and make requests against your quota. That's fine for a personal/demo project on the free tier, but if this gets real traffic, consider proxying requests through a serverless function (e.g. a Cloudflare Worker or Netlify Function) that holds the key server-side instead.
- **This is an aggregator, not original content.** Google's ranking systems are specifically tuned to deprioritize sites that just republish other outlets' headlines/descriptions without added original value (this is sometimes called "thin" or "scraped" content). If ranking is the real goal, the single highest-leverage change is adding something original per page — your own commentary, a daily roundup post, curated "editor's picks" with analysis, etc. — rather than just the live API feed. A pure live-feed aggregator can still be a genuinely useful tool for visitors; it's just unlikely to rank well in Google on its own.

## Files in this repo
- `index.html` — the site itself
- `robots.txt` — tells search engines they're allowed to crawl it, points to the sitemap
- `sitemap.xml` — helps Google/Bing discover the page immediately
