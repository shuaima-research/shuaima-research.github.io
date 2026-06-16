# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto website project - a personal academic/research portfolio site deployed to GitHub Pages. The site is built from Quarto Markdown (`.qmd`) source files and outputs static HTML to the `docs/` directory.

## Build Commands

```bash
# Render the site (generates HTML in docs/ directory)
quarto render

# Preview the site locally with live reload
quarto preview

# Publish to GitHub Pages
quarto publish gh-pages
```

## Architecture

**Source → Output Flow:**
- Edit `.qmd` files in project root
- Run `quarto render` to generate HTML in `docs/`
- GitHub Pages serves content from the `docs/` directory on the main branch

**Key Configuration (`_quarto.yml`):**
- Output directory: `docs/`
- Theme: Cosmo with custom CSS overrides (`styles.css`)
- Navigation: Home, Research, Projects, CV

**Page Structure:**
| Source | Page |
|--------|------|
| `index.qmd` | Home/About |
| `research.qmd` | Research themes |
| `projects.qmd` | Project portfolio |
| `cv.qmd` | Curriculum Vitae (uses trestles template with profile photo) |

**Custom Styling:**
- `styles.css` contains CSS overrides for the Quarto theme
- Currently adjusts the trestles template profile section width

## Workflow Notes

- Always run `quarto render` after editing `.qmd` files before committing
- The `docs/` directory contains generated files and should be committed for GitHub Pages deployment
- Profile images are in the root directory; `profile2.jpeg` is currently used in the CV page
