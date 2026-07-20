# packetsherpa.github.io — Agent Instructions

GitHub Pages site (Jekyll) for packetsherpa.github.io, including the "Walking
in Sober Boots" recovery-blog archive migrated from WordPress.

This file is the single source of truth for any agent working in this repo
(Claude Code, Codex, or others). `CLAUDE.md` and `GEMINI.md` are symlinks to
this file. Global conventions live in `~/.claude/CLAUDE.md` — do not restate
them here. This file covers only what is specific to packetsherpa.github.io.

## What This Tool Is

Jekyll 4.3 site deployed to GitHub Pages. Content areas:

- top-level pages (`index.html`, `404.html`, `frank.md`)
- `soberboots/` — the "Walking in Sober Boots" blog archive (2013-2023), served under `/soberboots/`, driven by `_posts/` (223+ WordPress-migrated posts) plus `jekyll-paginate-v2`/`jekyll-archives`

Key commands:

- `bundle install`
- `bundle exec jekyll serve` — local preview
- `bundle exec jekyll build --baseurl "..."` — production build (mirrors `.github/workflows/pages.yml`)

Gotchas:

- Deploys from `main` via `.github/workflows/pages.yml` on every push.
- `_config.yml` sets `permalink: /soberboots/:year/:month/:day/:title/` — don't change without checking existing post URLs.
- There's a leftover, untracked, empty `packetsherpa.github.io/` directory at repo root mirroring the `soberboots/` URL structure — looks like a stray Jekyll build artifact, not part of the site source. Safe to ignore.

## On Session Start

1. Run `git status --short --branch` and `git log --oneline -5`.
2. State the current task before starting; if it is not obvious, ask.

## Durable Memory

Durable facts, decisions, and landmines live in `.claude/memory/` as one-fact
files (frontmatter: `name`, `description`, `metadata.type`; linked with
`[[slug]]`). When something becomes durable, add a one-fact file and a line in
`.claude/memory/MEMORY.md` — do not bury it in prose.

@.claude/memory/MEMORY.md
