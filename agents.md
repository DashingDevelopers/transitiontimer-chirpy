# Agents & Copilot Instructions

This file provides context and guidance for AI coding agents (e.g., GitHub Copilot, Cursor, Claude) working on this project.

---

## Project Overview

- **Site name:** Transition Timer
- **Description:** A Jekyll site built on the [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) theme (v7.4.1). Helps users overcome time blindness and break hyperfocus with intelligent task transition support.
- **Theme mode:** Dark (set in `_config.yml`)
- **Timezone:** Asia/Shanghai
- **Language:** English (`en`)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Static site generator | [Jekyll](https://jekyllrb.com/) |
| Theme | [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) |
| CSS preprocessor | Sass (SCSS) |
| JS bundler | Rollup |
| CSS framework | Bootstrap 5 |
| Package manager | npm |
| Ruby dependency manager | Bundler |
| Linting | ESLint (JS), Stylelint (SCSS) |
| HTML testing | html-proofer |
| Git hooks | Husky + commitlint |

---

## Directory Structure

```
_config.yml          # Main Jekyll configuration
_posts/              # Blog posts — YYYY-MM-DD-title.md
_tabs/               # Sidebar nav pages (about, archives, categories, tags)
_layouts/            # Liquid HTML layout templates
_includes/           # Reusable Liquid HTML partials
_sass/               # SCSS source files
  abstracts/         # Variables, mixins, functions
  base/              # Resets, typography, base styles
  components/        # UI component styles
  layout/            # Sidebar, topbar, footer, etc.
  pages/             # Page-specific styles
  themes/            # Light/dark theme color definitions
_javascript/         # JS source files (bundled via Rollup)
_data/               # YAML data files (authors, locales, nav links)
assets/              # Static assets (images, pre-built JS/CSS)
_plugins/            # Ruby Jekyll plugins
tools/               # Shell scripts for dev/CI tasks
docs/                # Project documentation (CHANGELOG, CONTRIBUTING, etc.)
```

---

## Common Commands

### Local Development

```bash
# Install Ruby dependencies
bundle install

# Install Node dependencies
npm install

# Serve site locally with live reload (development)
bash tools/run.sh

# Serve on a custom host
bash tools/run.sh -H 0.0.0.0

# Serve in production mode
bash tools/run.sh -p

# Direct bundle exec (alternative)
bundle exec jekyll serve --livereload
```

### Build & Test

```bash
# Build site for production
JEKYLL_ENV=production bundle exec jekyll build

# Run html-proofer tests
bash tools/test.sh

# Run JS and SCSS linting
npm test

# Lint JS only
npm run lint:js

# Lint SCSS only
npm run lint:scss

# Auto-fix SCSS lint issues
npm run lint:fix:scss
```

### Asset Pipeline

```bash
# Build all assets (CSS purge + JS bundle)
npm run build

# Build JS bundle only (production)
npm run build:js

# Purge unused CSS
npm run build:css

# Watch JS for changes (development)
npm run watch:js
```

---

## Writing Posts

Posts live in `_posts/` and must be named `YYYY-MM-DD-title.md`.

### Minimal Front Matter

```yaml
---
title: My Post Title
date: 2026-02-26 10:00:00 +0800
categories: [TopCategory, SubCategory]
tags: [tag1, tag2]
---
```

### Full Front Matter Options

```yaml
---
title: My Post Title
date: 2026-02-26 10:00:00 +0800
last_modified_at: 2026-02-26 12:00:00 +0800
categories: [TopCategory, SubCategory]   # max 2 levels
tags: [tag1, tag2]                       # always lowercase
author: <author_id>                      # defined in _data/authors.yml
description: Short SEO description
image:
  path: /path/to/image.jpg
  alt: Image alt text
pin: true           # pin to top of home page
toc: true           # table of contents (default: true)
comments: false     # disable comments for this post
math: true          # enable LaTeX math rendering
mermaid: true       # enable Mermaid diagrams
---
```

### Post Features

- **Images:** `![Alt text](/path/to/img){: .shadow }` — supports captions with `_Alt text_`
- **Prompts:** `{: .prompt-tip }`, `{: .prompt-info }`, `{: .prompt-warning }`, `{: .prompt-danger }`
- **Code blocks:** Fenced with language identifier; line numbers enabled by default
- **Mermaid diagrams:** Fenced with ` ```mermaid ` after enabling `mermaid: true` in front matter
- **Math:** KaTeX blocks with `$$...$$` after enabling `math: true`

---

## Customization

### Theme Colors / Styles

- Light/dark theme variables: `_sass/themes/`
- Layout styles: `_sass/layout/`
- Component styles: `_sass/components/`

### Sidebar Navigation

- Tabs are defined in `_tabs/` — each `.md` file becomes a nav item
- Order controlled by `order:` in front matter

### Localization

- Locale strings: `_data/locales/<lang>.yml`
- Active language set by `lang:` in `_config.yml`

### Author Profiles

Add to `_data/authors.yml`:
```yaml
author_id:
  name: Full Name
  twitter: twitter_handle
  url: https://example.com
```

---

## Configuration Reference (`_config.yml`)

| Key | Purpose |
|---|---|
| `title` | Site title displayed in sidebar |
| `tagline` | Subtitle displayed under title |
| `description` | SEO meta description |
| `url` | Full site URL (required for production) |
| `baseurl` | Subpath if not at root (e.g. `/blog`) |
| `theme_mode` | `light` or `dark`; empty = follows system |
| `avatar` | Sidebar profile image path |
| `cdn` | CDN prefix for media assets |
| `toc` | Global TOC toggle for posts |
| `paginate` | Posts per page on home |
| `comments.provider` | Comment system: `disqus`, `utterances`, `giscus` |
| `analytics.*` | Analytics provider configuration |
| `pwa.enabled` | Enable PWA / installable app |

---

## GitHub Actions / CI

| Workflow | Trigger | Purpose |
|---|---|---|
| `ci.yml` | Push to `master`, PRs | Build & test across Ruby 3.1–3.3 |
| `cd.yml` | Push to `master` | Deploy to GitHub Pages |
| `lint-js.yml` | PRs | ESLint check |
| `lint-scss.yml` | PRs | Stylelint check |
| `commitlint.yml` | PRs | Enforce conventional commits |
| `codeql.yml` | Schedule / push | Security analysis |

---

## Commit Convention

This project uses [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add new feature
fix: correct a bug
docs: update documentation
style: formatting, no logic change
refactor: code restructure
perf: performance improvement
test: add or update tests
chore: build process or tooling changes
```

---

## Key Files for Agents

| Task | File(s) to edit |
|---|---|
| Site metadata / config | `_config.yml` |
| New blog post | `_posts/YYYY-MM-DD-title.md` |
| Sidebar page | `_tabs/<page>.md` |
| Layout changes | `_layouts/*.html` |
| Reusable HTML partials | `_includes/*.html` |
| Global styles | `_sass/` |
| Theme colors | `_sass/themes/` |
| JavaScript behavior | `_javascript/` |
| Navigation data | `_data/` |
| Locale/i18n strings | `_data/locales/<lang>.yml` |
| Ruby plugins | `_plugins/` |
| Ruby dependencies | `Gemfile` |
| Node dependencies | `package.json` |

