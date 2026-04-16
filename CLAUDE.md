# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the official website of RK Dubey, built as a scratch-built Hugo static site (no theme dependency).

## Common Commands

```bash
# Start local development server with live reload
hugo server

# Build the site (output goes to public/)
hugo

# Create new content
hugo new content/<section>/<filename>.md
```

## Architecture

This is a minimal Hugo site built without a pre-made theme — all templates are hand-written.

- `hugo.toml` — site configuration (baseURL, title, languageCode)
- `layouts/` — Go HTML templates; `index.html` is the homepage template
- `archetypes/default.md` — front matter template for `hugo new` commands
- `content/` — Markdown content files (not yet created)
- `static/` — Static assets served as-is (not yet created)

Hugo's template lookup order applies: `layouts/_default/` for base templates, `layouts/<section>/` for section-specific overrides, and `layouts/index.html` for the homepage.

Content files use TOML front matter (as set in `archetypes/default.md`). New content is created as drafts by default — pass `-D` flag to `hugo server` or `hugo` to include drafts.
