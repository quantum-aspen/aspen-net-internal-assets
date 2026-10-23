# aspen-net-pages

Static web pages for the ASPEN-NET software team: interactive diagrams and design drafts.

Only pages the wiki can't show belong here: interactive or custom HTML, not plain text. Notes and write-ups go on the [wiki](https://wiki.quantum-aspen.net).

**Live at:** https://quantum-aspen.github.io/aspen-net-pages/

Everything in `site/` is published to GitHub Pages by a GitHub Actions workflow on every push to `main`. There's no build step.

The site is public but not advertised: every page carries `noindex` and `robots.txt` blocks crawlers. Don't put anything here that can't be public.

## Adding a page

1. Make a folder with an `index.html`, e.g. `site/my-diagram/index.html`. Keep it self-contained (inline CSS and JS; pinned CDN scripts are fine) and use relative paths.
2. Add `<meta name="robots" content="noindex">` to its `<head>`.
3. Link it from `site/index.html` and add it to the table below.
4. Open a PR. Once merged, it's live at `https://quantum-aspen.github.io/aspen-net-pages/my-diagram/` within a minute or two.

To preview locally: `python3 -m http.server -d site`, then open http://localhost:8000.

## Pages

| Page | Wiki |
|------|------|
| [System Map](https://quantum-aspen.github.io/aspen-net-pages/system-map/) | [System Map](https://wiki.quantum-aspen.net/doc/system-map-mmczJY9ddV) |
