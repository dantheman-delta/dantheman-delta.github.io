# CLAUDE.md

## Project overview

Static site built with Jekyll, hosted on GitHub Pages at `https://dantheman-delta.github.io`.

## Structure

```
_config.yml          — site-wide settings (title, URL, markdown engine)
_layouts/
  default.html       — shared HTML shell used by all pages
assets/
  css/style.css      — global stylesheet
index.md             — home page
about.md             — about page
```

Pages use YAML front matter to select a layout and set a title:

```yaml
---
layout: default
title: Page Title
---
```

## Local development

```bash
gem install bundler jekyll
bundle install      # if Gemfile present
bundle exec jekyll serve --livereload
```

Site is served at `http://localhost:4000`.

## Deployment

Push to the `main` branch. GitHub Actions / GitHub Pages builds and deploys automatically. No build step is required locally before committing.

## Conventions

- Pages are written in Markdown (`.md`) with Jekyll front matter.
- All shared HTML lives in `_layouts/`. Create a new layout file there when a page needs a meaningfully different shell.
- CSS lives in `assets/css/style.css`. No preprocessor is configured; plain CSS only unless one is added to `_config.yml`.
- Do not commit `_site/`, `.jekyll-cache/`, or `vendor/` — these are in `.gitignore`.
- Keep pages minimal. Avoid JavaScript unless necessary.
