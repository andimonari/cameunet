---
type: Entity
title: Index Page
description: index.html, the single static page that is the whole website.
tags: [website]
timestamp: 2026-11-23T00:00:00Z
---

# Index Page

`index.html` is the entire site of [[Cambridge Europe Network CIC]]. Markup and CSS live in one file, and there is no JavaScript and no build step. Fonts come from Google Fonts (Montserrat for headings, Inter for text).

Sections in order: hero, About, What we do ([[Three Pillars]]), Erasmus+ ([[Erasmus Plus]]), Projects, Partners, Get involved, Contact. The hero shows `hero.jpg`, a photo of the Mathematical Bridge, under navy gradients, with the [[Hero Arch]] beneath the title. The [[C Mark Logo]] appears in the nav, the arch and the contact section. Colours follow [[Theming Tokens]]. It is hosted as described in [[Cloudflare Deployment]].

Breakpoints: at 900px the grids drop to one column; at 600px the nav wraps and stops being sticky.

The global web rule prefers a separate `styles.css`. This page keeps its CSS inline (as of 2026-11).

## Sources

- `index.html`
