# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Jekyll-based course website for "Matemáticas Discretas I" (Universidad de Antioquia), built on the [Just the Class](https://github.com/kevinlin1/just-the-class) template, which extends the [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme (`remote_theme` in `_config.yml`). Deployed via GitHub Pages classic build ("Deploy from a branch", `main` / root) — there is no `.github/workflows/` build pipeline; GitHub Pages builds directly from the `github-pages` gem.

The Just the Docs version pinned here (`v0.10.1`) is past `v0.9.0`, which shipped **unlimited-depth navigation** using only the `parent` field (no `grand_parent` required). See "Navigation nesting" below for the practical gotcha this still has.

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
- `lessons/` — actual class content, organized as `lessons/mod{N}/clase{N}.md` plus an `index.md` per module; not a Jekyll collection but a normal page tree with `permalink: '/:path/'` and layout forced to `default` (`has_children: false`) via the `scope: path: "lessons"` block in `defaults`. **Do not modify `lessons/` unless explicitly asked** — it's handled separately from config/date updates. (Exception: mechanical rendering fixes covered under "Rendering rules" below are safe to apply on request even to existing lesson content, since they never change pedagogical content — only markup.)

Top-level pages (`about.md`, `calendar.md`, `schedule.md`, `announcements.md`, `README.md`/index) are thin wrappers that loop over the collections above via Liquid (`{% for x in site.<collection> %}`) rather than containing content directly — to add course content, add/edit collection entries, not the top-level pages.

## Config notes

- `baseurl` and the `aux_links` GitHub repo URL in `_config.yml` must match the current semester's repo name (e.g. `discretas1-udea-20262`) — these have historically been left pointing at the prior semester's repo after copying the template. This same check applies to any hardcoded repo URL left inside `lessons/` content (e.g. a stray reference to `discretas1-udea-20261`) — grep for the previous semester's repo slug as a matter of routine after copying the template forward.
- `tagline` (`_config.yml`) and the intro paragraph in `README.md` embed the semester string (e.g. "2026-1") as plain text, separate from the repo-name references above.
- `liquid: strict_filters/error_mode: strict` is set — undefined Liquid variables/filters will hard-fail the build, not silently render blank.
- `exclude:` in `_config.yml` lists `CLAUDE.md` — it's kept out of the built `_site/` output.
- `callouts:` in `_config.yml` defines kramdown callout types in Spanish (`note`→"Nota", `tip`→"Consejo", `important`→"Importante", `warning`→"Advertencia"); used in lesson content via IAL syntax, e.g. `{: .note }` under a blockquote. See "Rendering rules" below for how to convert GitHub-style `[!NOTE]` alerts into this syntax.
- `math: mathjax` is already active site-wide via `_config.yml` — MathJax renders `$...$`/`$$...$$` automatically on every page. Do **not** add a manual MathJax `<script>` include to `_includes/head_custom.html` — that's advice for a vanilla Jekyll site with no math engine configured, and would load a conflicting second MathJax instance here. If math isn't rendering somewhere, the cause is a markup/escaping bug in that specific page (see "Rendering rules"), not a missing MathJax setup.

## Assets

Lesson-specific images live under `assets/images/lessons/mod{N}/clase{N}/` and are referenced from `lessons/` content with `{{ '/assets/images/...' | relative_url }}` (required because of `baseurl`). The same `relative_url` pattern applies to internal links between lesson pages — see "Rendering rules" below.

## Rendering rules — Just the Docs / kramdown / Liquid

Learned empirically while migrating and debugging lesson content (2026). These apply to every `.md` file under `lessons/`, including class notes, self-assessment (`*_autoevaluacion.md`), and workshop (`taller*.md`) documents. Check each one before considering a migration or a newly generated document "done".

