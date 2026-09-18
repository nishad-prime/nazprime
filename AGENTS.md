# nazprime - my corner of the internet

## Identity

nazprime is Nasir Hossain's personal corner of the internet.

It is not a conventional developer portfolio, résumé, agency website, freelancer landing page, or personal brand site.

The site should feel like a personal workshop, laboratory, notebook, archive, and playground.

Core idea:

> Taking things apart to build ’em back better.

The site is about curiosity, making, experimentation, learning, documenting interesting things, and following technical rabbit holes.

Do not frame Nasir as someone with a fixed set of mastered technologies.

Do not build the site's identity around a permanent technology stack.

Technologies are context for things being made, not a definition of the person.

Never invent:

* employment
* clients
* credentials
* awards
* achievements
* years of experience
* expertise
* project results
* statistics
* professional claims

Only use information that exists in project content or that has been explicitly provided.

## Hugo

Target Hugo version:

Hugo Extended with deploy support 0.166.0
Local platform: windows/amd64

Hugo version compatibility is a hard requirement.

Whenever making a Hugo-specific decision:

1. Verify the installed version with `hugo version`.
2. Prefer the current official Hugo documentation at https://gohugo.io/.
3. Verify behavior against the installed Hugo CLI when practical.
4. Do not rely on model memory for Hugo syntax when documentation or CLI help can verify it.
5. Do not copy old Hugo tutorials without checking that they apply to Hugo 0.166.0.
6. Do not introduce deprecated Hugo APIs or legacy template conventions.
7. When remembered knowledge conflicts with current Hugo documentation or the local CLI, trust the current documentation/CLI.

Hugo's template system has changed significantly in recent releases. Use the current template architecture and lookup conventions.

## Configuration

Use `hugo.yaml`.

Do not convert the project to TOML or JSON.

Keep `hugo.yaml` small and readable.

Prefer Hugo defaults unless a setting is intentionally required.

Do not create speculative configuration.

Do not introduce Hugo Modules unless there is an actual need.

Do not add a third-party theme.

This project uses custom first-party layouts.

## Content

Primary content sections:

* `content/projects/`
* `content/lab/`
* `content/notes/`
* `content/now/`
* `content/about/`

The content architecture must remain flexible.

Projects may be:

* software
* websites
* games
* game-engine experiments
* graphics experiments
* hardware projects
* Linux/system experiments
* tools
* prototypes
* abandoned projects
* unfinished experiments
* anything else worth documenting

Do not force unrelated things into one professional category.

## Content philosophy

Projects are artifacts and stories, not résumé entries.

Technologies should appear as metadata or context.

Prefer:

* built with
* experimented with
* explored
* used for this project
* currently learning
* currently working on

Avoid:

* expert in
* mastered
* specialist in
* highly skilled
* years of experience
* my tech stack
* technology expertise
* professional X

The site should communicate curiosity rather than authority.

## Design

The site should feel:

* personal
* editorial
* technical
* minimal
* tactile
* curious
* slightly unconventional
* independent

Avoid:

* generic developer portfolio layouts
* SaaS aesthetics
* agency aesthetics
* corporate design
* cyberpunk
* hacker-terminal clichés
* glassmorphism
* excessive gradients
* excessive cards
* skill bars
* technology percentage charts
* résumé timelines
* testimonials
* fake metrics
* unnecessary animations

Do not turn the site into a "developer portfolio template."

Prefer:

* strong typography
* generous whitespace
* thin rules
* editorial layouts
* lists
* numbering
* annotations
* subtle technical details
* restrained interaction

## Homepage

The homepage should communicate:

> nazprime — my corner of the internet

and the core phrase:

> Taking things apart to build ’em back better.

The homepage should primarily introduce:

1. who I am
2. what currently occupies my attention
3. things I have made
4. experiments
5. notes

Do not create a skills section.

Do not create an employment/experience section unless explicitly requested later.

Do not add "hire me" or service-selling CTAs.

## Sections

### Projects

Finished or substantial things I have made.

Projects should support:

