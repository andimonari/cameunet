---
type: Concept
title: Theming Tokens
description: How the page handles light and dark mode with CSS light-dark() tokens.
tags: [website, css]
timestamp: 2026-11-23T00:00:00Z
---

# Theming Tokens

The [[Index Page]] defines its colours as custom properties on `:root` with `light-dark()`, so one declaration covers both modes: `--bg`, `--ink`, `--muted`, `--panel`, `--line`, `--link`. Setting `data-theme="light"` or `"dark"` on `<html>` forces a mode through `color-scheme`.

Brand constants do not change with the mode: `--navy #0B1F5B`, `--blue #0057FF`, `--red #E0313C`, `--gold #F5B400`. The header, hero, contact band and footer stay navy in both modes. The pillar cards use blue, gold and red for the [[Three Pillars]].

## Sources

- `index.html` (`:root` rules)
