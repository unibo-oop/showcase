# OOP Projects Showcase

A [Hugo](https://gohugo.io/)-based static website that showcases student projects from the **"Programmazione ad Oggetti" (Object-Oriented Programming)** course at the [University of Bologna](https://www.unibo.it/), Cesena campus.

Live site: <https://unibo-oop.github.io/showcase/>

## What it is

The site collects notable student OOP projects (mostly Java games and applications) submitted over the years (2020–present). Each entry links to a downloadable JAR and an illustrative screenshot. The selection is **not exhaustive**: a project's absence does not imply low quality.

## Repository structure

```
config.toml              # Hugo site configuration
content/
  projects/              # One Markdown file per project (frontmatter: title, date, subtitle, link, image)
themes/
  showcase/              # Git submodule – showcase-hugo-theme (Tailwind CSS)
package.json             # Node dependencies for PostCSS / Tailwind build
.github/
  workflows/
    build-and-deploy.yml # CI: build with Hugo, link-check, deploy to gh-pages
```

## Adding a project

Create a new Markdown file under `content/projects/` following the naming convention `<year>-<slug>.md`:

```markdown
---
title: My Project
date: 2025-01-01
subtitle: 2025
link: https://github.com/org/repo/releases/download/v1.0/app.jar
image: https://example.com/screenshot.png
---
```

## Local development

```bash
# Install Node dependencies (PostCSS / Tailwind)
npm install

# Start Hugo dev server
hugo server --disableFastRender
```

Requires [Hugo extended](https://gohugo.io/installation/) ≥ 0.124.1.

## Deployment

Every push to `main` triggers the `build-and-deploy` workflow, which builds the site with Hugo and pushes the `public/` directory to the `gh-pages` branch, from which GitHub Pages serves the site.
