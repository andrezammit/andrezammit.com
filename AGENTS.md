# Repository guidelines

## Overview

This is the static source for [andrezammit.com](https://andrezammit.com), hosted from GitHub Pages. It deliberately has no package manager, build step, or automated test suite.

## Project layout

- `index.html` is the complete site and contains page metadata, content, social links, and CDN dependencies.
- `assets/style.css` contains the shared/desktop styling.
- `assets/style-mobile.css` contains the mobile overrides and is loaded only at widths up to 768px.
- `assets/` also contains the site imagery. `profile-min.jpg` is the in-page avatar; `profile_og.jpg` is the Open Graph/card image; `profile.jpg` is the higher-resolution source image; and `pattern.png` is the page background.
- `CNAME` must remain a single line containing `andrezammit.com` unless the custom domain is intentionally changing.

## Making changes

- Keep the site dependency-free and static. Do not introduce a build system, package manager, or framework for small content or styling updates.
- Make the smallest focused change that fulfils the request. The history favors small, single-purpose commits.
- Preserve the existing four-space indentation and avoid unrelated reformatting. Keep the repository's existing line endings intact where possible.
- When updating social links, edit the matching anchor in `index.html`; retain its Font Awesome class unless the icon itself is changing.
- When changing profile or social-preview imagery, update the matching Open Graph and Twitter card metadata URLs in `index.html` as needed. Optimize replacement images before committing and retain the dedicated preview image dimensions.
- Keep third-party CDN URLs and their integrity attributes unchanged unless the task explicitly calls for dependency upgrades.
- Preserve the responsive split: put shared rules in `assets/style.css` and narrow-screen-only overrides in `assets/style-mobile.css`.

## Validation

- There is no build command. For HTML/CSS/content edits, inspect the relevant diff and run `git diff --check`.
- Search for stale URLs or labels after link and metadata changes (for example, with `rg`).
- When visual styling or responsive behavior changes, open the page locally and check both desktop and a viewport at or below 768px.

## Git conventions

- Use concise, focused commit subjects in the style of the existing history, such as `Remove Bitbucket social link` or `Update open graph metadata`.
- Do not commit generated files, dependency directories, or larger image sources unless they are intended site assets.
