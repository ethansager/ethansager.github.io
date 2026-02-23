# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is Ethan Sager's personal academic website built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) theme. It deploys to GitHub Pages at `ethansager.github.io`.

## Development Commands

**Local dev server (with live reload):**
```bash
bundle exec jekyll serve
```

**Build site:**
```bash
bundle exec jekyll build
```

**Docker alternative (serves on port 8080):**
```bash
docker compose up
```

**Format Liquid/HTML with Prettier:**
```bash
npx prettier --write .
```

**Install Ruby dependencies:**
```bash
bundle install
```

## Architecture

### Content Structure

- **`_pages/about.md`** — Homepage (`/`). Bio text is in `_pages/about_ethan.md` but the current live bio is inline in `about.md`.
- **`_posts/`** — Blog posts (filename: `YYYY-MM-DD-title.md`)
- **`_bibliography/papers.bib`** — Publications managed via jekyll-scholar; displayed on the publications page
- **`_news/`** and **`_projects/`** — Jekyll collections for announcements and project cards
- **`_data/cv.yml`** — CV data rendered by the CV page layout
- **`_data/coauthors.yml`** — Maps coauthor names to their profile links for bib rendering

### Templates & Styling

- **`_layouts/`** — Liquid page templates (`about.liquid` is the homepage layout)
- **`_includes/`** — Reusable partials (header, footer, bib rendering, etc.)
- **`_sass/_themes.scss`** — Color scheme (currently a custom green palette for both light/dark modes)
- **`_sass/_variables.scss`** — SCSS variables (colors, spacing)

### Configuration

All major site settings live in **`_config.yml`**:
- Site identity, social links, and scholar config (`scholar.last_name`, `scholar.first_name`)
- Feature flags (`enable_darkmode`, `enable_math`, `enable_masonry`, etc.)
- Third-party library CDN versions and integrity hashes

### Pre-commit Hooks

Configured in `.pre-commit-config.yaml`: trailing whitespace, end-of-file fixer, YAML validation, large file check.
