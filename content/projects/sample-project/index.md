+++
title = "Sample project"
description = "Placeholder entry showing how the projects list and detail pages work. Delete the sample-project folder once you add real projects."
date = 2026-09-30

[taxonomies]
tags = ["demo"]

# Optional: rendered as a "Languages:" row under the date. Omit for no row.
[extra]
languages = ["Rust", "Kotlin", "Jetpack Compose"]

# Optional: rendered as a "Links:" row under the languages. Add or remove
# entries freely (repository, app stores, project site); order is display order.
[[extra.links]]
name = "GitHub"
url = "https://github.com/example/sample-project"

[[extra.links]]
name = "Google Play"
url = "https://play.google.com/store/apps/details?id=com.example.sample"

[[extra.links]]
name = "App Store"
url = "https://apps.apple.com/app/id000000000"

# Optional: rendered as the horizontal screenshots carousel under the Links row,
# one block per image, in the order written here. Delete every block for no
# carousel. `src` is required; `alt` is what a screen reader announces and
# doubles as the caption when `caption` is omitted; `caption` is the label
# printed under the image.
[[extra.screenshots]]
src = "screenshot-1.svg"
alt = "Overview screen with the summary cards"
caption = "Overview"

[[extra.screenshots]]
src = "screenshot-2.svg"
alt = "Settings screen with the notification toggles"
caption = "Settings"

[[extra.screenshots]]
src = "screenshot-3.svg"
alt = "Mobile layout listing the projects"
caption = "Mobile"
+++

This is a placeholder so `/projects/` has something to render. Delete the whole
`content/projects/sample-project/` folder once you add your own projects — the
structure below is what a real project page looks like.

## Why this page has a date

The projects list is sorted newest first, so every project needs a `date` in its
front matter. A project without one is skipped at build time, and Zola only
mentions it as `1 page(s) ignored (missing date)` in the build log. The
`description` field is the one-line summary shown next to the title in the list.

## What a project page gives you

Clicking this entry in `/projects/` opened a page laid out like a blog post:
title, date, the front-matter rows, the screenshot carousel, the body below, a
table of contents generated from these headings, and prev/next links to the
neighbouring projects.

## Screenshots

This page is a *page bundle*: `content/projects/sample-project/index.md` lives in
a folder next to the images it uses, and Zola copies every file in that folder
to the page's own URL (`/projects/sample-project/`). Nothing needs configuring —
a file dropped in here is immediately available to the page.

The carousel above is built from front matter, so one more screenshot is one
more block:

```toml
[[extra.screenshots]]
src = "screenshot-4.png"
alt = "Reports screen with the monthly totals"
caption = "Reports"
```

`src` accepts three shapes:

- a bare filename, resolved next to this page, as above;
- a path starting with `/`, served from `static/` — for example `/img/logo.png`;
- a full `https://` URL, for an image hosted elsewhere.

`alt` is what a screen reader announces, and it doubles as the caption when
`caption` is left out, so `src` plus `alt` is the shortest useful entry.

The strip scrolls sideways with a trackpad, a touch drag, the accent scrollbar,
or the arrow keys once it has focus. There is no JavaScript involved: it is a
native scroll container, so it keeps working with scripting turned off.

The three `.svg` files in this folder are stand-ins. Replace them with real
`.png` or `.webp` screenshots and delete the ones you don't use.

## Languages and links

The `Languages:` and `Links:` rows above come from this page's front matter, and
both are optional — a project that omits them renders neither row:

```toml
[extra]
languages = ["Rust", "Kotlin"]

[[extra.links]]
name = "GitHub"
url = "https://github.com/you/repo"
```

`languages` is a plain list of labels, shown in the same muted monospace as the
date and separated by `·`. Each `[[extra.links]]` entry takes a `name` (the
visible link text) and a `url`, and entries render in the order written here.

Note that `languages` sits under `[extra]` rather than at the top level: Zola
only exposes custom front matter nested under `extra`, so a top-level key would
be silently dropped at build time.
