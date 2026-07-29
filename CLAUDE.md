# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Jekyll-based course website for "Matemáticas Discretas I" (Universidad de Antioquia), built on the [Just the Class](https://github.com/kevinlin1/just-the-class) template, which extends the [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme (`remote_theme` in `_config.yml`). Deployed via GitHub Pages classic build ("Deploy from a branch", `main` / root) — there is no `.github/workflows/` build pipeline; GitHub Pages builds directly from the `github-pages` gem.

## Commands

```bash
bundle install                  # install gems (github-pages, webrick)
bundle exec jekyll serve        # local dev server at http://127.0.0.1:4000/discretas1-udea-20262/
                                 # (note: baseurl is set, so the site is NOT at plain localhost:4000/)
bundle exec jekyll build        # static build into _site/
```

There is no lint or test suite in this repo. A `.devcontainer/devcontainer.json` (Microsoft Jekyll devcontainer image) is available for a preconfigured environment; it runs `bundle install` on creation and forwards port 4000.

## Architecture

Content lives in Jekyll collections defined in `_config.yml`, each with a layout applied via `defaults`:

- `_modules/` (`week-01.md` … ) → `_layouts/module.html` — per-week class schedule entries (dates + topics), rendered into `calendar.md` by filtering on `module.slug`.
- `_schedules/` (`weekly.md`) → `_layouts/schedule.html` — generic weekly time-grid (hours/days), rendered into `schedule.md` via `{% for schedule in site.schedules %}`.
- `_announcements/` → `_layouts/announcement.html` — dated announcements, rendered on `announcements.md`.
- `_staffers/` (`prof1.md`, `prof2.md`) → `_layouts/staffer.html` — instructor profiles, rendered on `staff.md`.
- `lessons/` — actual class content, organized as `lessons/mod{N}/clase{N}.md` plus an `index.md` per module; not a Jekyll collection but a normal page tree with `permalink: '/:path/'` and layout forced to `default` (`has_children: false`) via the `scope: path: "lessons"` block in `defaults`. **Do not modify `lessons/` unless explicitly asked** — it's handled separately from config/date updates.

Top-level pages (`about.md`, `calendar.md`, `schedule.md`, `staff.md`, `announcements.md`, `README.md`/index) are thin wrappers that loop over the collections above via Liquid (`{% for x in site.<collection> %}`) rather than containing content directly — to add course content, add/edit collection entries, not the top-level pages.

## Config notes

- `baseurl` and the `aux_links` GitHub repo URL in `_config.yml` must match the current semester's repo name (e.g. `discretas1-udea-20262`) — these have historically been left pointing at the prior semester's repo after copying the template.
- `tagline` (`_config.yml`) and the intro paragraph in `README.md` embed the semester string (e.g. "2026-1") as plain text, separate from the repo-name references above.
- `liquid: strict_filters/error_mode: strict` is set — undefined Liquid variables/filters will hard-fail the build, not silently render blank.
