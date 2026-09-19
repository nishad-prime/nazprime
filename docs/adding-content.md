# Adding content

Everything on this site is a plain Markdown file with YAML front matter. Write in Obsidian (or any editor), commit and push. GitHub Actions builds and deploys.

Two Obsidian tips:

- In Settings → Files & Links, turn off `Use [[Wikilinks]]` so links stay standard Markdown, which Hugo understands.
- Never mind `.hugo_build.lock`, `public/`, and `resources/`; they're generated and ignored.

All examples below are examples only. Nothing in this file becomes site content.

## A Project

**Location:** `content/projects/<name>/index.md`: one folder per project (short slug: `traffic-light-controller`, not `My Traffic Light Controller`). Images and files live in the same folder.

Minimal front matter:

```yaml
---
title: Traffic Light Controller
date: 2026-10-01
draft: true
---
```

Optional fields (all of them are free to omit):

```yaml
summary: One line, shown in lists.        # list teaser
description: A longer lead for the page.  # page lead + meta description
tags: [hardware]                          # any tags; pages generate themselves
status: in progress                       # free text: finished, on hold, abandoned, ...
tech: [C, Raspberry Pi]                   # shown as "built with ..."
source: https://github.com/you/thing      # link, optional
demo: https://example.org                 # link, optional
```

Body: what it is and why → `## The build` (story + technical details) → `## Discoveries` (lessons). CLI users can scaffold this skeleton with `hugo new content projects/<name>/index.md` (optional).

**Images and files:** put them next to `index.md` and reference by filename: `![alt text](photo.jpg)`, `[schematic](schematic.pdf)`. Hugo resolves and copies them.

**Visibility:** with `draft: true` the project is excluded from the built site (preview locally with `hugo server -D`). Remove the draft line (or set `false`) and push; it appears at `/projects/<name>/`, in the Projects list, in the nav, and on the homepage. The Projects nav item itself only exists once at least one project is published.

## A Lab entry

Exactly like a project: `content/lab/<name>/index.md`, same front matter. The status vocabulary is lab-flavored (`experiment`, `in progress`, `unfinished`, `abandoned`), and unfinished or abandoned are perfectly good endings.

## A Note

**Location:** `content/notes/<name>.md`: a single file, no folder needed.

```yaml
---
title: Fixing the Wi-Fi Drop
date: 2026-10-02
draft: true
summary: What finally worked.
tags: [linux, networking]
---
```

Write the note below the front matter; code blocks are first-class. If a note needs images, make it a folder with `index.md` like a project. Published notes appear at `/notes/<name>/`, in the Notes list, and the three latest on the homepage.

## Now

Edit `content/now/index.md` directly; it's just bold-label lines:

```markdown
**Building**: a mechanical keyboard from scratch.
**Exploring**: how old consoles drew graphics.
```

Bump `lastmod:` in its front matter when you edit; the page shows an "updated" date.

## About

Edit `content/about/index.md`. Plain Markdown, no special structure.

## Tags

Add `tags: [a, b]` to any project, lab entry, or note. Tag pages at `/tags/<tag>/` generate themselves and are linked from the page footer. Pages without tags show nothing tag-related.

## Section list pages (optional)

`/projects/`, `/lab/`, and `/notes/` work without any setup; the section appears when its first entry exists. To give one a title and description, add e.g. `content/projects/_index.md`:

```yaml
---
title: Projects
description: Finished or substantial things I've made.
---
```

## Dates

Lists sort newest-first by `date`. One gotcha: a bare date (`2026-10-02`) means UTC midnight; if you're writing in the early hours (before ~6am Bangladesh time), date the piece as the previous day or include a time (`2026-10-02T12:00:00+06:00`), or it will count as "future" and stay invisible.

## Writing style

The short checklist that keeps the site sounding like one person:

- Write like you talk. Direct, plain, occasionally playful. No corporate or marketing voice.
- No em dashes anywhere. Commas, periods, colons, parentheses instead (site-wide convention).
- Technologies are context, never identity: "built with C", not "expert in C".
- Only real things. No invented projects, results, or claims; unfinished and abandoned are fine.
- Titles: specific and short. "Fixing the Wi-Fi Drop", not "Some Thoughts on Networking".
- `summary` is one honest sentence; `description` is the same voice, one or two.
- Statuses stay honest: `in progress`, `unfinished`, `abandoned` are all legitimate states.

## The whole workflow

Obsidian → write the file with front matter → remove `draft` when ready → commit and push → live at [nazprime.com](https://nazprime.com/) in a minute or two.
