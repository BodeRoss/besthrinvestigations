# Architecture

## Intent

The website is a lightweight frontend made of HTML, CSS, and JavaScript. A person should be able to open the files, see how a page is built, and change it with a text editor.

There is no application server, database, CMS, authentication system, or external service in the intended design. Do not add one unless a real requirement is demonstrated and the change is approved before it is built. Record that decision in `DECISIONS.md`.

## Repository layout

```text
index.html         Home page
services.html      Services page
process.html       Process page
about.html         About page
contact.html       Contact page
.cursor/rules/     Persistent project rules for work in this repository
docs/              Project documentation (this file and its neighbors)
public/images/     Image files served with the site
public/fonts/      Font files, if self-hosted fonts are used
src/css/           Stylesheets
src/js/            Browser scripts
src/components/    Reusable markup fragments, kept as ordinary HTML
```

The repository root is the static publishing directory. `index.html` is the homepage. A host can serve this folder directly. There is no build step that copies or rewrites the pages.

`src/components/` is a folder for shared HTML fragments. It is not a component framework and does not imply a build step.

## How a page is expected to work

Each page is an HTML document. It links to stylesheets in `src/css/` and, only when behavior is needed, to scripts in `src/js/`. Images and fonts live under `public/` and are referenced by relative paths.

No build, bundler, or package install is part of this architecture. If a page works only after a compile step, that is a change to this architecture and needs approval first.

## Boundaries

| Concern | Decision |
| --- | --- |
| Rendering | Static HTML in the browser |
| Styling | CSS in this repository |
| Behavior | Small JavaScript files in this repository, only where HTML and CSS are not enough |
| Data | Content lives in the HTML (or later, in files in this repository). No database |
| Accounts | None |
| Third parties | None, unless approved and documented |

## Accessibility and layout

Pages should use semantic HTML, keyboard-reachable controls, and text alternatives for meaningful images. Layout should respond to narrow and wide viewports with CSS. Specific breakpoints and visual design are not decided yet.
