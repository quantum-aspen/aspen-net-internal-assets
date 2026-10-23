# aspen-net-pages — agent notes

Static pages for the ASPEN-NET software team: interactive diagrams and design drafts.
Everything under `site/` is published to GitHub Pages by `.github/workflows/pages.yml` on
every push to `main`, so **a commit on `main` is a publish**. There is no build step: the
files in `site/` are served exactly as they are.

Live at <https://quantum-aspen.github.io/aspen-net-pages/>.

## What belongs here

Only pages the wiki can't show: interactive diagrams, explorable visualizations, small
tools, anything that needs its own HTML, CSS or JS. They don't have to start as Claude
artifacts.

Plain text doesn't belong here, even when it's formatted as HTML. Notes, write-ups,
tables, decision records and static diagrams (Mermaid, images) go on the wiki, or in
GitHub per the wiki's "Where Things Live" page. If a page is mostly prose with an
interactive piece, put the prose on the wiki and only the interactive piece here.

## Public, but not advertised

- The repo and the site are both public. Anything committed, including git history, can
  be read by anyone. Don't add credentials, internal hostnames, or anything the team
  hasn't agreed to make public. Removing something later doesn't take it out of history.
- Every page keeps `<meta name="robots" content="noindex">` in its `<head>`, and
  `site/robots.txt` blocks crawlers. Keep both when adding or editing pages.
- No analytics or third-party trackers.

## Adding a page

- One folder per page: `site/<slug>/index.html`, linked as `<slug>/` (with the trailing
  slash). Slugs are lowercase-kebab and permanent once linked from the wiki.
- Keep pages self-contained: inline CSS and JS. Use relative paths only. The site is
  served under `/aspen-net-pages/`, so a root-absolute path like `/foo.css` breaks.
- External scripts come from a CDN with an exact pinned version (e.g. `d3@7.9.0`), never
  `latest` or an unpinned major version.
- Support light and dark mode (`prefers-color-scheme`) and phone widths.
- Add the page to the list in `site/index.html` and to the table in `README.md`.
- Pages often start as Claude artifacts. When porting one, replace the artifact's
  wrapper `<head>` with a normal one (doctype, `lang`, charset, viewport, `noindex`).

## Preview

`python3 -m http.server -d site` then open <http://localhost:8000>.

## Related

- Each page usually has a matching page on the wiki (<https://wiki.quantum-aspen.net>),
  under ASPEN-NET Internal › Software. The wiki page holds a static snapshot and links
  here for the interactive version. When a diagram changes, the snapshot there needs
  re-uploading.