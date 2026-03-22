# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for Anshuman Mishra (heyyanshuman.com) — Machine Learning Engineer at Zomato and Google Developer Expert. Built with Quarto as a static site with blog, project showcase, and personal notes. Hosted on GitHub Pages via custom domain.

## Build & Development Commands

```bash
quarto preview                              # Local dev server with live reload
quarto render                               # Full site build → _site/
quarto render posts/agent_memory_101.qmd    # Render a single page while iterating
```

Publishing is automated: pushes to `master` trigger `.github/workflows/publish.yml`, which runs Quarto publish to `gh-pages`. No need to run `quarto publish` manually unless doing a one-off deploy.

## Site Architecture

### Configuration & Theme
- **_quarto.yml**: Minimal site config — `theme: default` with `site.css` for all custom styling
- **_nav.html**: Custom fixed navigation bar, injected site-wide via `include-before-body` in `_quarto.yml`. Edit this file to change nav links.
- The site deliberately hides Quarto's default navbar, sidebar, TOC, and color scheme toggle via CSS (`display: none !important`). All navigation is provided by `_nav.html` instead.
- `site.css` defines a paper-toned, serif-based, narrow (600px) reading layout with CSS custom properties (`--paper`, `--ink`, `--muted`, `--rule`)

### Content Organization
- **index.qmd**: Home page (bio, experience, open source)
- **writing.qmd**: Unified listing page for all posts and notes (replaces former `tech-blog.qmd` / `my-notes.qmd`)
- **pages/**: Section pages (`work.qmd`, `projects.qmd`, `talks.qmd`)
- **posts/**: Technical blog posts (`.qmd` files, shared config in `posts/_metadata.yml`)
- **notes/**: Personal reflections (`.qmd` files, shared config in `notes/_metadata.yml`)
- **archive/**: Older interview content

### Blog Post Frontmatter Template
```yaml
---
aliases:
- /post_slug
permalink: /post_slug
badges: false
toc: true
categories:
- Category1
date: 'YYYY-MM-DD'
description: Short description
hide: false
output-file: filename.html
search_exclude: false
title: Blog Post Title
---
```

### Assets & Extensions
- Images: `assets/images/pfp/` (profile pics), `posts/assets/[slug]/`, `notes/assets/[slug]/`
- Extensions: `_extensions/quarto-ext/fontawesome`, `_extensions/schochastics/academicons`

## Git Workflow

- Main branch: `master`
- `_site/` is **not** tracked (ignored via `**/_site/**` in `.gitignore`)
- `.quarto/` build cache is ignored
- Commit style: short, lowercase, imperative subjects (e.g., `fix tag`, `quarterly update`)

## Naming Conventions

- Section pages: simple names (`pages/work.qmd`)
- Blog posts: lowercase, underscore-separated slugs (`posts/agent_memory_101.qmd`)
- 2-space indentation in YAML
- Keep styling changes in `site.css`; prefer small overrides over inline styles

## Important Context

- **Current Role**: ML Engineer at Zomato (AI evaluation platform and SDK)
- **Newsletter**: The Conductor (conductorbyam.substack.com)
- **Google Developer Expert**: In Machine Learning
- **Execution mode**: `freeze: auto` — computational code output is cached; posts inherit `freeze: true` from `_metadata.yml`
