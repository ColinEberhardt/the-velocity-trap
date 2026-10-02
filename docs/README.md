# The Velocity Trap — site

A minimal Jekyll site for reading the manuscript in [`../manuscript-v2/`](../manuscript-v2/) as a book, rather than as loose markdown files. Every chapter uses a book-like serif layout with a small printer's flourish (⁂) marking scene breaks. Chapter 1's system-log excerpts render as small monospace panels. The older `report` layout, used for v1's incident-report chapter 1, is still available but no chapter uses it now.

Chapter content here is generated from `../manuscript-v2/chapter-*.md`. The `# Chapter N — Title` heading is stripped, and the title and chapter number are pulled into front matter. `chapter-00.md` (the author's note) is hand-written here and isn't generated. If you redraft a chapter in `../manuscript-v2/`, re-run the same conversion to update `_chapters/` (or just hand-edit the file in `_chapters/` directly if that's easier — the two aren't automatically kept in sync).

## Preview locally

You'll need Ruby installed. From this `docs/` directory:

```
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## Publish on GitHub Pages

This site lives in the `docs/` folder of this repo's root, which is a supported GitHub Pages source. In this repo's Settings → Pages, set Source to "Deploy from a branch", branch `main`, folder `/docs`. GitHub will build it with Jekyll automatically (no Actions workflow needed) since the `Gemfile` uses the `github-pages` gem, which matches what GitHub's own Pages builder runs.

## Structure

```
docs/
  _config.yml         site title/description, collection config
  _layouts/
    default.html      shared page chrome (header/footer, fonts, CSS)
    chapter.html       normal book-style chapters
    report.html       chapter 1's incident-report style
  _includes/
    chapter-nav.html  prev/contents/next footer
  _chapters/           the 24 chapters (Jekyll collection)
  assets/css/main.scss  all styling — palette, type, the ⁂ scene-break flourish
  index.md            homepage + table of contents
```

## Changing things

- **Title/subtitle/blurb:** edit `_config.yml` — the title is `"The Velocity Trap"` (confirmed 2026-09-14, no longer a placeholder), settable in one place.
- **Colours/fonts/flourish:** all in `assets/css/main.scss` — see the `$paper`, `$ink`, `$accent` variables near the top, and the `hr::after` rule for the scene-break glyph.
- **Which chapters use the report style:** controlled per-chapter by `layout: report` vs `layout: chapter` in each file's front matter in `_chapters/`.
