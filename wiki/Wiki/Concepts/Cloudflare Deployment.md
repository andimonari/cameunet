---
type: Decision
title: Cloudflare Deployment
description: The site runs as a Cloudflare Worker with static assets on cameunet.uk, deployed with wrangler.
tags: [website, hosting]
website: https://cameunet.uk
timestamp: 2026-11-23T00:00:00Z
---

# Cloudflare Deployment

The [[Index Page]] is served from Cloudflare as a Worker with static assets, named `cameunet`, on the custom domains cameunet.uk and www.cameunet.uk (live since 2026-11-23). There is no Worker script, only files.

Every push to `main` deploys through the GitHub Action in `.github/workflows/deploy.yml`, which runs `cloudflare/wrangler-action` with the repo secrets `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID`. A manual deploy from the repo root is `npx wrangler@4 deploy` after a one-time `npx wrangler@4 login`. The config is `wrangler.jsonc`. The asset directory is the repo root, so `.assetsignore` lists everything that must stay off the site: `wiki/`, `README.md`, `CLAUDE.md` and the config files. A new non-site file in the root has to be added there, or it gets published.

## Why

Chosen over Git-connected Cloudflare Pages because the custom domains are declared in `wrangler.jsonc` and bound in one CLI step, with no dashboard clicks. Pages would redeploy on push by itself; the GitHub Action gives the same result while keeping the domain setup in code (added 2026-11-23).

## Sources

- `wrangler.jsonc`, `.assetsignore`, `.github/workflows/deploy.yml`
