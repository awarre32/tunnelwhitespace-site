# tunnelwhitespace.com

Static wrapper site for the public Tunnel Whitespace map, so the address bar keeps `tunnelwhitespace.com` instead of jumping to the ArcGIS address.

- `index.html` shows the public ArcGIS Experience Builder app (`6101a0eeeaf14029bf49495ef8baab85`) full screen in an iframe; `southeast/index.html` opens its Southeast page. Both carry the title, description and link-preview tags.
- `preview.png` (link preview, 1200 by 630) and the icons are built by `scripts/build_site_assets.py` in the `tunnel-whitespace-map` repo.
- Hosting: GitHub Pages from `main`, custom domain in `CNAME`. DNS at Squarespace: four A records for the root (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153) and `www` CNAME to `awarre32.github.io`.
- Crawlability (2026-10-29): the map pages carry titles, descriptions, JSON-LD (WebSite, WebApplication, Dataset) and a 34 px link bar; text pages `markets/`, `markets/southeast/` and `about/` (method and FAQ), plus `llms.txt`, `llms-full.txt`, `sitemap.xml`, `robots.txt` (search and AI crawlers allowed) and the IndexNow key file. All of these are generated: run `python scripts/build_site_pages.py <this folder>` in the `tunnel-whitespace-map` repo (numbers come anonymously from the public map layers), commit, push, then `python scripts/ping_indexnow.py`. Do not hand-edit generated files.
- If the public app id changes, update `APP` in `build_site_pages.py` and rebuild.

Contains no data; the map and its data live in ArcGIS Online.
