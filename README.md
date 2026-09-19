# andrezammit.com

The source for [André Zammit's personal website](https://andrezammit.com/), with project links, social profiles, and contact information.

A small, static site hosted on GitHub Pages with a custom domain. There is no package manager, build step, or backend. The page uses HTML and CSS, with Bootstrap, Font Awesome, jQuery, and Popper loaded from CDNs.

## Projects featured

- [SocialTicker](https://socialticker.andrezammit.com/) — live updates from X in a social ticker.
- [PostsDash](https://postsdash.com/) — a browser extension for a tiled X / Twitter dashboard.
- [Instagram Dashboard](https://chromewebstore.google.com/detail/instagram-dashboard/bofgllabgmnckgnakhicnkbhoanfaidb) — an automatically updating, tiled Instagram feed.
- [Media Library](https://medialibrary.andrezammit.com/) — a searchable collection of music, films, and books.
- [Music DNA](https://musicdna.andrezammit.com/) — an interactive exploration of a music collection by artists, eras, and formats.

These projects are maintained separately; this repository contains the personal website that links to them.

## Repository layout

| Path | Purpose |
| --- | --- |
| `index.html` | Page content, social links, project cards, metadata, and structured data |
| `assets/style.css` | Shared styles and desktop layout |
| `assets/style-mobile.css` | Overrides for viewports up to 768px |
| `assets/` | Profile photos, social-preview image, and background pattern |
| `robots.txt` | Crawler directives and sitemap location |
| `sitemap.xml` | Canonical URLs for this site |
| `CNAME` | GitHub Pages custom domain |
| `AGENTS.md` | Repository editing and validation guidelines |

## Local preview

Clone the repository and open `index.html` in a browser. Internet access is needed for the CDN assets.

Alternatively, if Python is installed, serve the repository from its root:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Then visit [localhost:8000](http://localhost:8000/). Stop the server with `Ctrl+C`.

## Making changes

- Edit content and links in `index.html`. To add a project, copy a list item inside `ul.projects` and update its name, category, description, URL, and accessible link label. Cards wrap into new rows automatically.
- Keep shared styles in `assets/style.css` and narrow-screen overrides in `assets/style-mobile.css`.
- Keep the page title, description, canonical URL, social-sharing metadata, and JSON-LD consistent with the site's content.
- Add any new indexable pages on this domain to `sitemap.xml`. The linked projects on other domains or subdomains maintain their own sitemaps.
- Keep `CNAME` set to `andrezammit.com` unless intentionally changing the domain.

There is no automated test suite or build command. Before committing, inspect the diff and run:

```sh
git diff --check
```

For layout changes, check desktop, tablet, and phone widths in a browser. Verify updated links and avoid committing generated files or adding build tooling for small changes.

## Hosting

GitHub Pages serves the static site at [andrezammit.com](https://andrezammit.com/). Publishing follows the repository's configured Pages source; no local build output is required.
