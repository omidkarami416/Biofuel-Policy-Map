# World Biofuel Policies Map

An interactive world map of biofuel policies. Click a country to see what the policy is, when it began,
how it changed, the latest rule in force, what is still only proposed, and the sources.

- **Layers:** policy coverage, ethanol blend level, biodiesel blend level
- **Search, zoom, deep links** (for example `https://YOUR-NAME.github.io/biofuel-map/#Brazil`)
- Works on phones and desktops, supports dark mode, no tracking, no build step, no external services

Status as of 28 October 2026. This is a research dataset, not legal advice. Entries marked "Verify"
have conflicting or unconfirmed sources, and † marks start dates not confirmed in the research pass.

## Publish it free on GitHub Pages

1. Create a GitHub account if you do not have one, then click **New repository**.
2. Name it `biofuel-map` (or anything you like), set it to **Public**, and create it.
3. On the new repository page click **uploading an existing file**, drag in the **contents** of this folder
   (`index.html`, `lib/`, `data/`, `README.md`), and click **Commit changes**.
   Make sure `index.html` sits at the top level of the repository, not inside another folder.
4. Go to **Settings > Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**,
   choose branch **main** and folder **/ (root)**, and click **Save**.
5. Wait one to two minutes. Your site will be at `https://YOUR-USERNAME.github.io/biofuel-map/`.

## Update the data

All content lives in `data/data.json`. To change a country, open that file on GitHub, click the pencil icon,
edit the text, and commit. The site updates within a minute or two.

- `entries` holds each policy write-up (what it is, first implemented, changes, latest, pending, flags, sources).
- `countries` links each country (names as in the world map, e.g. `United States of America`) to its entries
  and sets `status` (`enacted` or `planned`), and the numeric `ethanol` / `biodiesel` blend percentages used for shading.
- To add a country: add an entry under `entries`, then add the country under `countries` pointing to its id.

## Preview on your own computer

Opening `index.html` directly will not load the data (browsers block that). Run a tiny local server instead:

```
cd biofuel-map
python -m http.server 8000
```

Then open http://localhost:8000.

## Custom domain (optional, not free)

GitHub Pages works with a domain you buy (about $10-15 a year): Settings > Pages > Custom domain.

## Credits and licences

- Map shapes: [world-atlas](https://github.com/topojson/world-atlas) (derived from Natural Earth, public domain)
- [D3](https://d3js.org) and topojson-client (ISC licence), bundled in `lib/`
- Country boundaries are simplified and shown for information only; they do not express any view on disputed borders.
