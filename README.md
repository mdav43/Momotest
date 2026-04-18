# monetago.com

A Jekyll site for MonetaGo, deployed to GitHub Pages via GitHub Actions.

## Run it locally

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open http://localhost:4000.

## Publish

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds with Jekyll, runs html-proofer on the output, and publishes to GitHub Pages.

Set the repository Pages source to **GitHub Actions** (Settings → Pages → Source).

## Edit content

### Add or change a page

Top-level `.md` / `.html` files in the repo root are the site's pages. Each uses front matter like:

```yaml
---
layout: page
title: "Page title"
lede: "One-sentence claim a reader could repeat verbatim."
eyebrow: Section
permalink: /your-path/
---
```

### Add a news / insights post

Create a file in `_posts/` named `YYYY-MM-DD-slug.md`:

```yaml
---
title: "Post title"
lede: "One-sentence summary."
---

Markdown body.
```

### Update the nav

Edit `_data/nav.yml`. The header and footer both read from this file.

### Update the customer strip or quotes

Edit `_data/customers.yml`. The homepage and the Evidence page both read from this file.

### Update the stats on the homepage

Edit `_data/stats.yml`.

### Update resources / whitepapers

Edit `_data/resources.yml`.

## House style

Written for B2B institutional readers (banks, fintechs, public sector). Two rules:

1. **Every adjective has a number or a citation next to it.** No "leading", "world-class", "trusted", "innovative" standing alone.
2. **Every page opens with a one-sentence claim** a risk officer could repeat verbatim. If you can't write that sentence, the page isn't ready.

## File layout

```
_config.yml            site metadata, plugins, collections
_data/                 data files that drive nav, customers, stats, resources
_includes/             partials: head, header, footer, nav, cta, stat-grid
_layouts/              default, page, solution, post, home
_posts/                news and insights
_sass/                 design tokens and components
assets/                CSS entry, JS, images, fonts
solutions/             solution pages (one per buyer type)
*.md / *.html          top-level pages
.github/workflows/     GitHub Actions deploy
```

## Design system at a glance

| Token | Value | Used for |
|---|---|---|
| `--ink` | `#0B1F3A` | Primary text, dark UI |
| `--slate` | `#334155` | Secondary text |
| `--paper` | `#F8FAFC` | Page background |
| `--line` | `#E2E8F0` | Borders |
| `--accent` | `#0E9488` | Links, highlights, CTA |

Fonts: **Source Serif 4** for headings, **Inter** for body (both loaded from the system stack unless you add them to `assets/fonts/` and reference in `_sass/_tokens.scss`).
