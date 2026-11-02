# tunnelwhitespace.com

Static wrapper site for the public Tunnel Whitespace map, so the address bar keeps `tunnelwhitespace.com` instead of jumping to the ArcGIS address.

- `index.html` shows the public ArcGIS Experience Builder app (`6101a0eeeaf14029bf49495ef8baab85`) full screen in an iframe; `southeast/index.html` opens its Southeast page. Both carry the title, description and link-preview tags.
- `preview.png` (link preview, 1200 by 630) and the icons are built by `scripts/build_site_assets.py` in the `tunnel-whitespace-map` repo.
- Hosting: GitHub Pages from `main`, custom domain in `CNAME`. DNS at Squarespace: four A records for the root (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153) and `www` CNAME to `awarre32.github.io`.
- Crawlability (2026-10-29, regional pages and analytics 2026-11-02): the map pages carry titles, descriptions, JSON-LD (WebSite, WebApplication, Dataset), a 34 px link bar, a clipped all-pages nav for crawlers and screen readers, and map engagement events for GA4; text pages `markets/`, `markets/<region>/` (six regions) and `about/` (method and FAQ), plus `404.html`, `llms.txt`, `llms-full.txt`, `sitemap.xml`, `robots.txt` (search and AI crawlers allowed) and the IndexNow key file. All of these are generated: run `python scripts/build_site_pages.py <this folder>` in the `tunnel-whitespace-map` repo (numbers come anonymously from the public map layers), commit, then release with `scripts/release_site.ps1` (fast-forward to `main`, live checks, IndexNow ping). Do not hand-edit generated files.
- Rankings and counts are published under CC BY-NC 4.0 (credit Tunnel Whitespace; commercial use by permission).
- If the public app id changes, update `APP` in `build_site_pages.py` and rebuild.

Contains no data; the map and its data live in ArcGIS Online.
