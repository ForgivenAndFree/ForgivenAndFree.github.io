# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

"Forgiven and Free" — a Lutheran adaptation of the EasyPeasy Method (itself adapted from Allen Carr's *EasyWay to Stop Smoking*) for escaping pornography addiction. This is a **Jekyll site hosted on GitHub Pages** at forgivenandFree.github.io.

## Build & Development

```bash
# Install dependencies (requires Ruby)
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build static site
bundle exec jekyll build
```

Output goes to `_site/` (gitignored).

## Site Architecture

- **Jekyll static site** using GitHub Pages (`github-pages` gem). No custom plugins.
- **Single layout**: `_layouts/default.html` — contains ALL CSS inline (no external stylesheets or JS files). Parchment/gold/red theme using EB Garamond font. Responsive with mobile slide-out sidebar at 860px breakpoint.
- **Includes**: `_includes/sidebar.html` (wraps toc-list) and `_includes/toc-list.html` (the ordered chapter list + resources, shared between desktop sidebar and mobile panel).
- **Config** (`_config.yml`): Sets default layout for all pages. Chapters in `chapters/` and root pages both use the `default` layout automatically.

## Content Structure

- **30 chapters** in `chapters/` as Markdown files with YAML frontmatter (`layout: default`, `title:`). Named `NN-slug.md` (e.g., `01-introduction.md`, `07-crossing-the-red-line.md`).
- **`index.md`** — Landing page with full introduction, method overview, and table of contents linking to all chapters.
- **`resources/`** — Supplementary essays (e.g., `why-lutheranism.md`). Has its own `index.md`.
- **Navigation**: Chapter links in `index.md` TOC and `_includes/toc-list.html` must stay in sync. When adding/renaming chapters, update both.

## Theological Guidelines

This is a **confessional Lutheran** work. When editing content:

- **Law/Gospel distinction** is central: the Law reveals sin but cannot save; only the Gospel (Christ's work) delivers freedom. Never frame quitting as willpower or self-improvement.
- **Means of Grace**: Baptism, Absolution, Lord's Supper are how God delivers forgiveness. These are not symbolic.
- **Fallen nature, not design**: Disordered desires (e.g., novelty-seeking, lust) are consequences of the Fall, NOT how God designed humanity. Never imply God made humans to be promiscuous or that sinful tendencies are "natural design."
- **The devil is real and active** — temptation and deception are attributed to him, not merely to psychological processes.
- **Anti-works**: The book explicitly opposes accountability culture, day-counting, willpower methods, and paid recovery programs as forms of Law-based thinking.
- Scripture quotations use **ESV**.

## Workflow

After every major change or update, commit and push to GitHub (deploys automatically via GitHub Pages).
