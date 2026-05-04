# Trellis Site — Project Orientation for Claude

You are working on the **Trellis Site**, a static Jekyll site that
publishes Gabe Gloege's *Trellis: A Framework for AI Adoption* as a
book-style website. Read this whole file before doing anything else.
It is the orientation.

---

## Vision

Trellis is a long-form methodology book. The site presents it the way
Basecamp's [Shape Up](https://basecamp.com/shapeup) presents Ryan
Singer's book — landing page that opens the book to its first page,
clean chapter pages with prev/next navigation, a table of contents
grouped by part, and editorial typography. No marketing chrome, no
newsletter signup, no purchase flow. Open the book and read it.

The visual identity is Gabe's personal brand (warm editorial
minimalism — Fraunces + Inter on ivory paper, brick red accent) — the
same design system used by LXD Studio OS. See "Cross-project
references" below.

The site is hosted at **<https://ggloege.github.io/trellis/>** under
the `ggloege/trellis` GitHub repo.

---

## What's been built

| Surface | Status | Notes |
|---|---|---|
| Jekyll 4 site shell | ✅ working | `_layouts`, `_includes`, baseurl `/trellis` |
| Design system CSS | ✅ working | `assets/css/styles.css` — full token set mirroring LXD Studio OS |
| Landing page | ✅ working | Renders Trellis overview/exec summary + auto-generated TOC |
| Chapter collection | ✅ working | All 18 chapters imported, prev/next nav working end-to-end |
| Figures | ✅ working | 3 SVGs in chapters 3, 8, 13 — Liquid-aware paths so they resolve under `/trellis` |
| About page | ✅ working | Minimal, links to gabegloege.com |
| GitHub Pages deploy | ✅ working | Via `.github/workflows/jekyll.yml` (GitHub's default starter, edited) |
| Content management workflow | 🚧 not built | See "Open work" below |
| Glossary / appendix | ❌ not present | The original 00-overview mentions Appendix A; no chapter file exists |

**Repo:** <https://github.com/ggloege/trellis>
**Branch:** `main` (every push to `main` triggers a Pages deploy)

---

## Architecture at a glance

- **Stack:** Jekyll 4.4 with kramdown (GFM input). No build step beyond
  Jekyll itself. Hosted as a static site on GitHub Pages.
- **Why not the github-pages gem:** It pins ancient Jekyll/Liquid
  versions that break on Ruby 3.2+. We use vanilla Jekyll 4 locally
  and build via the GitHub Actions workflow on push.
- **Chapters as a Jekyll collection:** Each chapter lives in
  `_chapters/NN-slug.md` with YAML front-matter that drives the
  layout. The chapter layout reads `chapter`, `title`, `subtitle`,
  `part`, `part_title` from front-matter and renders the header.
  Prev/next nav is computed at build time by sorting `site.chapters`
  on the `order` field.
- **TOC grouping:** `_data/parts.yml` lists the five parts (plus a
  reserved Appendix entry that doesn't currently render anything).
  The `toc.html` include iterates parts and pulls chapters whose
  `part:` field matches. Empty parts render nothing — the guard is
  `{% if part_chapters.size > 0 %}`.
- **Figures:** Source markdown uses `![alt](figures/foo.svg)`. On
  import, those become `<figure>` blocks with
  `<img src="{{ '/assets/figures/foo.svg' | relative_url }}" …>` so
  they resolve correctly under the `/trellis` baseurl.
- **Baseurl handling:** Production baseurl is `/trellis` (set in
  `_config.yml`). Local preview uses `bundle exec jekyll serve
  --baseurl ""` to serve at root.

---

## Conventions discovered along the way

These weren't decided up front. Honor them.

### Content workflow

- **Source of truth for chapters is `Trellis Methodology/`** (sibling
  folder under `Documents/Projects/`). Chapter files in `_chapters/`
  are imports — when chapter content changes, re-read the source
  files and regenerate the import.
- **Front-matter pattern for chapters** (when importing):
  ```yaml
  ---
  title: The Premise
  subtitle: 'Why "AI Strategy" Is the Wrong Frame'   # optional
  chapter: 1
  order: 1
  part: I
  part_title: Foundations
  slug: the-premise
  ---
  ```
  Strip the `# Chapter N — Title` H1 and `*Part X: Name*` italic line
  from the source body — the layout renders both.
- **Figure paths:** Always convert
  `![alt](figures/foo.svg)` →
  `<figure><img src="{{ '/assets/figures/foo.svg' | relative_url }}" alt="alt"></figure>`
  on import.

### Design

- **Sentence case headlines.** No Title Case anywhere outside the
  eyebrow labels (which are the only uppercase exception, per the
  design system spec).
- **No emoji as visual elements.** Ever.
- **Brick red is the only accent.** Used sparingly — primary buttons,
  links, hero italic, the brand mark. Roughly 5–10% of any view.
- **Single design system source of truth:** the tokens in
  `assets/css/styles.css :root` mirror the LXD Studio OS spec at
  `Documents/Projects/LXD Studio OS/docs/design-system.md`. If the
  spec changes, the CSS here should be updated to match.

### Git & deploy

- **Don't push to `main` without Gabe's say-so.** Every push triggers
  a Pages deploy.
- **Workflow file is `.github/workflows/jekyll.yml`** (GitHub's
  default starter, with Ruby version bumped). Don't add a second
  workflow — they will race on deploy.
- **Never force-push.**
- **Gemfile.lock is committed** for reproducible CI. See the Ruby/
  bundler memory note (`feedback_ruby_bundler_lock.md`) for the
  bundler-version-vs-Ruby gotcha — when regenerating the lock, use
  bundler 2.5.x so CI's Ruby 3.3 can read it.

### Voice & UX

- **Plain language, no developer jargon without explanation.** Gabe
  is not a software developer. When introducing a technical concept
  (Jekyll collection, baseurl, Liquid filter), explain in plain
  terms why it exists and what it does. See his user memory for
  background.

---

## Open work

Things that are intentionally parked, in priority order:

1. **Content management workflow** — there's no script or process
   yet for re-importing chapters when the source markdown in
   `Trellis Methodology/` changes. The current import was a one-shot
   manual transformation. Build this when the methodology changes
   meaningfully or when stale cross-references need fixing.
2. **Stale cross-references** — Gabe deferred fixing these so the
   first run of the content-management workflow has something
   meaningful to do. Don't fix them ad-hoc in the meantime.
3. **Appendix entry in `_data/parts.yml`** — also parked for the
   content-management workflow test. Currently renders as nothing
   (the TOC guards against empty parts), so it's harmless.
4. **Glossary** — Shape Up has one. Trellis doesn't yet. Worth
   considering once content stabilizes.
5. **Custom domain** — currently `ggloege.github.io/trellis`. Could
   move to a subdomain (e.g. `trellis.gabegloege.com`) later.

---

## Where to find things

- `_config.yml` — site-wide config, baseurl, collection definition.
- `_layouts/default.html` — base HTML scaffold (Fraunces + Inter,
  header, footer, jekyll-seo-tag).
- `_layouts/home.html` — landing page wrapper.
- `_layouts/chapter.html` — chapter wrapper with prev/next nav logic.
- `_includes/header.html`, `footer.html`, `brand-mark.svg`,
  `toc.html` — partials used by the layouts.
- `_data/parts.yml` — the five parts + Appendix entry. Drives TOC
  grouping.
- `_chapters/NN-slug.md` — the 18 chapter pages.
- `assets/css/styles.css` — the entire design system as one file.
- `assets/figures/` — the 3 SVGs from the methodology folder.
- `index.md` — landing page content (Trellis overview + TOC include).
- `about.md` — about page.
- `.github/workflows/jekyll.yml` — Pages deploy workflow.

---

## Cross-project references

Pull these into context only when relevant to the current task:

- **`Documents/Projects/LXD Studio OS/docs/design-system.md`** —
  the canonical brand spec. Source of truth for color tokens, type
  scale, components (callouts, tags, venation divider), and the
  "voice" rules. The CSS in `assets/css/styles.css` mirrors this.
- **`Documents/Projects/Trellis Methodology/`** — the chapter source
  files, named `00-overview.md` through `18-starting-where-you-are.md`.
  Re-read these when importing or re-importing chapters. The folder
  also contains `figures/` (SVG sources) and `_revision-notes.md`
  (skip — meta file, not site content).

---

## Local preview

```bash
cd "Documents/Code Projects/Trellis Site"
bundle install                              # only needed once
bundle exec jekyll serve --baseurl ""       # http://127.0.0.1:4000/
```

Ruby 4.0+ via Homebrew is on PATH (added to `~/.zshrc`). If `bundle`
isn't found, run:

```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

---

## How to keep this file honest

At the end of any session that produces commits or makes a
content/architecture decision, ask Gabe:

> "Want me to update CLAUDE.md to reflect what we just built? I'll
> show the diff before saving."

If he says yes, update the affected sections. The status table and
the open-work list are the highest-value things to keep current.

A stale orientation doc is worse than no orientation doc — it leads
future-you confidently down the wrong path. Keep it current.
