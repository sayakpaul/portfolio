# Repository Guidelines

## Project Structure & Module Organization
This repository is a Quarto website. Site-wide configuration lives in `_quarto.yml`, with the home page at `index.qmd` and unified writing listing at `writing.qmd`. Section pages live in `pages/` (`work.qmd`, `projects.qmd`, `talks.qmd`), long-form articles in `posts/`, archived material in `archive/`, and notes in `notes/`. Custom navigation is in `_nav.html`, injected via `include-before-body`. Shared defaults for posts and notes are defined in `posts/_metadata.yml` and `notes/_metadata.yml`. Store source images in `assets/` or content-local folders such as `posts/assets/`. `_extensions/` contains Quarto extensions, and `_site/` is generated output that is **not** tracked in git.

## Build, Test, and Development Commands
- `quarto preview` runs the local authoring server with live reload.
- `quarto render` rebuilds the full site into `_site/`.
- `quarto render posts/agent_memory_101.qmd` renders one page while iterating on a post.

Publishing is automated in `.github/workflows/publish.yml`; pushes to `master` trigger Quarto publish to `gh-pages`.

## Coding Style & Naming Conventions
Write content in Quarto Markdown (`.qmd`) with concise YAML front matter. Use 2-space indentation in YAML, keep headings readable and consistent, and preserve existing front matter keys such as `permalink`, `date`, and `output-file` where present. Follow existing filename patterns: simple names for section pages (`pages/ml.qmd`) and lowercase, underscore-separated slugs for posts (`posts/agent_memory_101.qmd`). Keep styling changes in `site.css`, and prefer small, reusable overrides over inline styling.

## Testing Guidelines
There is no automated test suite in this repository. Validate changes by running `quarto render`, then review the result in `quarto preview`. Spot-check links, images, navigation, table of contents behavior, and permalink/output paths. If you change layout or theme files, verify both the edited page and the homepage.

## Commit & Pull Request Guidelines
Recent commits use short, lowercase subjects such as `fix tag`, `update description`, and `quarterly update`. Keep commit messages brief, imperative, and specific to one content or styling change. Pull requests should summarize the user-visible change, list the affected paths, note how you validated the render, and include screenshots for visual updates. Mention when `_site/` was regenerated so reviewers know generated output is intentional.
