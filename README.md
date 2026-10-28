# tunnelwhitespace.com

Static wrapper site for the public Tunnel Whitespace map, so the address bar keeps `tunnelwhitespace.com` instead of jumping to the ArcGIS address.

- `index.html` shows the public ArcGIS Experience Builder app (`6101a0eeeaf14029bf49495ef8baab85`) full screen in an iframe; `southeast/index.html` opens its Southeast page. Both carry the title, description and link-preview tags.
- `preview.png` (link preview, 1200 by 630) and the icons are built by `scripts/build_site_assets.py` in the `tunnel-whitespace-map` repo.
- Hosting: GitHub Pages from `main`, custom domain in `CNAME`. DNS at Squarespace: four A records for the root (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153) and `www` CNAME to `awarre32.github.io`.
- If the public app id changes, update the iframe `src` in both pages.

Contains no data; the map and its data live in ArcGIS Online.
