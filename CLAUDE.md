# CLAUDE.md

Jekyll site hosted on GitHub Pages using the Minimal Mistakes remote theme (dark skin).

## Local dev

```bash
./serve.sh --livereload    # serves at http://localhost:4000 with livereload
```

Never edit anything inside `_site/` — that is build output and is gitignored.

## Adding a project page

Create `projects/<slug>.md` with `layout: project`. The layout auto-generates the meta line and back link from front matter:

```yaml
---
layout: project
title: My Tool
permalink: /projects/my-tool/
language: Go           # optional
platform: Linux        # optional
github: https://...    # optional — renders "View on GitHub →" link
---
```

Then link to it from `projects.md`.

## Adding a writing/blog post

Create `blog/<slug>.md` with `layout: writing`:

```yaml
---
layout: writing
title: My Post
permalink: /blog/my-post/
---
```

## Layouts

| Layout | Use for | Adds automatically |
|---|---|---|
| `project` | Project detail pages | Meta line, sidebar TOC, back link |
| `writing` | Blog posts | Sidebar TOC, back link |
| `splash` | Home page | Hero header area |
| `single` | Generic pages (projects index, blog index) | Nothing extra |

## Sidebar TOC

Both `project` and `writing` layouts include `_includes/sidebar-toc.html`, which:
- Injects a nav into `.sidebar.sticky` (the left author panel) via JS on DOMContentLoaded
- Only activates at viewport ≥ 1024px (desktop only)
- Picks up all `h3[id]` and `h4[id]` in `.page__content` — kramdown generates IDs automatically
- Highlights the active section on scroll
- First entry is always the page title, linking to `#page-title`

## Navigation

Defined in `_data/navigation.yml`. Items with `children:` render as a hover dropdown on desktop (click on mobile). The dropdown is wired in `_includes/masthead.html` and styled in `assets/css/style.scss` under `// Nav dropdown`.

To add a top-level link:
```yaml
- title: "Page Name"
  url: /page-name
```

To add a dropdown:
```yaml
- title: "Label"
  children:
    - title: "Child"
      url: /child
```

## CSS

All custom styles live in `assets/css/style.scss`. The file is loaded after the theme's `main.css` so anything here overrides the theme.

Key colors:
- Accent / links: `#7eb8f7`
- Muted text: `#888`, `#aaa`
- Borders: `#333`, `#2a2a2a`
- Card backgrounds: dark rgba overlays on `#1a1a2e`

