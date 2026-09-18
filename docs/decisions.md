# Decisions

Durable choices that shape this project. Implementation details live in the code; rationale for anything here is in `AGENTS.md`.

## Platform

- **Hugo 0.166.0 (Extended, with deploy)** is the project baseline. Version compatibility is a hard requirement; CI pins the exact version.
- **`hugo.yaml`** is the configuration format. No TOML, no JSON.
- **Custom first-party layouts.** No third-party theme. Templates follow the Hugo 0.146+ template system (`layouts/` root, `_partials/`, no `_default/`).
- **Tailwind CSS v4** via the npm CLI, wired through Hugo's `css.TailwindCSS` and the documented build-stats pipeline.

## Identity

- **nazprime is a personal corner of the internet** — a workshop, laboratory, and notebook. It is intentionally not a developer portfolio, résumé, or personal brand site.
- **Technologies are contextual metadata** on individual projects and experiments ("built with …"), never a site-level skills inventory. No invented accomplishments, employment, or claims.

## Infrastructure

- **Canonical domain:** `https://nazprime.com/`
- **Deployment:** GitHub Pages through GitHub Actions, with a custom domain configured in Pages settings (no committed `CNAME` file). The workflow is not yet written — create it against the current official Hugo/GitHub Pages documentation when the time comes.
- **Git:** primary remote is `origin` over SSH (`git@github.com:nishad-prime/nazprime.git`). Generated output (`public/`, `resources/`, `hugo_stats.json`) is never committed.
