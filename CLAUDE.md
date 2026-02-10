# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website for Anshuman Mishra (heyyanshuman.com), a Machine Learning Engineer at Zomato and Google Developer Expert. Built with Quarto, the site includes:
- Home page with bio and experience
- ML work (OSS contributions, papers, Kaggle)
- Building (fun projects like Nebula, Sidekick, Snapgenie)
- Talks & Media (conference talks, podcasts, YouTube)
- Tech Blog (technical articles)
- My Notes (personal reflections)

## Build & Development Commands

### Preview the site locally
```bash
quarto preview
```
This starts a local development server with live reload. Access at http://localhost:4848 (or port shown in output).

### Build the site
```bash
quarto render
```
Generates static site files in the `_site/` directory.

### Publish to GitHub Pages
```bash
quarto publish gh-pages
```
Builds and deploys the site to GitHub Pages. The site is hosted at heyyanshuman.com (custom domain configured via CNAME).

## Site Architecture

### Core Configuration
- **_quarto.yml**: Main configuration file defining site structure, theme, navigation, and metadata
  - Uses custom theme (`custom_theme.scss`) with light/dark mode support
  - Google Analytics integration
  - Social media cards (Twitter, Open Graph)
  - Five main navbar sections: "ML", "Building", "Talks", "Tech Blog", "My Notes"

### Content Structure
- **index.qmd**: Home page with bio, current role at Zomato, experience, and consultancy work
- **pages/ml.qmd**: ML work including OSS contributions, publications, and Kaggle competitions
- **pages/building.qmd**: Fun projects (Nebula, Sidekick, Snapgenie, SlideBookLM, etc.)
- **pages/talks.qmd**: Conference talks, podcasts, and YouTube videos
- **tech-blog.qmd**: Technical blog listing page with filtering, sorting, and RSS feed
- **my-notes.qmd**: Personal blog listing page
- **posts/**: Technical blog posts as `.qmd` files
  - **posts/_metadata.yml**: Shared configuration for all blog posts (freeze: true, title-block-banner: true)
  - Each post has YAML frontmatter with: title, date, description, categories, aliases, permalink
- **notes/**: Personal blog posts as `.qmd` files
  - **notes/_metadata.yml**: Shared configuration for personal posts
  - Follows same frontmatter pattern as technical posts

### Blog Post Structure
All blog posts follow a consistent YAML frontmatter pattern:
```yaml
---
aliases:
- /post_slug
permalink: /post_slug
badges: false
toc: true
categories:
- Category1
- Category2
date: 'YYYY-MM-DD'
description: Short description
hide: false
output-file: filename.html
search_exclude: false
title: Blog Post Title
---
```

### Styling
- **custom_theme.scss**: Custom Quarto theme (light mode)
- **sketchy.scss**: Alternative theme file
- **styles.css**: Additional custom styles
- Dark mode uses Quarto's built-in "darkly" theme

### Extensions
- **_extensions/quarto-ext/fontawesome**: FontAwesome icon support
- **_extensions/schochastics/academicons**: Academic icon support (e.g., Google Scholar icon)

### Assets
- **assets/images/pfp/**: Profile pictures
- **posts/assets/**: Technical blog post images and media files organized by post
- **notes/assets/**: Personal blog post images and media files

## Git Workflow

- Main branch: `master`
- GitHub repo: https://github.com/kanpuriyanawab/
- The `_site/` directory is tracked in git (uncommented in .gitignore)
- Build artifacts in `.quarto/` are ignored

## Content Guidelines

### When Creating New Blog Posts

**Technical Posts:**
1. Create a new `.qmd` file in the `posts/` directory
2. Use the YAML frontmatter template shown above
3. `freeze: true` is inherited from `posts/_metadata.yml` to cache computational output
4. Place images in `posts/assets/[post-slug]/`
5. Use categories that align with existing taxonomy (check `tech-blog.qmd` listing)

**Personal Notes:**
1. Create a new `.qmd` file in the `notes/` directory
2. Use the same YAML frontmatter pattern
3. Place images in `notes/assets/[post-slug]/`
4. Categories typically include: Personal, Reflections, Career, etc.

### When Editing Existing Content
- Home page bio and experience: Edit `index.qmd`
- ML work (OSS, papers, Kaggle): Edit `pages/ml.qmd`
- Fun projects: Edit `pages/building.qmd`
- Talks and media: Edit `pages/talks.qmd`
- Technical blog posts: Edit files in `posts/`
- Personal notes: Edit files in `notes/`
- Navigation or site metadata: Edit `_quarto.yml`

## Technical Notes

- Quarto version: 1.7.31 (check with `quarto --version`)
- Execution mode: `freeze: auto` (computational code is frozen/cached)
- The site uses Quarto's website project type
- Blog listing automatically generates from `posts/` directory content
- RSS feed is automatically generated for the blog
- Social media metadata (Twitter cards, Open Graph) is configured in `_quarto.yml`

## Output Directory

The `_site/` directory contains the built website. Key files:
- Static HTML pages for all content
- `listings.json`: Blog post metadata for listing pages
- `search.json`: Search index data
- `sitemap.xml`: Site sitemap
- `tech-blog.xml`: RSS feed for the technical blog
- `my-notes.xml`: RSS feed for personal notes

## Important Context

- **Current Role**: Machine Learning Engineer at Zomato (building AI evaluation platform and SDK)
- **Newsletter**: The Conductor (https://conductorbyam.substack.com/) - linked in Tech Blog and home page
- **Google Developer Expert**: In Machine Learning
- **Education**: NIT Warangal, 2023