### 1. GitHub-style alerts are not supported
`> [!NOTE]`, `> [!TIP]`, `> [!WARNING]`, `> [!IMPORTANT]` (GitHub's alert syntax) render as a plain blockquote with the literal text "[!TYPE]" visible — Just the Docs doesn't recognize this syntax; it needs the `callouts:` IAL syntax noted above instead.
- Correct conversion: drop the `[!TYPE]` line, keep the rest of the blockquote as-is, and add `{: .type }` (lowercase: `note`/`tip`/`warning`/`important`) immediately after the block — no blank line between the closing `>` line and the `{: .type }` line.

### 2. `<details>` needs TWO things at once, not one
Without both, inner content (bold, LaTeX, inline code) either fails to render as Markdown, or — worse — the block silently swallows the rest of the document with no visible error.
- (a) `markdown="1"` on the opening tag: `<details markdown="1">`
- (b) Multi-line format with real blank lines around the content:
  ```
  <details markdown="1">
  <summary>Text</summary>

  Content here, with a blank line before and after.

  </details>
  ```
  Never use the compact single-line form (`<details><summary>X</summary>content</details>`), even for short answers — it's the most common cause of a page silently truncating with no build error.

### 3. Liquid processes the file before kramdown does
Any `{{` in the text — including LaTeX with double braces, e.g. `\dfrac{{p\rightarrow q}\atop{p}}{q}` — can be parsed by Liquid as the start of a variable, breaking the build with "Liquid syntax error... was not properly terminated".
- Fix: wrap the affected block (the whole table, not just the formula) in `{% raw %}` … `{% endraw %}`.
- Exception: intentional Liquid usage (e.g. `{{ '/path/' | relative_url }}` for image or internal-link paths) must **not** be wrapped in raw — that's the correct mechanism, not a bug.
- Raw HTML `<table>` blocks (see rule 4) generally don't need this — plain `\begin{array}` has no double braces — but keep the check in mind whenever `\dfrac{{...}}`-style notation is involved.

### 4. `\hline` inside a table — root cause identified and solved
`\hline` breaks specifically inside **kramdown's native Markdown pipe-table syntax** (`| cell | cell |`) — kramdown's pipe-table parser mangles the LaTeX before MathJax ever sees it ("Misplaced \hline" on the built site), regardless of `\dfrac` vs `\begin{array}`, single vs multi-line, or how clean the raw Markdown looks in GitHub.com or any other renderer (those use different engines entirely and are not a valid test).

**Confirmed fix**: replace the Markdown pipe-table with a raw HTML `<table>`:
```html
<table>
<thead>
<tr><th>Nombre</th><th>Regla</th><th>Descripción</th></tr>
</thead>
<tbody>
<tr>
<td><strong>Modus Ponens</strong></td>
<td>

$$
\begin{array}{l}
p \to q \\
p \\
\hline
\therefore\ q
\end{array}
$$

</td>
<td>Si se da la causa, ocurre el efecto.</td>
</tr>
</tbody>
</table>
```
kramdown treats the whole `<table>...</table>` block as raw HTML passthrough and never applies its pipe-table parser, so `\hline` inside `\begin{array}{l}...\hline...\end{array}` reaches MathJax intact and renders correctly (confirmed working in production, 2026). Each math cell needs its LaTeX on its own blank-line-separated block within the `<td>` (same blank-line requirement as rule 2's `<details>`).

- Use this whenever a table needs `\hline`-style inference rules, or any LaTeX with literal `\\` row breaks in a cell.
- For tables WITHOUT that need, plain Markdown pipe-tables remain simpler — don't switch to HTML tables by default, only when `\hline`/`\\` inside a cell requires it.
- Safe fallback that avoids the whole issue (still a valid choice when an HTML table feels heavier than needed): `\dfrac{{premise1}\atop{premise2}}{\therefore\ conclusion}` inside a normal Markdown pipe-table cell — no `\hline`, no `\\`, works natively. Avoid nesting `\atop` inside `\atop` for 3+ premises (it shrinks the innermost text via MathJax's script-level scaling); instead comma-join two premises on one line inside a single `\atop` level.
- Do not trust an external tool's (ChatGPT/Gemini/etc.) generic claim about "Jekyll can't render X" at face value — verify against this repo's actual, tested config first. E.g. a suggestion to manually add a MathJax `<script>` to `_includes/head_custom.html` would be wrong here (see the `math: mathjax` note above) even though it's reasonable generic advice for a Jekyll site with no math engine configured.

### 5. Internal links: always via `relative_url`, never a raw file path
- Images: covered above (`assets/images/lessons/mod{N}/clase{N}/`).
- Links to other lessons: `[Clase N]({{ '/lessons/mod{N}/clase{N}/' | relative_url }})` — never `[Clase N](claseN.md)` (a file path, which doesn't resolve against the site's pretty permalinks).

### 6. Table of contents (TOC)
Each lesson/self-assessment/workshop doc should have:
```
## Tabla de Contenidos
{: .no_toc .text-delta }

1. TOC
{:toc}

---
```
placed right after the intro narrative, before the theory content starts (`# Parte I`, `## Calentamiento`, or `## Objetivo de aprendizaje`, depending on the document type).
- The decorative H1 title (and its H3 subtitle, if any) get `{: .no_toc }` so they don't show up in the index.
- Every `###` in the document gets `{: .no_toc }` — the auto-generated TOC is intentionally limited to `#`/`##` only.

### 7. Navigation nesting (`parent` / `has_children`)
- This repo's Just the Docs version supports unlimited nesting depth via `parent` alone (see note at the top of this file).
- The parent page still needs an explicit `has_children: true` in its front matter, or its children won't render nested in the sidebar — they disappear from the nav silently, with no error.
- The `parent:` value must match the parent page's real `title:` **exactly**, character for character (case, accents, hyphens) — a mismatch produces no error, the child page just doesn't appear anywhere in the nav tree.

### 8. Standard front matter for self-assessment and workshop pages
```yaml
---
layout: default
title: Autoevaluación 0N - <exact class title>
parent: <EXACT title of the corresponding claseN.md>
nav_order: 1
---
```
For workshop pages (`Talleres de Repaso`), same pattern with `parent: Talleres de Repaso` and sequential `nav_order`.

### 9. Internal "Clase N" numbering — recurring failure mode to watch for
Several previously generated lesson documents contain self-references and cross-references to "Clase N" that are off by one relative to the site's real numbering (e.g. a document that is really Clase 6 refers to itself as "Clase 7"). Before signing off on a migration or a new generation pass, grep the document for `Clase ` and `claseN.md` and check every number against the module's actual `nav_order` mapping. Don't apply a blind uniform shift across a whole document without verifying — some documents mix correct and incorrect references in the same file.

### 10. Line endings (CRLF/LF)
Files in this repo mix CRLF and LF depending on origin/authoring tool. When editing, preserve the existing file's line-ending style rather than normalizing it — normalizing produces noisy whole-file diffs in git for no functional benefit.

### 11. Anexos / appendix sections in workshop docs
Workshop (`taller*.md`) source files often ship with 3-4 generic appendix blocks (declarative sentence types, argumentative-passage indicators) inherited from a shared template, of which only one (the operators/rules formulary) is actually cross-referenced from the body. Before migrating, grep for `Anexo` across the whole file to check which appendix numbers are actually referenced in the body text — unreferenced ones are safe to drop on request. If only one appendix remains after trimming, rename the section header to singular ("Anexo completo") and drop the number from in-body references (just "el Anexo") rather than leaving a stale "Anexo 4" pointing at the only item.

### 12. Never use a literal `|` for absolute value / cardinality inside math
A bare `|` inside `$...$` or `$$...$$` — e.g. `|A|`, `|A \cap B|` — can be misread by kramdown as a Markdown table column separator, breaking the render into a garbled table even inside a callout or a plain paragraph (confirmed in production, 2026: a quoted `$\mathrm{Min}(|A|+|B|)$` inside a `{: .note }` callout rendered as a broken multi-column table instead of text). This is independent of the pipe-table issue in rule 4 — it can happen in a single inline formula with no table syntax anywhere nearby.

- Always use `\lvert ... \rvert` for cardinality/absolute value: `\lvert A \rvert`, `\lvert A \cap B \rvert`.
- If you're quoting a source verbatim that used a single stray `|` (e.g. documenting an error in a PDF's original notation), replace it with `\vert` instead of a literal `|` — `\vert` renders identically to `|` in MathJax but doesn't trip kramdown's table detection. Do this even when the quote is meant to show "what the original incorrectly said" — the visual result for the reader is the same, only the underlying character differs.
- When migrating or generating new content, grep for a bare `|` inside `$...$`/`$$...$$` as a routine check, the same way you'd check for `\hline` or `{{`.
