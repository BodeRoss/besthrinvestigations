# Maintenance

The site is meant to be maintained by a person, in any text editor, without Cursor or other AI tools. Git and the files in this repository are sufficient.

## What you need

- This repository
- A text editor
- A current desktop browser
- Git, for saving and reviewing changes

You do not need Node, a package install, a framework CLI, or an AI assistant to edit or preview the intended site.

## Everyday edits

1. Open the HTML file for the page in `src/pages/`.
2. Change the text or markup. Keep headings, links, and image descriptions meaningful.
3. If the change is visual, edit the relevant file in `src/css/`.
4. If the change is behavior, edit the relevant file in `src/js/`. Prefer HTML and CSS when they can do the job.
5. Put new images in `public/images/` and new font files in `public/fonts/`. Use paths relative to the page.
6. Open the page in a browser and check it at a narrow width and a wide width. Use the keyboard to reach every link and control.
7. Commit the change with a short message that says why it changed.

Shared header or footer markup, once it exists, will live in `src/components/`. Until a later decision adds a build step, those fragments are copied into each page by hand. That keeps the published files obvious.

## How to preview

Open the HTML file in a browser. That is enough for content and layout while the site has no server-only features.

If a browser blocks a local script or font because the page was opened as a file, use any static file server you already trust, from the repository root, and open the page over `http://localhost`. Do not add a project dependency just for preview unless that decision is recorded in `TECH_STACK.md` and `DECISIONS.md`.

## What not to add during a routine edit

- Packages, CDNs, or new accounts
- Secrets, API keys, or passwords in source files
- A backend, database, or form processor
- Removal of a page or feature that is already live, unless that removal was approved

## Where to look when something is unclear

| Question | Document |
| --- | --- |
| What is the site for? | `PROJECT_OVERVIEW.md` |
| How are files organized? | `ARCHITECTURE.md` |
| What tools are actually in use? | `TECH_STACK.md` |
| What is done and what is not? | `PROGRESS.md` |
| Why was a constraint chosen? | `DECISIONS.md` |
| How does the live site get updated? | `DEPLOYMENT.md` (still pending) |

If a maintenance task requires a new tool or service, stop and record the proposal in `DECISIONS.md` before changing the architecture.
