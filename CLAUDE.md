# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static one-page website for Cambridge Europe Network CIC ("CamEUnet"). No build, no tests, no JavaScript, no dependencies beyond Google Fonts (Montserrat, Inter).

Preview: `python3 -m http.server 8000`, then open http://localhost:8000.

Deploy: automatic on push to `main` via `.github/workflows/deploy.yml` (needs repo secrets `CLOUDFLARE_API_TOKEN`, `CLOUDFLARE_ACCOUNT_ID`). Manual: `npx wrangler@4 deploy` (Cloudflare Workers static assets, config in `wrangler.jsonc`, serves cameunet.uk and www.cameunet.uk). The repo root is the asset directory; `.assetsignore` keeps docs, wiki and config off the site, so add any new non-site file there.

## Structure that spans files

- `index.html` holds all markup and CSS (one `<style>` block). The comment at the top of that block records the design intent (voice, idea, colour, type, layout). Keep changes consistent with it.
- **Logo ("C mark")**: 17 gradient-filled polygons. It is defined once as `<symbol id="cmark">` with gradients `cm0`..`cm16` in a hidden SVG at the top of `<body>` and reused via `<use href="#cmark">` in the nav, hero arch and contact section. `favicon.svg` is a standalone copy of the same polygons and gradients. If the logo changes, update both.
- **Hero arch**: an inline SVG of hand-coloured polygons in blue, white, red and gold, from Cambridge (C mark, left) to Europe (EU star box, right). The coordinates were generated; there is no generator script in the repo.
- **Theming**: colour tokens on `:root` use `light-dark()`. `data-theme="light|dark"` on `<html>` forces a theme. Brand constants: `--navy #0B1F5B`, `--blue #0057FF`, `--red #E0313C`, `--gold #F5B400`. The hero, header, contact and footer are always navy.
- **Responsive**: breakpoints at 900px (grids become one column) and 600px (nav wraps and stops being sticky, simpler hero background).
- `hero.jpg` (Mathematical Bridge, 703x437) sits under navy gradient overlays in `.hero`.

## Content facts

UK rejoins Erasmus+ from 2027. Partners: Tredu Club (Austria), ACPELIA (Pissouri, Cyprus). Contact: `hello@cameunet.uk`. Projects listed are proposals that depend on Erasmus+ funding. Tagline: "Where Everyone Moves Forward."

## Note

The global web rule asks for a separate `styles.css`. This page currently keeps CSS inline in `index.html`. Ask before splitting it out.