* title
* summary
* date/year
* status
* optional technologies/tools
* images
* context
* story
* technical details
* lessons/discoveries
* source/demo links

### Lab

Experiments, prototypes, unfinished ideas, abandoned work, weird investigations, hardware experiments, graphics experiments, Linux experiments, games, and other technical rabbit holes.

The Lab is explicitly allowed to contain imperfect work.

### Notes

A personal technical notebook.

Writing should feel human and direct rather than corporate or SEO-generated.

### Now

A small living snapshot containing things such as:

* building
* exploring
* learning
* currently interested in
* currently obsessed with

The content should be easy to edit manually.

### About

Short, personal, and human.

Not a résumé.

Do not turn the About page into a skills inventory.

## Frontend

Use:

* Hugo templates
* Markdown
* Tailwind CSS
* minimal vanilla TypeScript/JavaScript

Do not use React.

Do not build an SPA.

Do not introduce a JavaScript framework unless a genuinely interactive feature requires one.

Prefer HTML/CSS over JavaScript whenever practical.

## Tailwind

Use the current Tailwind CSS integration appropriate for this Hugo version.

Do not use obsolete Hugo/Tailwind integration examples.

Before changing the Tailwind build pipeline, verify current official Hugo documentation.

Do not add a large component system.

Use existing styles and patterns before introducing new ones.

## Templates

Prefer simple, explicit Hugo templates.

Use partials for genuinely reused pieces.

Do not create abstractions for one-off markup.

Do not create generic components merely to make the code appear sophisticated.

Keep template logic easy to follow.

Avoid cleverness.

## Copy

The writing should sound like a real person.

Avoid generic marketing language such as:

* passionate developer
* cutting-edge technology
* innovative solutions
* results-driven
* turning ideas into reality
* highly experienced
* full-stack professional

Do not make everything sound polished for the sake of sounding polished.

Natural, direct, understated, and occasionally playful is preferred.

## Performance

Prefer:

* static HTML
* optimized images
* responsive images
* minimal JavaScript
* minimal third-party scripts
* efficient CSS
* local assets where sensible

Do not install a library for something that can be implemented cleanly with HTML/CSS or a small amount of TypeScript.

## Accessibility

Use semantic HTML.

Maintain:

* logical heading hierarchy
* keyboard accessibility
* visible focus states
* accessible navigation
* suitable contrast
* alt text
* reduced-motion support

## Git

The primary Git remote is named:

`origin`

Use SSH.

Remote URL format:

`git@github.com:<username>/nazprime.git`

Push to `origin`.

Do not use GitHub CLI.

Do not rewrite remote history unless explicitly requested.

Never force-push.

Do not commit generated Hugo output such as `public/` unless explicitly required.

Write small, meaningful commits.

## GitHub Pages

Deployment target:

GitHub Pages through GitHub Actions.

Pin Hugo to exactly 0.166.0 in CI.

Never use `latest`.

Before writing or changing the deployment workflow, consult the current official Hugo GitHub Pages documentation and GitHub Pages documentation.

Use the current GitHub Pages artifact/deploy workflow.

Do not use old third-party deployment actions unless there is a documented reason.

The custom domain is:

`https://nazprime.com/`

Do not invent another domain.

When using a custom GitHub Pages Actions workflow, do not depend on a `CNAME` file being committed to the source repository. Configure the custom domain through GitHub Pages settings as appropriate.

## Verification

After meaningful changes:

`hugo version`

`hugo build --gc --minify --printPathWarnings --printUnusedTemplates --logLevel info`

Fix relevant warnings instead of ignoring them.

For substantial template changes, use Hugo's template diagnostics/metrics when useful.

After changing deployment configuration, verify the workflow and local production build.

Do not declare a task complete solely because the page visually renders.

## Architectural discipline

When multiple approaches work, choose the smallest current Hugo-native solution.

Do not add complexity simply because Hugo, Tailwind, JavaScript, or GitHub can support it.

Prefer code that will still be understandable six months from now.

The site is a personal place, not a software architecture showcase.
